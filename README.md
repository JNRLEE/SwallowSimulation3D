# SwallowSimulation3D

**3D physics simulation of pharyngeal swallowing mechanics for acoustic research**

> Full code will be released upon paper publication.

---

## What is this?

Understanding *why* swallowing sounds the way it does requires a physical model — not just data. This project builds a 3D simulation of the human pharynx and upper esophagus to:

1. Generate synthetic swallowing acoustics for ML training data augmentation
2. Explore how anatomical variation (strictures, reduced muscle tone) changes the acoustic signature
3. Provide mechanistic grounding for features used in the [MicForDysphagia](https://github.com/JNRLEE/MicForDysphagia) classifier

---

## Simulation Architecture

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
   neck surface vibration estimation)
        │
        ▼
  Synthetic Audio Output
  (time-series neck vibration signal)
```

---

## Modeled Anatomy

- Pharyngeal cavity with realistic SDF-based geometry
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
| Paper | Submission in preparation | In preparation |

---

## Relationship to Clinical ML

This simulation feeds into the [MicForDysphagia](https://github.com/JNRLEE/MicForDysphagia) project. Synthetic data helps address the limited availability of labeled clinical recordings, and physics-derived features provide interpretable biomarkers.

---

## Code Release

The full simulation codebase will be released publicly upon paper acceptance. If you are interested in the methodology or collaboration, please open an issue.

---

## License

To be determined upon publication.
