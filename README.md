# 🛠️ TinyWhoop ELRS Vision Bridge (In Progress)

A ground-station–only, AI-powered control system for **Tiny Whoop drones** using **analog FPV** video and **ExpressLRS (ELRS)** radio. This project aims to create a Python SDK and vision pipeline that allows drones to perform “follow-me” tasks — **without onboard compute** and **without ROS**.

> ⚠️ This project is under active development. We're starting with the ELRS → MAVLink bridge. Follow for monthly updates!

---

## 🎯 What We're Building

A lightweight system that:
- Captures analog FPV video via USB tuner
- Runs real-time object detection and tracking (YOLOv8 + DeepSORT)
- Computes RC control signals (via PID)
- Sends RC commands over **ELRS serial bridge**
- Operates **fully on the ground** with zero onboard intelligence

---

## ✅ Phase 1: ELRS Bridge SDK (🟢 In Progress)

We're currently building the core bridge that:
- Reads raw serial data from an ELRS receiver
- Parses channel values
- Sends them as `RC_CHANNELS_OVERRIDE` via MAVLink (soon)
- CLI-enabled for quick testing and integration

```bash
pip install -e .
elrs-bridge --port /dev/ttyUSB0
```

---

## 🔭 Roadmap

| Phase | Milestone | Status |
|-------|-----------|--------|
| 1     | ELRS Bridge (serial + MAVLink RC) | 🟢 In Progress |
| 2     | Analog video capture + YOLOv8 detector | ⏳ Planned |
| 3     | Object tracking (DeepSORT) + PID | ⏳ Planned |
| 4     | Integration with TinyWhoop + CLI SDK | ⏳ Planned |
| 5     | Docs, GitHub CI/CD, live demos | ⏳ Planned |

---

## 📦 Tech Stack

- `pyserial` — for ELRS serial I/O  
- `pymavlink` or `MAVSDK-Python` — for RC overrides  
- `opencv-python` + `ultralytics` — for vision (future)  
- `deep_sort_realtime` — for object tracking (future)  
- `asyncio` — for modular, event-driven control loop

---

## 🤔 Why Ground-Only?

- Keeps drones ultralight and power efficient  
- Supports analog FPV systems with zero onboard compute  
- Works with Tiny Whoops and budget drones  
- Ideal for inspection, surveillance, and creative use cases

---

## 💡 Example Use Case

Imagine a telecom technician climbing a tower with a Tiny Whoop that **automatically follows and livestreams**, spotting structural damage in real time—boosting safety, reducing inspection time by up to 40%, and creating new service revenue models.

No GPS. No heavy compute. Just analog vision + Python smarts.

---

## 🙌 Contributions Welcome

This project is in early development. Whether you're into FPV, embedded systems, AI vision, or clean Python code — you're invited!

📅 **Monthly updates will be posted here and on LinkedIn.**

📂 GitHub: [https://github.com/harittrivedi/ELRS_Offboard_autonomy]

🔁 Re-share if you're into FPV, embedded vision, MAVLink, or just creative drone engineering.

---

#FPV #ELRS #TinyWhoop #Python #DroneTech #ComputerVision #OpenSource #MadeInIndia
