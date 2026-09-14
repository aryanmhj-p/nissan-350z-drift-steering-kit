# Modular High-Angle Steering Kit with Adjustable Ackermann (Nissan 350Z)

[![SolidWorks](https://img.shields.io/badge/CAD-SolidWorks-red.svg)](#)
[![Geomagic](https://img.shields.io/badge/Mesh_Processing-Geomagic_Design_X-blue.svg)](#)
[![CarSim](https://img.shields.io/badge/Simulation-CarSim-darkblue.svg)](#)
[![Vehicle Dynamics](https://img.shields.io/badge/Dynamics-Bicycle_Model_%26_CarSim-orange.svg)](#)

A chassis engineering and vehicle dynamics project focused on point-cloud processing, kinematic synthesis, 3D CAD modeling, and multi-body dynamic simulation of a modular high-angle drift steering kit on a Nissan 350Z platform.

---

## 📌 Project Highlights & Core Contributions

- **Kinematic Synthesis & CAD Modeling:** Reconstructed the steering knuckle geometry from processed 3D scan data and engineered a bolt-on high-angle adapter in SolidWorks, achieving **$41^\circ$** steering lock (OEM ~32–35°).
- **Adjustable Ackermann Mechanism:** Designed a modular obround-slot mechanism with interchangeable inserts to achieve **Parallel ($\Delta\delta \approx 0$) and Slight Reverse Ackermann ($\Delta\delta < 0$)** steering characteristics.
- **Crossmember Relocation Design:** Re-engineered the front subframe/crossmember bracket in CAD to reposition the steering rack forward, resolving tie-rod over-centering and steering bind at extreme lock.
- **CarSim Dynamic Evaluation:** Modeled and simulated vehicle behavior on a 10 m radius skidpad (100% throttle / 2nd gear / locked differential), demonstrating that **Reverse Ackermann provides superior path tracking and minimized sideslip angle ($\beta$) oscillations**.
- **Geometric Analysis & Verification:** Validated the kinematics on the assembled chassis, confirming **$\delta_i = 38^\circ$, $\delta_o = 41^\circ$, and $\Delta\delta = -3^\circ$ (Slight Reverse Ackermann)**.

---

## 🔬 Vehicle Dynamics Theory for Drifting

In steady-state drift maneuvers, the vehicle operates under controlled, continuous oversteer where the rear tire slip angle exceeds the front ($\alpha_r > \alpha_f$) at a non-zero vehicle sideslip angle ($\beta \neq 0$):

$$\delta = \frac{L}{R} + \alpha_f - \alpha_r$$

$$\alpha_r > \alpha_f \implies \delta < 0 \quad \text{(Countersteer)}$$

### Why High Angle & Non-Positive Ackermann?
1. **Extended Controllability Range:** Higher steering angle broadens the operational countersteering window before spin-out occurs.
2. **Minimizing Front Tire Scrub:** Conventional positive Ackermann causes excessive scrub and unpredictable lateral force drop-off under high slip angles. Tuning towards **parallel or slight reverse Ackermann ($\Delta\delta \le 0$)** ensures both front tires operate efficiently within the lateral friction limit ($F_y \le \mu F_z$).

---

## ⚙️ Engineering & Development Workflow
