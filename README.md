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
