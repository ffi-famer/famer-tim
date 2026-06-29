Compliance Requirements Derived from ISO 21448 (SOTIF)
=

// General scope: requirements directly relevant to achieving SOTIF objectives regarding insufficiencies and intended functionality, with scope limited to specifications within the system development phase.

<treqs-element id="296db62eaf7411f08318467a017f3d7d" type="compl.requirement">

ISO-21448-R1: Intended functionality
--

The system shall have clearly and completely defined intended functionality, with sufficient information to conduct the SOTIF-related activities. This includes:

- The ODD.
- Level and details of the automated driving function control authority over vehicle dynamics.
- Design of the relevant system.
- Vehicle-level SOTIF strategy.
- Description of decision-making logic and its elements implementing the intended functionality.

<treqs-link type="derivedFrom" target="f6994569cefe41878f546dce683e40f5"/>
<treqs-link type="derivedFrom" target="89db272ec18c11f0a009467a017f3d7d" />

</treqs-element>

<treqs-element id="2c7ec23ec18211f0bf0f467a017f3d7d" type="compl.requirement">

ISO-21448-R2: Operational Design Domain (ODD)
--

The system shall have a precisely specified Operational Design Domain, including:

- Geographic boundaries
- Environmental conditions (weather, lighting, road conditions)
- Traffic conditions
- Speed ranges
- Road types and infrastructure

<treqs-link type="derivedFrom" target="d0ff2848c19211f09089467a017f3d7d" />
<treqs-link type="derivedFrom" target="89db272ec18c11f0a009467a017f3d7d" />
<treqs-link type="derivedFrom" target="8c3bf8a4c19111f09d4f467a017f3d7d" />

</treqs-element>

<treqs-element id="fbfad3e2c18511f0b5d9467a017f3d7d" type="compl.requirement">

ISO-21448-R3: Modifications and limitations
--

The system shall document all functional modifications and known limitations of the intended functionality.

<treqs-link type="derivedFrom" target="7bb37758c19311f08e88467a017f3d7d" />
<treqs-link type="derivedFrom" target="daa20ae0c19311f0a520467a017f3d7d" />

</treqs-element>

<treqs-element id="7513380ac18611f0ac17467a017f3d7d" type="compl.requirement">

ISO-21448-R4: Acceptance criteria for residual risk
--

The system shall establish quantifiable acceptance criteria for residual risk that remains after mitigation measures.

<treqs-link type="derivedFrom" target="1e15b4fcc24811f0b0a9467a017f3d7d" />
<treqs-link type="derivedFrom" target="aa6c7c66c24711f08fbf467a017f3d7d" />

</treqs-element>

<treqs-element id="b806706ec18611f0b6c1467a017f3d7d" type="compl.requirement">

ISO-21448-R5: Risk Evaluation
--

The system shall evaluate identified risks considering:

- Severity (potential harm)
- Exposure (frequency of operational scenarios)
- Controllability (ability to prevent harm)

<treqs-link type="derivedFrom" target="97614f9cc24811f081d0467a017f3d7d" />
<treqs-link type="derivedFrom" target="0031dfdcc24911f08d88467a017f3d7d" />

- Consequence for FAMER TIM:
  - On system level, out of scope for FAMER TIM (but relevant to give traceable targets)

</treqs-element>

<treqs-element id="2ae06428c18711f0975d467a017f3d7d" type="compl.requirement">

ISO-21448-R6: Systematic approach to identify functional insufficiencies
--

The system development shall employ a systematic approach to identify functional insufficiencies that could lead to hazardous behavior, and the system response shall be evaluated for SOTIF acceptability.

<treqs-link type="derivedFrom" target="e9b1bb3cc24e11f0990c467a017f3d7d" />
<treqs-link type="derivedFrom" target="95eae3e2c24f11f0a3c3467a017f3d7d" />

</treqs-element>

<treqs-element id="7cae6d18c18711f087c0467a017f3d7d" type="compl.requirement">

ISO-21448-R7: Functional insufficiencies and potential triggering conditions
--

The system shall identify functional insufficiencies and potential triggering conditions using both:

- Top-down analysis: From hazards to their potential causes.

- Bottom-up analysis: From known system limitations to potential hazards.

<treqs-link type="derivedFrom" target="23756138c25011f0a1fb467a017f3d7d" />

- Consequence for FAMER TIM:
  - On system level, out of scope for FAMER TIM (but relevant to give traceable targets), it should be covered in requirements
  - triggering condition (e.g. sign detection, but snow on sign), to trace edge cases and scenarios against... these may be relevant for the TIM

</treqs-element>

<treqs-element id="d334083cc18711f0b1cd467a017f3d7d" type="compl.requirement">

ISO-21448-R8: Analysis-based verification and validation methods
--

The system shall utilize analysis-based verification and validation methods, including:

- Formal verification techniques

- Safety argumentation

- Quantitative risk analysis

- Theoretical performance analysis

<treqs-link type="derivedFrom" target="23b5016ac25211f08fa9467a017f3d7d" />
<treqs-link type="derivedFrom" target="3eafc800c25311f0849c467a017f3d7d" />
<treqs-link type="derivedFrom" target="cacb2f32c25311f0bafe467a017f3d7d" />

- Consequence for FAMER TIM:
  - On system level, out of scope for FAMER TIM (but relevant to give traceable targets), it should be covered in requirements

</treqs-element>
