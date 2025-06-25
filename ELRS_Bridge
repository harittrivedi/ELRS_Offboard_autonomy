## Project: TinyWhoop ELRS Bridge SDK

# Folder: elrs_bridge_sdk/

# elrs_bridge.py
import serial
import time

class ELRSBridge:
    def __init__(self, port='/dev/ttyUSB0', baudrate=460800):
        self.ser = serial.Serial(port, baudrate, timeout=0.1)

    def read_raw(self):
        if self.ser.in_waiting:
            data = self.ser.readline()
            print(f"[ELRS RAW] {data}")
            return data
        return None

    def close(self):
        self.ser.close()

# cli.py
import argparse
from elrs_bridge import ELRSBridge

def main():
    parser = argparse.ArgumentParser(description="ELRS Bridge CLI")
    parser.add_argument('--port', type=str, default='/dev/ttyUSB0')
    parser.add_argument('--baud', type=int, default=460800)
    args = parser.parse_args()

    bridge = ELRSBridge(port=args.port, baudrate=args.baud)
    print("[INFO] Reading ELRS data... Press Ctrl+C to stop.")
    try:
        while True:
            bridge.read_raw()
            time.sleep(0.05)
    except KeyboardInterrupt:
        print("\n[INFO] Stopping...")
        bridge.close()

if __name__ == '__main__':
    main()

# setup.py
from setuptools import setup, find_packages

setup(
    name='elrs_bridge_sdk',
    version='0.1.0',
    packages=find_packages(),
    entry_points={
        'console_scripts': [
            'elrs-bridge=cli:main'
        ]
    },
    install_requires=[
        'pyserial'
    ],
    author='YourName',
    description='ELRS Bridge SDK for TinyWhoop control',
    keywords='ELRS MAVLink Serial FPV Python',
)

# README.md
"""
# ELRS Bridge SDK for TinyWhoop

This is a lightweight Python SDK to interface with ELRS receivers via serial and stream RC channel values to your ground station software. Designed for analog FPV drones (e.g. Tiny Whoop), this is the starting point for AI-augmented follow-me features.

## Features
- Read raw ELRS UART data
- Ready for RC_CHANNELS_OVERRIDE integration (MAVLink or MAVSDK)
- Modular and easy to extend

## Usage
```bash
pip install -e .
elrs-bridge --port /dev/ttyUSB0
```

## Dependencies
- Python 3.10+
- pyserial

## Roadmap
- [x] Raw UART read
- [ ] Parse and interpret channel data
- [ ] Integrate with MAVLink override
- [ ] Full AI-driven flight logic

"""
