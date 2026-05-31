# 📡 WiFi Radar

A real-time WiFi network visualizer built with Python and Pygame.
Displays nearby networks on a radar-style interface — stronger signals appear closer to the center.

---

## 🚀 Features

- Scans all nearby WiFi networks in real time (Windows)
- Signal strength mapped to radar distance
- Auto-deduplicates networks (keeps strongest signal)
- Falls back to demo data on non-Windows systems
- Runs at 60 FPS with smooth sweep animation

---

## 🛠️ Requirements

- Python 3.x
- Pygame

Install dependencies:

pip install pygame

---

## ▶️ How to Run

python wifi_radar.py

> **Note:** On Windows, run as Administrator for full WiFi scan access.
> On Linux/Mac, demo mode activates automatically.

---

## 📁 Project Structure

wifi-radar/
│
├── wifi_radar.py      # Main application
└── README.md          # Project documentation

---

## 🧠 How It Works

| Component | Description |
|---|---|
| `get_WiFi_data()` | Calls `netsh` to fetch nearby SSIDs and signal strength |
| `generate_positions()` | Maps signal % to polar coordinates on the radar |
| Main loop | Draws rings, sweep line, and network dots at 60 FPS |

Signal → Distance formula: `distance = (100 - signal) * 2.5`

---

## ⚠️ Known Limitations

- Windows only for live scanning (`netsh` command)
- SSID parser may catch the header line `SSID count` — minor edge case
- Networks are plotted at fixed positions (no real directional data)
