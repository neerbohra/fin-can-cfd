# Fin can aerodynamics: CFD study

A parametric rocket fin can designed in Fusion and tested in CFD (SimScale), comparing drag for three fin designs after validating the setup against textbook cases.

**Status:** in progress (Oct - Nov 2026)
**Skills:** Fusion (parametric modelling), SimScale CFD (meshing, boundary conditions, k-omega SST), validation against hand calculations, mesh-independence study

---

## Question

How do fin count and fin shape change the drag of a small rocket body at 40 m/s?

## Why the validation cases come first

A CFD result is only believable if the same setup gets known answers right. So before the fin can:

| Case | Known answer | My CFD result | Error |
|---|---|---|---|
| Laminar pipe flow (Hagen-Poiseuille pressure drop) | dP = 32 mu L V / D^2 | | |
| Flow past a cylinder, Re = 20 | Cd about 2.0 | | |

### Mesh independence (cylinder)

| Mesh | Cells | Cd |
|---|---|---|
| Coarse | | |
| Medium | | |
| Fine | | |

## Fin can setup

| Setting | Value |
|---|---|
| Geometry | Fusion parametric model, exported as STEP |
| Domain | |
| Inlet speed | 40 m/s (well under Mach 0.3, so incompressible) |
| Turbulence model | k-omega SST |
| Mesh | |
| Convergence check | Residuals flat + drag force steady |

## Results

Cd = 2F / (rho V^2 A), with A = the body tube's frontal area.

| Design | Drag force (N) | Cd | Change vs body only |
|---|---|---|---|
| Body only | | | - |
| 3 fins | | | |
| 4 fins | | | |
| Alternative fin shape | | | |

Images: pressure contours and streamlines for the best design (add to `images/`).

## Folder layout

```
cad/        Fusion exports: STEP for each design, drawing PDF (GitHub shows .stl files in 3D)
cfd/        Setup notes, mesh settings, SimScale project link, exported results (CSV)
analysis/   Hand calcs + Python for the tables and plots
images/     Contours, streamlines, mesh screenshots, renders
docs/       One-page write-up (PDF)
```

SimScale project (public): add the link here.

## Milestones

- [ ] Parametric fin can (fin count 3 -> 4 rebuilds cleanly)
- [ ] Pipe flow within 5% of hand calc
- [ ] Cylinder Cd near 2.0, mesh-independent
- [ ] Body-only run converged
- [ ] Three fin designs on identical settings
- [ ] Best design on a finer mesh + images
- [ ] Write-up

## What I'd do next

Fill in after the study (e.g. a finer mesh, a different speed, comparing with OpenRocket).
