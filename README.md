# FSAE Composite Tubular Spar Benchmark — ANSYS ACP & Structural FEA

A composite structural analysis benchmark inspired by Formula Student suspension hardware, investigating carbon-fibre laminate design, tubular composite behaviour, metallic end-fitting load transfer, and ply-level failure assessment using ANSYS ACP and ANSYS Mechanical.

##  Tools & Technologies

- **CAD:** SOLIDWORKS / CATIA V5
- **Composite Pre-processing:** ANSYS ACP (Pre)
- **Structural Analysis:** ANSYS Mechanical
- **Composite Failure Assessment:** Hashin and Puck criteria, subject to solver capability
- **Engineering Methods:** Classical beam theory, mesh-convergence assessment, analytical-versus-FEA correlation

## Geometry & Design Specifications

- **Composite tube length:** 300 mm
- **Tube outer diameter:** 40 mm
- **Nominal laminate thickness:** 1.5 mm
- **Number of plies:** 12
- **Nominal individual ply thickness:** 0.125 mm
- **End-fitting material:** Aluminium
- **End-fitting sleeve length:** 50 mm

The composite tube is represented using a shell-based formulation, with a solid aluminium end-fitting to investigate load transfer between dissimilar structural materials.

##  Composite Laminate Definition

A symmetric 12-ply laminate is defined using the stacking sequence:

**[45° / −45° / 0° / 0° / 90° / 0°]s**

The intended functions of the ply orientations are:

- **0° plies:** Contribute to axial stiffness and bending resistance.
- **±45° plies:** Contribute to in-plane shear stiffness and torsional response.
- **90° plies:** Contribute to circumferential stiffness and resistance to cross-sectional deformation.

The laminate is defined in ANSYS ACP using appropriate material orientations and tubular mapping. The fibre coordinate system and stacking direction must be checked against the CAD geometry before interpreting the results.

## Structural Analysis Methodology

### 1. Geometry Preparation

Create the hollow composite tube and aluminium end-fitting in CAD. Prepare the geometry for shell-based composite modelling and define the interface between the composite tube and metallic insert.

### 2. Material Definition

Define orthotropic elastic properties for the carbon-fibre composite, including the required Poisson's ratios and shear moduli. Include relevant tensile and compressive strengths for failure assessment. Model the aluminium fitting using appropriate isotropic material properties.

### 3. ANSYS ACP Layup

Define the 12-ply symmetric laminate with a nominal total thickness of 1.5 mm. Verify the ply count, individual thicknesses, fibre orientations and material coordinate system before transferring the composite model to ANSYS Mechanical.

### 4. Isolated Structural Load Cases

**Load Case 1 — Cantilever Bending**

Apply a transverse tip load with a defined support condition. Compare the predicted tip displacement with classical Euler–Bernoulli beam theory:

δ = PL³ / (3EI)

Use a suitable effective bending stiffness for the composite tube and document the assumptions behind the analytical approximation.

**Load Case 2 — Torsion**

Apply a defined torque to investigate the torsional response, shear stresses and contribution of the ±45° laminate plies.

**Load Case 3 — Axial Loading**

Apply axial tension and compression to investigate longitudinal stiffness, deformation and load transfer near the metallic end-fitting.

### 5. Numerical Validation

Assess mesh sensitivity and compare analytical predictions with finite-element results under equivalent loading and boundary conditions. Review deformation, stress distributions, reaction forces and the sensitivity of results to modelling assumptions.

### 6. Composite Failure Assessment

Where supported by the implemented solver workflow, assess ply-level failure using Hashin and/or Puck criteria. Distinguish fibre-related failure from matrix or inter-fibre failure and report failure indices or reserve factors only when calculated from the model.

## Modelling Assumptions & Limitations

- The metallic insert-to-composite interface is initially represented using idealised bonded contact.
- Local adhesive peel stresses, pin-bearing failure and detailed joint damage require additional modelling.
- Fatigue, impact loading, manufacturing defects and experimental correlation are outside the initial benchmark scope.
- The model is a structural analysis study inspired by Formula Student hardware, not a production-ready or physically validated suspension component.

##  Planned Engineering Deliverables

- CAD geometry and engineering dimensions
- ANSYS ACP laminate definition and ply-orientation visualisations
- Mesh-convergence study
- Analytical-versus-FEA comparison
- Bending, torsion and axial deformation results
- Ply-level failure assessment, where implemented
- Engineering conclusions, assumptions and recommended next steps

##  Related Portfolio Projects

- **FSAE Topology Optimisation:** SOLIDWORKS-based topology optimisation of a suspension link.
- **FSAE Suspension Fatigue Analysis:** Structural and fatigue assessment of suspension components using ANSYS Mechanical.

Explore the associated projects on my [GitHub profile](https://github.com/rupeshwaran67-prog).

##  Author

**Rupeshwaran Paranthaman**

MSc Automotive Engineering — University of Hertfordshire

Composite Design Lead & Crash Test Engineer — UH Racing Autonomous (Formula Student)

**Project focus:** Composite structures, laminate design, finite-element analysis, structural validation and failure assessment.
