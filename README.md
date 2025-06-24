# Gesture-Controlled Game Automation using OpenCV & MediaPipe

This project enables gesture-based control for games or applications on Windows by simulating keyboard key presses using computer vision. It uses OpenCV and MediaPipe to detect hand landmarks from a webcam feed and simulates arrow key inputs using the Windows API via `ctypes`.

## 🎮 Features

- 👋 Hand gesture detection using MediaPipe.
- 🧠 Interprets open/closed fingers to perform actions.
- ⌨️ Simulates keypresses using low-level Windows `SendInput` function.
- ✅ Gesture-based "Accelerator" and "Brake" simulation.
- 💡 Works with any Windows-based application that supports keyboard input.

## 🛠️ Technologies Used

- Python 3
- OpenCV
- MediaPipe
- ctypes (Windows-only keyboard simulation)

## 🖐️ Gesture Mapping

| Fingers Shown | Action       | Description                        |
|---------------|--------------|------------------------------------|
| 0 (Fist)      | Brake        | Simulates pressing brake key (`K`) |
| 5 (Open Hand) | Accelerate   | Simulates pressing gas key (`M`)   |

## 📂 Project Structure

```plaintext
.
├── directkeys.py       # Contains the low-level keyboard simulation logic
├── gesture_control.py  # Main script for hand tracking and gesture interpretation
└── README.md           # Project documentation
````

## 🚀 Getting Started

### Prerequisites

* Python 3.7 or above
* Windows OS (due to `ctypes.windll` usage)

### Install Dependencies

```bash
pip install opencv-python mediapipe
```

### Run the Application

```bash
python gesture_control.py
```

### Exit the App

Press `q` to exit the webcam window and release all keys.

## 📌 Notes

* Make sure the webcam is functional and not being used by another application.
* This project currently supports only Windows because it uses Windows API (`SendInput`) for simulating keyboard events.
* Use in a well-lit environment for accurate hand tracking.

## 🧠 How It Works

1. Initializes MediaPipe Hand Tracking.
2. Captures real-time webcam input.
3. Identifies the number of fingers shown.
4. If all fingers are open: Simulate **Gas** (`M` key).
5. If all fingers are closed: Simulate **Brake** (`K` key).
6. Releases keys when hand is in neutral or invalid gesture.

## 📷 Example (Optional)

You can include screenshots or a demo GIF here showing hand gestures controlling a game like Angry Birds or a racing simulator.

## 📄 License

This project is licensed under the MIT License.

---

> **Disclaimer**: This project is for educational purposes only. Use responsibly and ensure compliance with the terms of any third-party games or software.

```
