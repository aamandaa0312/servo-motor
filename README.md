[*Servo Motor + LEDs*
![Media](https://github.com/user-attachments/assets/60e7ce62-9ebc-4083-9904-0d9d1ec1c187)

📦 Materiais necessários
1x ESP32

1x Servo motor (ex.: SG90)

3x LEDs (vermelho, amarelo, verde ou cores de sua preferência)

3x Resistores (220 Ω ou 330 Ω)

Jumpers

Protoboard

🔌 Ligações
Servo motor

Fio laranja (sinal) → Pino 19 do ESP32

Fio vermelho (VCC) → 3.3V ou 5V (dependendo do servo)

Fio marrom (GND) → GND

LEDs

LED1 → Pino 2

LED2 → Pino 4

LED3 → Pino 18
(cada LED deve ter resistor em série)

📜 Código
#include <ESP32Servo.h>
#include <Arduino.h>
Servo meuMotor;

// Definição dos pinos
const int LED1 = 2;
const int LED2 = 4;
const int LED3 = 18;
const int SERVO = 19;

void setup()
{
  // Configuração do servo
  meuMotor.attach(SERVO);
  meuMotor.write(0);

  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
}

void loop()
{
  meuMotor.write(180);
  delay(1000);
  digitalWrite(LED3, HIGH);

  meuMotor.write(90);
  digitalWrite(LED3, LOW);
  digitalWrite(LED2, HIGH);
  delay(1000);

  meuMotor.write(0);
  digitalWrite(LED2, LOW);
  digitalWrite(LED1, HIGH);
  delay(1000);

  meuMotor.write(90);
  digitalWrite(LED1, LOW);
  digitalWrite(LED2, HIGH);
  delay(1000);

  meuMotor.write(180);
  digitalWrite(LED2, LOW);
  digitalWrite(LED3, HIGH);
  delay(1000);
}
▶️ Explicação do funcionamento
O servo é inicializado na posição 0°.

O programa movimenta o servo para 180°, acendendo o LED3.

Depois vai para 90°, apagando o LED3 e acendendo o LED2.

Em seguida, vai para 0°, apagando o LED2 e acendendo o LED1.

O processo repete, criando um ciclo de LEDs sincronizado com o movimento do servo.

Esse teste mostra como controlar atuadores (servo) e saídas digitais (LEDs) em conjunto.
](https://github.com/user-attachments/assets/60e7ce62-9ebc-4083-9904-0d9d1ec1c187

📋 Descrição
Projeto que demonstra o controle simultâneo de um servo motor e LEDs com ESP32, criando um ciclo sincronizado entre movimento e iluminação.

📦 Materiais Necessários
1x ESP32

1x Servo motor (ex.: SG90)

3x LEDs (vermelho, amarelo, verde)

3x Resistores (220 Ω ou 330 Ω)

Jumpers

Protoboard

🔌 Ligações
Servo Motor
Fio laranja (sinal) → Pino 19 do ESP32

Fio vermelho (VCC) → 3.3V ou 5V

Fio marrom (GND) → GND

LEDs
LED1 → Pino 2 (com resistor em série)

LED2 → Pino 4 (com resistor em série)

LED3 → Pino 18 (com resistor em série)

📜 Código
cpp
#include <ESP32Servo.h>
#include <Arduino.h>

Servo meuMotor;

// Definição dos pinos
const int LED1 = 2;
const int LED2 = 4;
const int LED3 = 18;
const int SERVO = 19;

void setup() {
  // Configuração do servo
  meuMotor.attach(SERVO);
  meuMotor.write(0);

  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
}

void loop() {
  meuMotor.write(180);
  delay(1000);
  digitalWrite(LED3, HIGH);

  meuMotor.write(90);
  digitalWrite(LED3, LOW);
  digitalWrite(LED2, HIGH);
  delay(1000);

  meuMotor.write(0);
  digitalWrite(LED2, LOW);
  digitalWrite(LED1, HIGH);
  delay(1000);

  meuMotor.write(90);
  digitalWrite(LED1, LOW);
  digitalWrite(LED2, HIGH);
  delay(1000);

  meuMotor.write(180);
  digitalWrite(LED2, LOW);
  digitalWrite(LED3, HIGH);
  delay(1000);
}
▶️ Funcionamento
O servo inicia em 0° e executa movimentos sequenciais para 180°, 90° e 0°, acionando os LEDs em sincronia com cada posição. O ciclo se repete continuamente, demonstrando o controle simultâneo de atuadores e saídas digitais.)
