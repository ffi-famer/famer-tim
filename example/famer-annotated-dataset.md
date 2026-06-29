FAMER Dataset Annotations
===

<treqs-element id="c82de4d298874abd90b8e7bd0ed32b99" type="annotation-requirement">

FAMER-Annotation-Req-1: Objects for path planning shall be annotated in 2D and 3D
---

All static and dynamic objects relevant to collision avoidance path planning shall be annotated with connected 2D boxes and 3D cuboids.

**Coverage Requirements:**

- **Distance range:** 0-120 meters from the ego vehicle
- **Sensor fusion:** Camera + 360° lidar
- **Object classes:** Vehicle, Truck, Bus, Pedestrian, Rider, RidableVehicle

**Quality Requirements:**

- 3D cuboid accuracy: <=0.1m deviation on X, Y, Z
- 2D box accuracy: <=2 pixel error
- Connected objects: Same object_id for 2D/3D pairs

<treqs-link type="input" target="31b676563bcc11f18bde467a017f3d7d"> 
Input to dataset annotation test
</treqs-link>
</treqs-element>

<treqs-element id="2f719092667b410eb93600352131a4df" type="dataset-requirement">

FAMER-Dataset-Req-1: Dataset shall support CAS safe path planning perception
---

The dataset shall be sufficient to train perception models for detecting objects and calculating safe steering paths in the CAS ODD.

**Requirements:**

- **Geographic coverage:** Swedish roads (highway, tunnel, city, suburban)
- **Sensor modalities:** Camera + lidar fusion
- **Sequence structure:** 100-200 frames at 10 Hz
- **Annotation format:** Connected 2D/3D objects

<treqs-link type="augmented-by" target="c82de4d298874abd90b8e7bd0ed32b99" />

</treqs-element>

<treqs-element id="efb61a8e77fb4332b26ffd229dd3a55e" type="ai-safety-requirement">

FAMER-AI-Safety-Req-1: Perception system reliably detects objects for safe path calculation
---

The AI-based perception system shall reliably detect and track objects relevant to collision avoidance to enable safe steering path planning.

**Performance Targets:**

- **Object detection recall:** ≥ 98% for safety-critical classes
- **3D localization accuracy:** ≤ 0.15m error
- **Tracking consistency:** ≥ 95% across sequences

<treqs-link type="foundation-for" target="2f719092667b410eb93600352131a4df" />

</treqs-element>

<treqs-element id="e8a5c74366a84064bbb7e27c17d6abeb" type="functional-safety-requirement">

FAMER-Functional-Safety-Req-1: CAS shall detect threats and provide safe path suggestions
---

The Collision Avoidance by Steering (CAS) system shall detect road threats and provide safe steering path suggestions to avoid collisions.

**Requirements:**

- Continuous background operation within ODD
- Object detection and threat assessment
- Safe path calculation with BLIS support

<treqs-link type="demands" target="efb61a8e77fb4332b26ffd229dd3a55e" />
</treqs-element>

<treqs-element id="5f7dd5a569474dad89ee52408cfd70a3" type="functional-safety-concept">

FAMER Functional-Safety-Concept: CAS detects objects and suggests safe steering paths
---

The system achieves collision avoidance by:

- Detecting and tracking objects in the vehicle's path
- Assessing collision risk continuously
- Calculating and suggesting safe lateral paths
- Supporting decisions with BLIS lateral awareness

<treqs-link type="solved-by" target="e8a5c74366a84064bbb7e27c17d6abeb" />
</treqs-element>

<treqs-element id="b4756dba365711f185b3467a017f3d7d" type="dataset-annotation">

FAMER-Annotated-Data-1: CAS Object Detection Dataset v1.0
---

Dataset containing annotated sequences of road objects for training and evaluating the CAS perception system.

**Dataset Details:**

- Sequences: 150 sequences (100-200 frames each at 10 Hz)
- Sensors: Camera + 360° lidar fusion
- Scenarios: Highway, tunnel, city center, suburban areas
- Object classes: Vehicle, Truck, Bus, Pedestrian, Rider, RidableVehicle
- Annotation format: Connected 2D boxes + 3D cuboids
- Quality: 3D accuracy ≤0.1m, 2D accuracy ≤2 pixels

**Coverage:**

- Distance range: 0-120m from ego vehicle
- Geographic: Swedish public roads
- Conditions: Various lighting and traffic scenarios

<treqs-link type="training-data-for" target="61d5c2be189b11f1bd0d8adebfb72d7d">

> Trains the CAS object detection model
</treqs-link>

</treqs-element>
