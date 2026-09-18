# lung-on-chip-comsol
Computational investigation of porous respiratory membrane and mucus layer effects on oxygen transport in a lung-on-a-chip using COMSOL Multiphysics
# Computational Investigation of Porous Respiratory Membrane and 
# Mucus Layer Effects on Oxygen Transport in a Lung-on-a-Chip

## Overview

This repository contains the computational model, results, and documentation 
for my undergraduate research project on **lung-on-a-chip simulation using 
COMSOL Multiphysics 6.2**. The project was conducted at the Department of 
Chemical and Petroleum Engineering, Sharif University of Technology.

## Research Objective

To investigate the effect of **respiratory membrane porosity** on oxygen 
diffusion using the **Bruggeman effective medium model**, and to evaluate 
the role of **mucus layer thickness** as an additional barrier in diseased 
lungs.

## Research Gap

Previous lung-on-a-chip studies (Jafarzadeh et al., 2019; Sarami Foroushani 
et al., 2024) treated the respiratory membrane as a **permeable but non-porous** 
barrier with constant diffusivity. This ignores the pore structure and 
tortuosity effects that govern real oxygen transport.


### Geometry
- 3-channel microfluidic setup: air channel, respiratory membrane, blood channel
- Channel dimensions: 150 μm (L) × 27 μm (W) × 14(air)/10(blood) μm (H)
- Membrane thickness: 1.11 μm
- Mucus layer (unhealthy model): 1.11–5.55 μm

### Physics
- **Laminar Flow** (Navier-Stokes, continuity)
- **Transport of Diluted Species** (convection-diffusion)
- **Porous Media** (Bruggeman effective medium approximation)

### Key Equations
- Bruggeman model: D_eff / D_0 = ε^1.5
- Tortuosity: τ = ε^(-1/2)
- Henry's Law for boundary conditions
- Oxygen-hemoglobin binding curve

### Software
- COMSOL Multiphysics 6.2
- 3D simulation
- Blood modeled as Newtonian (<1% difference vs non-Newtonian)

## Key Findings

| Condition | Result |
|-----------|--------|
| Healthy, no porosity | Blood saturated after 48 μm |
| Healthy, with porosity (ε=80%) | Blood saturated after 32 μm |
| Porosity effect | **+69.4% oxygen diffusion** |
| Mucus (5.55 μm) + porosity | **−85.3% oxygen transport** |
| Mucus + porosity combined | All porosity models converge → **mucus dominates** |

### Validation
The logarithmic relationship between mucus thickness and oxygen concentration 
agrees with experimental data from Worlitzsch et al. (2002) on cystic 
fibrosis patients.

## Limitations

- Bruggeman model assumes random isotropic spherical/cylindrical pores
- Does not account for particle shape, anisotropy, or complex pore networks
- Restrictive effects not included → may overestimate D_eff at low porosity
- Single alveolus model, not full lung

## Future Work

- Coupled mechanical breathing motion
- Extension to full alveolar-capillary network
