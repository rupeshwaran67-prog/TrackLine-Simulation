# FSAE Composite Tubular Spar Benchmark — ANSYS ACP & Structural Validation

End-to-end composite design, advanced laminate definition via ANSYS ACP, and multi-axial structural FEA validation of a tubular carbon-fiber spar featuring an integrated metallic end-fitting, representing the core structural methodology of a Formula Student suspension A-arm.

---

##  Toolchain & Specifications
* **CAD & Modeling:** SolidWorks / CATIA V5 (Mid-surface shell representation & solid metallic insert)
* **Pre-Processing & Layup:** ANSYS ACP-Pre (Composite PrepPost), Tubular Mapping, Oriented Selection Sets (OSS)
* **Structural Solver:** ANSYS Mechanical (Bonded contact mechanics, static multi-axial loading)
* **Failure Criteria:** Puck & Hashin Advanced Failure Theories
* **Domain:** Formula Student (FSAE) / Advanced Composite Suspension Hardware

---

## Methodology & Workflow

1. **Geometry Preparation (CAD):** Modeled a clean hollow circular tube (300 mm length, 40 mm outer diameter) extracted as a mid-surface shell, paired with a 3D solid aluminum end-fitting sleeve (50 mm length) to replicate realistic rod-end joint interfaces found in suspension wishbones.
2. **Material Property Definition:** Defined orthotropic material parameters for high-modulus carbon fiber prepreg ($E_1 = 135\text{ GPa}$, $E_2 = 10\text{ GPa}$) and isotropic properties for the aluminum insert ($E = 70\text{ GPa}$).
3. **Composite Layup (ANSYS ACP):** Built a symmetric 12-ply hybrid schedule ($[\pm 45^\circ / 0^\circ_2 / 90^\circ / \pm 45^\circ]_s$, total thickness = 1.5 mm). Outer $\pm 45^\circ$ plies manage torsional shear, interior $0^\circ$ plies handle longitudinal bending, and $90^\circ$ hoop plies resist radial deformation. Tubular mapping workflows were utilized to ensure smooth fiber continuity across complex 3D profiles.
4. **Boundary Conditions & Contact Mechanics:** Applied a fixed constraint ($X, Y, Z, \text{Rotation} = 0$) to the base of the solid metal insert and introduced a transverse/axial point load at the free end of the composite tube, utilizing bonded contact interfaces between the metal outer diameter and composite inner shell wall.
5. **Failure Analysis Post-Processing:** Evaluated structural integrity using **Hashin** and **Puck** failure criteria to map fiber tension/compression, matrix distress, and reserve factor margins across individual plies.

---

##  Related Portfolio Work
* [fsae-topology-optimization](https://github.com/rupeshwaran67-prog) — SOLIDWORKS Topology Optimisation of a three-point suspension link.
* [fsae-suspension-fatigue-analysis](https://github.com/rupeshwaran67-prog) — Static structural and fatigue analysis of suspension components (ANSYS Mechanical).

---

##  Author
**Rupeshwaran Paranthaman**  
* MSc Automotive Engineering, University of Hertfordshire
* Composite Design Lead & Crash Test Engineer, UH Racing Autonomous (Formula Student)  
[GitHub Profile](https://github.com/rupeshwaran67-prog)
