# Redesign of Ducati V4S Steering Plate for Additive Manufacturing


## 📖 Project Overview
This project presents a comprehensive feasibility study and re-design of the upper steering plate for the **Ducati V4 S (Superleggera)**. The primary objective was to transition from the traditional CNC subtractive manufacturing process (machined from an Anticorodal aluminum block) to an **Additive Manufacturing (AM)** workflow, specifically Laser Powder Bed Fusion (LPBF).

The study targets a production volume of **500 parts per year**, utilizing topology optimization to maximize stiffness while reducing mass compared to the original 400g component.

## 🎯 Objectives
* **Lightweighting:** Reduce component mass while maintaining structural integrity.
* **Material Analysis:** Compare the performance and feasibility of standard **AlSi10Mg** against high-performance **A20X** aluminum alloy.
* **Process Simulation:** Validate printability using the **EOS M 400-4** system.
* **Cost Analysis:** Assess the economic viability of AM compared to traditional methods.

## ⚙️ Methodology

### 1. Load Evaluation & Validation
Dynamic riding conditions were translated into static dimensioning load cases:
* **Braking:** Vertical force (980 N) and Longitudinal force (3800 N).
* **Cornering:** High lateral loads (1000 N) and vertical loads (1500 N) generating torsional stress.
* **Bump Impact:** High-magnitude impulsive forces simulated as static loads (6400 N vertical).
* **Bolt Pretension:** Modeled with 7000N tightening forces.

*A reverse engineering process validated these loads on the original CNC component using FEM analysis in Altair Hypermesh.*

### 2. Topology Optimization
Using **Altair Inspire**, the geometry was optimized to minimize mass with a safety factor constraint of **1.2**.
* **Design Space:** Original internal cutouts were filled to create a solid design volume.
* **Non-Design Space:** Critical interfaces (fork clamps, steering stem) were preserved with specific offsets (5mm for AlSi10Mg, 3mm for A20X).

### 3. Manufacturing Strategy (DfAM)
The simulation was set up for the **EOS M 400-4** (Quad-Laser) system.
* **Orientation:** Vertical alignment with a 5° tilt to optimize nesting (12 parts/job) and manage thermal stress.
* **Support Strategy:** Hybrid approach using solid supports for anchoring, tree supports for holes, and diamond patterns for overhangs.
* **Machining Allowance:** Added material (1.5mm) on clamping holes and reduced bolt hole diameters (to 5mm) for post-processing.

## 📊 Results

### Structural Performance
Both materials outperformed the original component in safety factors, but **A20X** offered superior weight reduction due to its higher yield strength ($R_{p0.2} > 400$ MPa).

| Metric | Original CNC | AlSi10Mg (AM) | A20X (AM) | Improvement (A20X) |
| :--- | :--- | :--- | :--- | :--- |
| **Mass** | 434g | 340g | **268g** | **-38%** |
| **Braking S.F.** | 1.1 | 1.9 | **1.6** | +45% |
| **Cornering S.F.** | 1.0 | 1.7 | **2.3** | +130% |



### Process Simulation (Inherent Strain)
Simulations confirmed printability for both materials with peak residual stresses (~204 MPa) remaining below the yield threshold, ensuring no cracking or excessive distortion.

### 💰 Cost Analysis
The economic analysis revealed a counter-intuitive result where the high-performance material was cheaper to produce.

| Material | Cost Per Part | Explanation |
| :--- | :--- | :--- |
| **AlSi10Mg** | €605.18 | Standard material cost, but larger printed volume. |
| **A20X** | **€595.31** | Higher powder cost is offset by **reduced print time** (-2 hours) due to significant volume reduction via optimization. |

**Conclusion:** A20X is the superior choice, offering a lighter component at a lower unit cost.

## 🛠️ Tools & Software Used
* **Altair Hypermesh:** FEM Analysis & Load Validation.
* **Altair Inspire:** Topology Optimization & PolyNURBS fitting.
* **Altair Inspire Print Analysis:** AM Process Simulation (Inherent Strain Method).
* **SolidWorks:** Geometry finishing and CAD reconstruction.

