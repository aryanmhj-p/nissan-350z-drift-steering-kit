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

### 1. Reverse Engineering & Point Cloud Processing
- Processed the raw optical 3D scan data of the factory Nissan 350Z aluminum upright in **Geomagic Design X**.
- Cleaned point clouds, extracted critical mounting surfaces, ball joint centers, and the kingpin axis.
- Reconstructed reference datums and interface features in **SolidWorks** to ensure 100% bolt-on compatibility with OEM suspension components.

### 2. Kinematic Synthesis & Mechanism Design
- **Shorter Steering Arm:** Reduced tie-rod pickup radius ($r_{modified} < r_{OEM}$) to maximize lock per rack stroke, while accounting for increased tie-rod load ($M = F \cdot r$).
- **Obround Modular Slot:** Designed a rotating insert mounted on the steering bracket, allowing continuous tuning of the tie-rod pickup point relative to the kingpin axis.
- **Design for Manufacturing (DFM):** Prepared flat-pattern DXF layouts for laser cutting, bend allowances for CNC press brakes, and dimensional tolerances for CNC turning/milling.

### 3. Steering Rack Relocation Modeling
- Redesigned the crossmember mounting interfaces to shift the steering rack forward, eliminating the risk of tie-rod over-centering (steering bind) at $41^\circ$ lock.

---

## 📊 CarSim Dynamic Simulation

A Nissan 350Z model was simulated on a **10-meter radius circular skidpad** (2nd gear, 100% throttle, locked differential) to evaluate the dynamic impact of Ackermann variation:

| Parameter | Conventional Ackermann | Parallel Steering ($\Delta\delta = 0$) | Reverse Ackermann ($\Delta\delta < 0$) |
| :--- | :---: | :---: | :---: |
| **Trajectory Tracking** | Moderate drift-off | Least stable path maintenance | **Best path adherence & circular stability** |
| **Vehicle Sideslip ($\beta$)** | Notable oscillation | Severe lateral fluctuations | **Smoothest & lowest variation** |
| **Yaw Rate ($r$) Stability** | Intermediate spikes | Highly erratic fluctuations | **Consistent, dampened response** |
| **Steering Torque Demand** | Highest driver effort | Medium | **Optimal & predictable countersteer torque** |

---

## 🛠️ Chassis Geometric Verification

The design was fitted onto a stripped Nissan 350Z test chassis to verify kinematic lock and clearance:
- **Measured Passenger Wheel Angle ($\delta_i$):** $38^\circ$
- **Measured Driver Wheel Angle ($\delta_o$):** $41^\circ$
- **Ackermann Difference ($\Delta\delta$):** $-3^\circ$ (Validated Slight Reverse Ackermann)
- **Kinematic Check:** Verified clearance across full suspension travel and steering sweep with zero mechanical bind.

---

## 👥 Roles & Contributions

- **Aryan Mahjoubi:** Point cloud processing (Geomagic), kinematic synthesis & CAD modeling (SolidWorks), subframe relocation modeling, DFM specifications, CarSim vehicle dynamics simulations, and geometric kinematic verification.
- **Alireza Ostadi:** Part fabrication, workshop machining, chassis integration, and physical assembly.
- **External Support:** Optical 3D scanning of the OEM knuckle.
- **Academic Supervisor:** Dr. Saadat Foomani *(Department of Mechanical Engineering, Sharif University of Technology)*
