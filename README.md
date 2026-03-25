# SwallowSimulation3D

**3D physics simulation of pharyngeal swallowing mechanics — toward personalized structural reconstruction from in-ear acoustics**

> Full code will be released upon paper publication.

---

## Vision

Current clinical assessment of swallowing disorders requires **videofluoroscopy** — a radiation-based imaging procedure performed in a clinical setting. We are working toward a future where a patient can wear an **in-ear microphone at home** and receive a personalized 3D model of their pharyngeal swallowing dynamics.

The path to get there:

```
[This project]                     [Long-term goal]
3D physics simulation         →    Physics-Informed Neural Networks (PINNs)
of pharyngeal anatomy              trained on in-ear acoustic data
                              →    Personalized 3D reconstruction of
                                   pharyngeal/laryngeal motion structure
                              →    Home-based, imaging-free dysphagia monitoring
```

The physics simulation in this repository provides the **forward model** — the mechanistic prior that makes the inverse problem tractable. Without it, mapping acoustic signal → 3D structure is severely underconstrained.

---

## What is this?

This project builds a 3D simulation of the human pharynx and upper esophagus to:

1. Establish a validated physics-based forward model of swallowing acoustics
2. Generate synthetic training data for the inverse (PINN) model
3. Provide mechanistic grounding for features used in the companion [MicForDysphagia](https://github.com/JNRLEE/MicForDysphagia) classifier

---

## Architecture

```
Anatomical Geometry
(pharynx, epiglottis, aryepiglottic folds,
 vestibular folds, upper esophageal sphincter)
        │
        ▼
  Physics Engine
  (soft-body deformation, fluid-structure interaction,
   bolus transport, peristaltic wave propagation)
        │
        ▼
  Acoustic Propagation Model
  (pressure wave generation at tissue boundaries,
   neck/ear canal surface vibration estimation)
        │
        ▼
  Synthetic Audio Output             Forward model training data
  (time-series signal)          →    for PINN inverse solver
```

---

## Modeled Anatomy

- Pharyngeal cavity with SDF-based geometry
- Epiglottis and aryepiglottic folds
- Vestibular folds
- Upper esophageal sphincter with peristaltic dynamics
- Multi-bolus transport scenarios

---

## Current Status

| Phase | Description | Status |
|---|---|---|
| Phase 1–9 | Geometry construction, physics calibration | Complete |
| Phase 10–14 | Vestibule, bolus transport, acoustic coupling | Complete |
| Phase 15 | Acoustic signal synthesis | In progress |
| Phase 16 | Validation against clinical recordings | In progress |
| Next | PINN inverse model (acoustic → 3D structure) | Planned |
| Paper | Submission in preparation | In preparation |

---

## Relationship to MicForDysphagia

This project and [MicForDysphagia](https://github.com/JNRLEE/MicForDysphagia) are two components of a larger system:

- **MicForDysphagia**: discriminative — classifies swallowing health from neck microphone recordings
- **SwallowSimulation3D**: generative — models the physics that produce those recordings, and will eventually power a PINN-based inverse solver to reconstruct personalized anatomy

Together they form a pipeline from **raw acoustic signal** to **clinical structural insight**, without imaging.

---

## Code Release

The full simulation codebase will be released publicly upon paper acceptance. If you are interested in the methodology or potential collaboration, please open an issue.

---

## License

To be determined upon publication.
