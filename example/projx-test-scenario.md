Project X Test Scenario and Results
===

<treqs-element id="31b676563bcc11f18bde467a017f3d7d" type="dataset-annotation-check">

PROJ-X-Test-Scenario-1: CAS Object Detection Validation
---

**Test Objective:**

This test aims to verify the plausibility of annotations in the CAS detection dataset.

**Test Data:**

<!-- 30% of the total 150 sequences -->

- 45 test sequences (separate from training data), each 100-200 frames at 10Hz.
- Captured on Swedish roads covering all defined scenarios:
  - Highway: 18 sequences (40%)
  - Tunnel: 5 sequences (10%)
  - City Center: 14 sequences (30%)
  - Suburban and residential areas: 8 sequences (20%)

- Class distribution covers: Vehicle, Truck, Bus, Pedestrian, Rider, RidableVehicle

**Pass Criteria:**

- No unannotated frames in scenes with visible objects
- 3D box dimensions are within plausible ranges per class
- 2D/3D box pixel error <= 2px
- Tracking consistency >= 95% across sequences
- Inter-annotator IoU agreement >= 0.85

<treqs-link type="produces" target="9c31b2c03bcc11f19f0d467a017f3d7d">Creates check results</treqs-link>
</treqs-element>

<treqs-element id="9c31b2c03bcc11f19f0d467a017f3d7d" type="dataset-annotation-check-result">

PROJ-X-Test-Result-1: Test Results (PASS)
---

**Plausibility Checks:**

| Check | Result | Status |
|---|---|---|
| Completeness | 0 unannotated frames in non-empty scenes | PASS |
| 3D box dimension outliers | 0.4% of annotations flagged across all classes | PASS |
| 2D/3D projection deviation | 1.7px mean | PASS |
| Tracking ID consistency | 95.8% across sequences | PASS |
| Inter-annotator IoU agreement | 0.88 mean | PASS |

**Per-Class 3D Box Outlier Rate:**

|Class          |Outlier Rate |Status |
|---            |---:         |---:   |
| Vehicle       | 0.3%        | PASS  |
| Truck         | 0.5%        | PASS  |
| Bus           | 0.4%        | PASS  |
| Pedestrian    | 0.6%        | PASS  |
| Rider         | 0.3%        | PASS  |
| RidableVehicle| 0.4%        | PASS  |

**Notes:**

- Foggy sequences showed lower inter-annotator agreement (0.84), flagged for re-annotation review.

<treqs-link type="validates" target="b4756dba365711f185b3467a017f3d7d">

> Validates the dataset annotations
</treqs-link>

</treqs-element>
