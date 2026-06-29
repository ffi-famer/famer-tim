FAMER Intended Functionality
===

<treqs-element id="629232fa4abe11f1b4ee467a017f3d7e" type="intended-functionality">

Collision Avoidance by Steering (CAS) Intended Functionality
---

CAS is a driving assistance function aimed to avoid/reduce collisions by actively supporting lateral vehicle control when potential crashes are detected.

**Key Functions:**

- The Collision Avoidance by Steering shall operate continuously within its ODD.
- The system shall evaluate detected objects and assess collision risk.
- The system shall provide user notification when a collision risk is detected or when system functionality is degraded/unavailable.

**Operational Context:**

- Outside the defined ODD, CAS shall be disabled or inactive outside ODD boundaries.
- The user shall be informed when the system functionality is not available.

**System Dependencies:**

- Blind Spot Information System (BLIS) for lateral awareness
- Vehicle dynamics estimation for safe path calculation
- Object detection and tracking for threat assessment

**Safety Principles:**

- The user remains the ultimate authority over vehicle control.
- All steering interventions shall be predictable, bounded and reversible by user input.

<treqs-link type="includes" target="5f7dd5a569474dad89ee52408cfd70a3">

> Includes the functional safety concept.
</treqs-link>

<treqs-link type="foundation-for" target="2f719092667b410eb93600352131a4df">

> Provides foundation for dataset requirements.
</treqs-link>

</treqs-element>
