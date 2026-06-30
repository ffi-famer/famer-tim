FAMER Annotation Guideline
===

<treqs-element id="09c5c0683c0b11f1a001467a017f3d7d" type="annotation-guideline">

Vehicle and Object 2D/3D Annotation Guideline v1.0
---

Concrete instructions for annotating objects captured by a vehicle equipped with one camera and lidar.

**Annotation Instructions:**

**3D Cuboid Placement:**

- Draw 3D cuboids for all visible objects in classes: Vehicle, Truck, Bus, Pedestrian, Rider, MobilityDevice
- Object must be within 0-120 meters from ego vehicle
- Object must have at least 3 distinct lidar points
- Fit cuboids to look accurate in 3D view
- Maximum deviation: 0.1 meters on X, Y, Z axes

**2D Box Placement:**

- Draw 2D boxes for objects visible in camera
- Smallest box side must be > 10 pixels
- Maximum error: 2 pixels between box edge and object boundary

**Good Annotations:**

- Cuboid tightly fitted to object in 3D view
- 2D box accurately frames object, with an error of ≤ 2 pixels between the box side and object boundary.
- Same object_id for connected 2D/3D annotations
- Consistent dimensions throughout sequence for rigid objects

**Bad Annotations:**

- Cuboid too loose or misaligned in 3D
- 2D box encloses the object with an error of > 2 pixels between the box side and object boundary
- Different object_ids for same object in 2D/3D
- Changing dimensions for rigid objects across frames

**Class-Specific Rules:**

**Vehicle (Passenger Car, Van, Camping Car):**

- Include open doors in cuboid
- Exclude mirrors from cuboid
- Include mounted accessories (roof box, bike rack)

**Truck:**

- Include open doors in cuboid
- Exclude mirrors from cuboid
- Include driving cabin and cargo trailer

**Edge Cases:**

- Occlusion: maintain full object dimensions (don't shrink for missing points)
- Truncation: 2D boxes maintain full dimensions even at image edge
- Disappearing/reappearing: Use same object_id throughout sequence

**Quality Check:**

- Use "Polar Grid" to verify distance constraints (0-120m)
- Check 3D-to-2D projection alignment
- Verify object_id consistency between 2D/3D

<treqs-link type="specifies" target="b4756dba365711f185b3467a017f3d7d" >
Describes how to create the CAS object detection dataset.
</treqs-link>

<treqs-link type="specifies" target="5857ae3a3c0b11f1a36d467a017f3d7d" >
Uses example annotation platform.
</treqs-link>

<treqs-link type="input" target="31b676563bcc11f18bde467a017f3d7d"> 
Input to dataset annotation tests</treqs-link>
</treqs-element>

<treqs-element id="5857ae3a3c0b11f1a36d467a017f3d7d" type="annotation-tool">

Example Annotation Platform
---

Annotation platform used for creating the CAS 2D/3D object detection dataset.

**Tool Features:**

- 2D/3D connected object annotation
- Motion compensation for static objects
- Frame interpolation for sequences
- Export to standard formats

**Sensor Support:**

- Camera and 360° lidar fusion
- 2D-to-3D and 3D-to-2D projection
- Polar grid for distance verification

<treqs-link type="creates" target="b4756dba365711f185b3467a017f3d7d">

> Used to create dataset annotations
</treqs-link>

</treqs-element>
