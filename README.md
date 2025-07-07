# 🤖 4-DOF Robotic Arm Controlled via ESP32 & Smartphone Browser

This project features a 4-degree-of-freedom (DOF) robotic arm controlled wirelessly using an ESP32 and a smartphone browser. It uses WebSocket-based real-time communication and offers both **manual control** and **record-playback functionality** via a custom-built web interface.

---

## 📹 Demonstration
👉 [Watch the demo video](demonstration%20video.mp4)

---

## 🔧 Features
- 📱 **Wireless control** using smartphone browser (no router required)
- 🎮 Sliders to control Base, Shoulder, Elbow, and Gripper in real-time
- 💾 **Recording & Playback** for repetitive tasks
- 🌐 ESP32 acts as both **Wi-Fi hotspot** and WebSocket server
- 📡 Real-time servo angle updates using WebSocket

---

## 🛠️ Hardware Used
| Component                  | Description                              |
|---------------------------|------------------------------------------|
| ESP32 Dev Board           | Microcontroller with built-in Wi-Fi      |
| SG90 Servo Motors (x4)    | For joint movement                       |
| External 5V Power Supply  | Required to drive all servo motors       |
| Breadboard + Jumper Wires | For wiring connections                   |
| Smartphone or PC Browser  | For web-based control interface          |

---

## 🔌 Circuit Diagram

![Circuit Diagram](Circuit%20Diagram.png)

---

## 💻 Arduino IDE Setup Instructions

### 1️⃣ Install Arduino IDE
- Download from the official site: https://www.arduino.cc/en/software

### 2️⃣ Install ESP32 Board in Arduino IDE
1. Go to: `File` → `Preferences`
2. In **Additional Board URLs**, paste this:  
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
3. Go to `Tools` → `Board` → `Boards Manager`
4. Search **ESP32** → Click **Install**

---

### 3️⃣ Install Required Libraries

#### 🔹 (A) ESPAsyncWebServer & AsyncTCP
- Extract the following ZIPs and place them in `Documents/Arduino/libraries/`:
- [`ESPAsyncWebServer-master.zip`](ESPAsyncWebServer-master.zip)
- [`AsyncTCP-master.zip`](AsyncTCP-master.zip)

#### 🔹 (B) ESP32Servo Library
- Go to `Sketch` → `Include Library` → `Manage Libraries`
- Search for **ESP32Servo** and install it.

---

### 4️⃣ Upload the Code
- Open `Robotic_arm.ino` in Arduino IDE
- Select board: `ESP32 Dev Module` from `Tools > Board`
- Select correct COM port
- Click `Upload`

---

### 5️⃣ Run the Project

1. After upload, the ESP32 creates a Wi-Fi hotspot named:
SSID: RobotArm
Password: 12345678
2. Connect your smartphone/PC to this Wi-Fi
3. Open browser and go to: `192.168.4.1`
4. Use the sliders to move servos in real-time
5. Press **Record** to capture motion → **Play** to replay

---

## 📁 Project Structure

| File                            | Description                                           |
|--------------------------------|-------------------------------------------------------|
| `Robotic_arm.ino`              | Main Arduino code (ESP32 with Web UI & control logic) |
| `Circuit Diagram.png`          | Visual wiring diagram of servos and ESP32             |
| `image.jpg`                    | UI or setup image (optional use)                      |
| `demonstration video.mp4`      | Project working demo                                  |
| `ESPAsyncWebServer-master.zip` | Required Arduino library (include in `libraries/`)    |
| `AsyncTCP-master.zip`          | Dependency library for ESPAsyncWebServer              |
| `README.md`                    | Project overview and documentation                    |

---

## 💡 How Recording Works

- Press `Record` → Move servos → Press `Stop`
- Press `Play` to replay the exact recorded steps
- Uses timing logic (in milliseconds) to mimic human interaction

---

## 🌍 Real-World Applications

- Industrial pick-and-place tasks
- Educational tool for robotics learning
- DIY home automation arms
- Simulated control logic for larger robotic systems

---

## 🚀 Future Improvements
- Save recording to SD card in CSV format
- Add voice command control using Google Assistant/Bluetooth
- Integrate camera for object tracking
- 6-DOF upgrade with inverse kinematics

---

## 👩‍💻 Developed By

**Shreya Dandale**  
Final Year B.Tech Student – Electronics & Telecommunication  
JSPM RSCOE, Pune
