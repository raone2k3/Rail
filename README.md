# RailGuard — mmWave Radar-Based Railway Track Displacement Detection System

## Overview
RailGuard is a hardware system designed to detect railway track misalignment caused by thermal stress, using a millimeter-wave (mmWave) radar sensor for real-time, non-contact displacement monitoring. Continuously welded rails can buckle or fracture under temperature-driven expansion and contraction, and conventional monitoring methods (strain gauges, manual inspection) are slow, invasive, or reactive. RailGuard addresses this with contactless radar sensing and a live visualization interface.

## My Role: Hardware Design
I was responsible for the complete hardware layer of the system:
- Selecting and interfacing the mmWave sensor
- Ensuring stable, correctly wired power and data connections
- Producing full documentation of the interconnection design and every component used

## System Architecture
The TI IWR6843ISK mmWave sensor connects to a host laptop over USB, which supplies both 5V power and the data/flashing interface. The sensor, mounted on a tripod for stable positioning, emits a 60–64 GHz radar signal toward metal rod reflectors standing in for rail displacement points, calibrated at 18 cm from the board with 5 cm spacing between rods. Reflected signals return to the sensor and are processed by the host software stack for real-time visualization.

## Key Components
| Component | Role | Key Specification |
|---|---|---|
| TI IWR6843ISK | mmWave radar sensor, core detection unit | 60–64 GHz, 4 GHz bandwidth, integrated FFT/DSP |
| Tripod / fixed mount | Stable, repeatable radar positioning | Custom-aligned to target distance |
| Metal rods (reflectors) | Proxy targets simulating track displacement | Calibrated at 18 cm from board, 5 cm spacing |
| 5V power supply / USB | Powers the radar module | Delivered via USB from host |
| Laptop / PC | Flashing, visualization, debugging | Runs mmWave SDK + Demo Visualizer |
| 3D-printed casing | Protects and secures the sensor | Custom-designed enclosure |

## Configuration & Signal Parameters
The sensor configuration file was generated using the TI mmWave Sensing Estimator and validated through the mmWave Demo Visualizer, defining parameters for precise short-range displacement detection: operating frequency 60–64 GHz, 4 GHz bandwidth (~5 cm range resolution), 10 m maximum range, 12 dBm transmit power, and CFAR-based adaptive thresholding for stable static-target detection on rail surfaces.

## Documentation
Full hardware design and circuit documentation is available in this repository: [RailGuard_Hardware_Documentation.pdf](./RailGuard_Hardware_Documentation.pdf)

## Author
**Rehan Ahamed** — ECE Graduate, hardware & documentation specialist for embedded/ELV systems
