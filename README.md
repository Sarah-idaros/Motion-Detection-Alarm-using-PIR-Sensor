# Motion-Detection-Alarm-using-PIR-Sensor

This project demonstrates a simple motion detection alarm system. When the PIR sensor detects motion, the system turns on an LED and a buzzer for a short period to indicate movement.


---

🧰 Components Used

Arduino board (Uno, Nano, etc.)

PIR Motion Sensor

LED

220Ω Resistor

Active Buzzer

Breadboard

Jumper wires



---

⚡ Wiring Guide

Component	Arduino Pin	Description

PIR Sensor VCC	5V	Power supply
PIR Sensor GND	GND	Ground
PIR Sensor OUT	D2	Motion detection signal
LED Anode (+)	D3 via 220Ω	Connect through a 220Ω resistor
LED Cathode (-)	GND	Ground
Buzzer (+)	D4	Buzzer control signal
Buzzer (-)	GND	Ground


> 💡 Note: Use a 220Ω resistor in series with the LED anode.




---

🖼 Circuit Diagram


![Circuit Diagram](./motion-alarm-circuit.png)


---

🧾 Arduino Code

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
    delay(2000); // Keep alarm on for 2 seconds
  } else {
    digitalWrite(ledPin, LOW);
    digitalWrite(buzzerPin, LOW);
  }

  delay(100);
}


---

▶ How to Use

1. Build the circuit using the wiring table above.


2. Upload the provided code to your Arduino.


3. Open the Serial Monitor to observe motion logs.


4. When motion is detected, the LED and buzzer turn on for 2 seconds.




