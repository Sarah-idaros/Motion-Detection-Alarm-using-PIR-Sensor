# Motion-Detection-Alarm-using-PIR-Sensor

This project demonstrates a simple motion detection alarm system using a PIR sensor, an LED, and a buzzer. When motion is detected, the LED and buzzer are activated for 2 seconds to indicate movement.

🔧 Components Used

Arduino (Uno, Nano, etc.)
PIR Motion Sensor
LED
220Ω Resistor
Buzzer (active)
Jumper wires
Breadboard

🛠 Circuit Diagram

![Circuit Diagram](./motion-alarm-circuit.png)

🔌 Wiring

Component	Arduino Pin	Description

PIR Sensor VCC	5V	Power supply
PIR Sensor GND	GND	Ground
PIR Sensor OUT	D2	Signal output
LED Anode (+)	D3 via resistor	LED positive through resistor
LED Cathode (-)	GND	LED negative to ground
Buzzer (+)	D4	Buzzer signal pin
Buzzer (-)	GND	Buzzer ground


> Resistor (220Ω) should be placed between LED anode and Arduino pin D3.



📝 Code

int pirPin = 2;       // PIR sensor connected to digital pin 2
int ledPin = 3;       // LED connected to digital pin 3
int buzzerPin = 4;    // Buzzer connected to digital pin 4

void setup() {
  pinMode(pirPin, INPUT);
  pinMode(ledPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int motion = digitalRead(pirPin);

  if (motion == HIGH) {
    Serial.println("Motion Detected!");
    digitalWrite(ledPin, HIGH);
    digitalWrite(buzzerPin, HIGH);
    delay(2000); // Alarm duration (2 seconds)
  } else {
    digitalWrite(ledPin, LOW);
    digitalWrite(buzzerPin, LOW);
  }

  delay(100);
}

📁 How to Use

1. Connect the PIR sensor, LED, and buzzer according to the wiring table above.
2. Upload the code to your Arduino board.
3. Open the Serial Monitor to view motion detection logs.
4. When motion is detected, the LED and buzzer will activate for 2 seconds.

