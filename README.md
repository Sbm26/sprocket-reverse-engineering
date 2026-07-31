# sprocket-reverse-engineering
# ⚙️ Industrial 14-Tooth Sprocket Reverse Engineering & DFM Workflow

> **Project Type:** Component Reverse Engineering + Technical Proposal   
> **Tools:** SolidWorks, GearTrax  
> **Manufacturing Processes:** CNC Lathe Turning, Gear Hobbing (Tooth Cutting), Induction Hardening  

---

## Project Overview
A client supplied a worn drive sprocket requesting reverse engineering and replacement. With no original engineering drawings/models or matching chain specifications provided initially

---

## 🔬 Reverse Engineering

### 1. Pitch Estimation & Chain Identification
* **Initial Surface Condition:** Severe tooth flank erosion rendered direct pitch measurements unreliable (initial rough estimates yielded $\approx 56\text{ mm}$ pitch).
* **Chain Size Verification:** Multiple standard industrial chains were test-fit against the component. The sprocket was conclusively identified as an **ANSI #160 (2.0-inch / 50.8 mm pitch)** standard profile featuring a **$20\text{ mm}$ pin diameter**
* PS: The correspondent ISO standard would be ISO 606 I believe

### 2. Mathematical Back-Calculation
Using standard ANSI B29.1 formulas for a **14-tooth ($N = 14$)** sprocket, the Pitch Circle Diameter ($PCD$) and root radii were established:

$$PCD = \frac{P}{\sin\left(\frac{180^\circ}{N}\right)} = \frac{50.8\text{ mm}}{\sin\left(\frac{180^\circ}{14}\right)} \approx 228.48\text{ mm}$$

### 3. Physical Validation
To de-risk manufacturing before committing to material procurement, a physical sample segment of #160 industrial chain was requested from the client and manually verified against the reconstructed tooth profile to ensure zero binding and smooth roller seating.

---

## 💻 3D CAD Modeling (SolidWorks + GearTrax)

Using calculated parameters, **GearTrax** generated the exact ANSI standard tooth geometry, exported directly into **SolidWorks** (`.GTX` format) for final detailing.



## 🛠️ DFM & Production Workflow

The CAD model serves as the master specification for the complete 5-step manufacturing lifecycle:

```text
  [1] Stock Procurement ──► [2] CNC Lathe Turning ──► [3] Hobbing / Tooth Cutting
                                                                │
  [5] Client Delivery ◄── [4] Quality Control (QC) ◄── [3.5] Induction Hardening
