
---

```
┌───────────────────────────────────────────────────────────────┐
│                     🛰️ Benu Radar Scanning System              │
│                     Author: Benayas Wondwosen                 │
└───────────────────────────────────────────────────────────────┘
```

## 🧠 **Project Overview**

The **Benu Radar Scanning System** is a real-time ultrasonic radar visualizer built using **Arduino + Processing**.
The Arduino sweeps an ultrasonic sensor across a set angle range, sends distance readings to Processing, and Processing renders a live **military-style radar interface**.

**System Includes:**

* Continuous servo sweep *(15° → 165° → 15°)*
* Live ultrasonic distance measurement
* LED alert when object is close
* Full radar visual UI in Processing
* Real-time object detection + tracking

Perfect for security projects, robotics, mapping, and visualization learning.

---

```
┌───────────────────────────────────────────┐
│           ⚙️ Hardware Requirements         │
└───────────────────────────────────────────┘
```

* Arduino UNO / Nano / Mega
* HC-SR04 Ultrasonic Sensor
* SG90 / MG995 Servo Motor
* LED for alert (optional)
* Jumper wires
* USB cable
* Computer with Processing installed

---

```
┌───────────────────────────────────────────┐
│           🧠 Software Requirements         │
└───────────────────────────────────────────┘
```

### Processing

Uses built-in library:

* `processing.serial.*` (no installation needed)

### Arduino IDE

Libraries used (built-in):

* `Servo.h`

---

```
┌───────────────────────────────────────────┐
│                🔌 Arduino Setup            │
└───────────────────────────────────────────┘
```

**File:** `benu_radar_system.ino`
⚠️ *The code is already uploaded — no need to include it in the README.*
Just instruct users to **download it and upload to Arduino**.

**Steps:**

1. Download the Arduino file
2. Open with Arduino IDE
3. Select your board + COM port
4. Upload the sketch

---

```
┌───────────────────────────────────────────┐
│              🧩 Processing Setup           │
└───────────────────────────────────────────┘
```

**File:** `benu_radar_visualizer.pde`

Edit the COM port line to match your device:

```processing
myPort = new Serial(this, "COM9", 9600);
```

Then run the Processing sketch to start the radar interface.

---

```
┌───────────────────────────────────────────┐
│              🧪 Running the Project        │
└───────────────────────────────────────────┘
```

1. Connect Arduino via USB
2. Upload the Arduino sketch
3. Run the Processing program
4. Watch the radar animate 🎯

**You’ll see:**

* Rotating radar sweep line
* Green distance rings
* Red object detection points
* Live angle + distance readings
* Smooth animated interface

---

```
┌───────────────────────────────────────────┐
│              🧾 Features Summary           │
└───────────────────────────────────────────┘
```

| Feature                 | Description                   |
| ----------------------- | ----------------------------- |
| 🔄 Servo Sweep          | Automatic 15° → 165° scanning |
| 📡 Distance Measurement | Live ultrasonic readings      |
| 🖥️ Radar UI            | Processing visualization      |
| 🎯 Object Detection     | Detects objects < 40 cm       |
| 💡 LED Alert            | Faster blink = closer object  |
| ⚡ Real-Time             | Smooth serial + UI updates    |

---

```
┌───────────────────────────────────────────┐
│               🛠️ Troubleshooting           │
└───────────────────────────────────────────┘
```

**❌ Serial port not found**
✔ Change `"COM9"` to your actual port
✔ Close Arduino Serial Monitor

**❌ Radar not showing in Processing**
✔ Check Arduino is running
✔ Ensure baud rate = `9600`

**❌ Servo shaking**
✔ Use external 5V for servo
✔ Connect all grounds together

---

```
┌───────────────────────────────────────────────────────────┐
│        ❤️ Made by Benayas Wondwosen — Nafiyas Solution     │
│                Embedded Systems Division                   │
└───────────────────────────────────────────────────────────┘
```
