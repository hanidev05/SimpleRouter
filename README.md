#  Simple Router Simulation (M/M/1 & M/M/1/K)

## Project Overview

This console-based project simulates packet transmission in a **single-router system** modeled as a queuing system.

The simulation includes two queueing models:

- **M/M/1** → Infinite buffer capacity  
- **M/M/1/K** → Finite buffer capacity (packet dropping enabled)

Packet arrivals follow a **Poisson process**, which realistically approximates random traffic behavior in communication networks.

The project analyzes system behavior under both:

- **Stable conditions (ρ < 1)**
- **Congested conditions (ρ ≥ 1)**

---

## System Model

The router is modeled as:

- A single server  
- Exponentially distributed inter-arrival times  
- Exponentially distributed service times  
- Optional finite buffer  

When the buffer is full in the **M/M/1/K** model:

> Incoming packets are dropped.

---

## Computed Metrics

The simulation calculates and displays:

- Transmission Delay  
- Propagation Delay  
- Traffic Intensity (ρ)  
- Average Queue Delay  
- Queue Length  
- Number of Dropped Packets  

The results are visualized and stored in the `Images/` folder.

---

##  Mathematical Definitions

### Transmission Delay
D_trans = L/R

### Propagation Delay
D_prop = d/s

### Traffic Intensity
ρ = lambda* L/R

---

## Parameters

| Parameter | Description |
|-----------|------------|
| **L** | Packet size (bits) |
| **R** | Transmission rate (bits/sec) |
| **d** | Distance between nodes (meters) |
| **s** | Propagation speed (m/s) |
| **λ (lambda)** | Packet arrival rate (packets/sec) |
| **K** | Buffer capacity (finite queue size) |

---

##  Project Structure
SimpleRouter/
-delay.py
-Images/
- `delay.py` → Main simulation script  
- `Images/` → Generated graphs and simulation results  

---

##  How to Run

1. Open the project folder
2. Run the script:
python delay.py


3. The simulation results and plots will be generated automatically.

---

## Simulation Insights

- If **ρ < 1** → The system is stable  
- If **ρ ≥ 1** → The queue grows (congestion)  
- In finite buffer mode → Packet dropping occurs when the buffer is full  

This project demonstrates the difference between theoretical infinite-buffer systems and practical finite-buffer router implementations.
