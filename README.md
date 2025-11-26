.

🛰️ Benu Radar Scanning System

👤 Author: Benayas Wondwosen

🧠 Project Overview

The Benu Radar Scanning System is a real-time ultrasonic radar visualizer built using Arduino and Processing.

The Arduino sweeps an ultrasonic sensor across an angle range and sends distance data to Processing, which renders a live animated radar UI similar to real military-style scanners.

The system performs:

Continuous servo sweep (15° → 165° → 15°)

Ultrasonic distance measurement

LED blinking alert when an object is close

Real-time radar visualization using Processing

Object detection and distance plotting

This project is perfect for robotics, security systems, mapping, and visualization learning.

⚙️ Hardware Requirements

Arduino UNO/Nano/Mega

HC-SR04 Ultrasonic Sensor

SG90/MG995 Servo Motor

LED (optional proximity alert)

Jumper wires

USB cable

PC with Processing installed

🧠 Software Requirements
Processing Libraries

Built-in libraries (no installation needed):

processing.serial.*

Arduino IDE

No extra libraries required except:

Servo.h (built-in)

🔌 Arduino Setup

File: benu_radar_system.ino

Upload this code to your Arduino:

#include <Servo.h>

const int trigPin = 10;
const int echoPin = 11;
const int ledPin = 9;

long duration;
int distance;
Servo myServo;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
  myServo.attach(12);
}

void loop() {
  for(int i = 15; i <= 165; i++) {
    myServo.write(i);
    delay(15);
    distance = calculateDistance();
    Serial.print(i);
    Serial.print(",");
    Serial.print(distance);
    Serial.print(".");
    blinkLED(distance);
  }

  for(int i = 165; i > 15; i--) {
    myServo.write(i);
    delay(15);
    distance = calculateDistance();
    Serial.print(i);
    Serial.print(",");
    Serial.print(distance);
    Serial.print(".");
    blinkLED(distance);
  }
}

int calculateDistance() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;
  return distance;
}

void blinkLED(int d) {
  if (d > 0 && d < 40) {
    int blinkDelay = map(d, 1, 40, 30, 300);
    digitalWrite(ledPin, HIGH);
    delay(blinkDelay);
    digitalWrite(ledPin, LOW);
    delay(blinkDelay);
  } else {
    digitalWrite(ledPin, LOW);
  }
}


✅ Upload using Arduino IDE
✅ Note your COM port (e.g., COM4 or COM9)

🧩 Processing Setup

File: benu_radar_visualizer.pde

Edit this line to match your COM port:

myPort = new Serial(this,"COM9", 9600);


Then run the Processing sketch.

🧪 Running the Project

Connect your Arduino via USB

Upload the Arduino sketch

Run the Processing program

Watch the radar come alive 🎯

You will see:

A rotating radar sweep line

Green distance rings

Detected objects marked in red

Live angle and distance data

Smooth animated UI

🧾 Features Summary
Feature	Description
🔄 Servo Sweep	Automated 15° → 165° scanning
📡 Distance Measurement	HC-SR04 live ultrasonic readings
🖥️ Radar UI	Processing-based visualization
🎯 Object Detection	Displays objects under 40 cm
💡 LED Alert	Blinks faster when objects are close
⚡ Real-Time	Smooth animation + live serial data
🛠️ Troubleshooting
❌ “Serial port not found”

✔ Change "COM9" to your port
✔ Close Arduino Serial Monitor

❌ Processing shows no radar

✔ Check Arduino is running
✔ Make sure baud is 9600

❌ Servo shaking or glitching

✔ Use external 5V supply
✔ Common ground required

❤️ Made by Benayas Wondwosen

🛠️ A project from Nafiyas Solution – Embedded Systems Division
