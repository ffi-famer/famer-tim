# FAMER TTIM

For visualization, this document creates an instance of each item in the traceability model with the same name.
It then adds links according to the traceability model.
This allows to generate a graphical traceability model with the following command:

```bash
treqs list --plantuml --outlinks tim-documentation/famer-tim-rationale.md
```

The resulting graph is shown at the end of this document.

In addition, the following treqs command produces an overview which standards relate to a particular element in the TIM.

```bash
treqs list --plantuml --inlinks --followlinks True --type annotation-requirement
```

# Types and Links

<treqs-element id="9c3484c82d124e76a694554125353df9" type="operational-design-domain">

Operational Design Domain (ODD)
---

Todos:

- [ ] Make sure that all neighbouring artifacts are in TIM
- [ ] Provide an example

<treqs-link type="context-for" target="5a0039ffee7a4924bfe423956918f750" />
</treqs-element>
<treqs-element id="5a0039ffee7a4924bfe423956918f750" type="intended-functionality">

Intended Functionality
---

Todos:

- [ ] Make sure that all neighbouring artifacts are in TIM
- [ ] Provide an example

<treqs-link type="includes" target="1f0e57fcf2ed4e5d9547a64d5f6a3994" />
<treqs-link type="foundation-for" target="667438ccdfef413aa485ff2581d6ffc5" />

</treqs-element>
<treqs-element id="1f0e57fcf2ed4e5d9547a64d5f6a3994" type="functional-safety-concept">

Functional Safety Concept
---

Todos:

- [ ] Make sure that all neighbouring artifacts are in TIM
- [ ] Provide an example

<treqs-link type="solved-by" target="de34d5f3d3a24e8ba360001b5aa25922" />
</treqs-element>
<treqs-element id="de34d5f3d3a24e8ba360001b5aa25922" type="functional-safety-requirement">

Functional Safety Requirement
---

Todos:

- [ ] Make sure that all neighbouring artifacts are in TIM
  - [ ] We may need Technical Safety Requirement and Technical Safety Concept as well
  - [ ] Unclear whether it is FSR or TSR which links to AI Safety Requirement
- [ ] Provide an example

Changes:

- Renamed from system-level-safety-requirement to functional-safety-requirement (but may need to link to a technical safety requirement?)

Participant 3:

- May need to introduce Functional Safety Concept between intended Functionality and System Level Safety Requirement
- The safety concept must relate to the system architecture through system components (relate to TSC-Technical Safety Concept) and the decomposition into HW and SW requirements
- Open question: Is this the FSR (Functional Safety Requirement)? On which level (system/software)?
  - if yes: Link to System Component missing?

Safety goal: unaware of technical solution (do not overrun pedestrians)
FSC: allocate FSR to system (detect pedestrians, engage breaking)
FSR: detect pedestrians; engage breaking; sensor is running and not blocked (self-test); possible to activate, absence of errors
TSR: parameters for detection (area, volume, density, moving? how fast?); dependend on technology (e.g. radar, camera, lidar); e.g. influenced by rain, fog, ...

<treqs-link type="demands" target="b46bb22119ac47028bee515844fcbf33" />
</treqs-element>
<treqs-element id="b46bb22119ac47028bee515844fcbf33" type="ai-safety-requirement">

AI Safety Requirement
---

Todos:

- [ ] Make sure that all neighbouring artifacts are in TIM
- [ ] Provide an example
- [ ] Include KPI in template and example

Participant 3:

- Link to system or software requirement?

<treqs-link type="foundation-for" target="667438ccdfef413aa485ff2581d6ffc5" />
</treqs-element>
<treqs-element id="667438ccdfef413aa485ff2581d6ffc5" type="dataset-requirement">

Data Set Requirement
---

Todos:

- [ ] Make sure that all neighbouring artifacts are in TIM
- [ ] Provide an example

<treqs-link type="augmented-by" target="40a7bac946a34174844e42378d23e489" />
</treqs-element>
<treqs-element id="40a7bac946a34174844e42378d23e489" type="annotation-requirement">

Annotation Requirement
---

|Reference|Status|Comment|
|---:|---:|---:|
|FAMER IM|okay||
|ISO8800|Probably okay|input space constraints must be documented|
|ISO21448|okay||

Todos:

- [ ] Provide an example
- [ ] Add Input Space Constraint as traceable artifact or attribute

<treqs-link type="specifies" target="79a0763913e946e7b238deb3eb705ecb" />
<treqs-link type="input" target="9f336b1a28b7439899012241f15623ec" />
</treqs-element>

---

<treqs-element id="79a0763913e946e7b238deb3eb705ecb" type="annotation-guideline">

Annotation Guideline
---

|Reference|Status|
|---:|---:|
|FAMER IM|Okay|
|ISO880|Okay|
|ISO21448|Okay|

Todos:

- [ ] Provide an example

Participant 1:

- Guideline contains examples, annotation requirement can be an abstraction.
- Guideline may require experience and often written/owned by annotation provide

<treqs-link type="specifies" target="2e6fe9901849498f86d6c514c3c824e2" />
<treqs-link type="describes" target="3eac6b785ba245a284185f6edbfc0767">

- renamed ``applied_to`` to ``describes``

</treqs-link>
<treqs-link type="input" target="9f336b1a28b7439899012241f15623ec" />

</treqs-element>

---

<treqs-element id="3eac6b785ba245a284185f6edbfc0767" type="dataset-annotation">

Dataset Annotation
---

Participant 1:

- might come in versions
  - there might be updates, trying to overcome annotation errors, leading to a new version
  - there might be additions, either leading to a new version of this dataset, or an additional annotated dataset
- can be checked and updated based on testresults or based on ``plausability checks`` (often included in the tool)
- annotation v&v should probably be added
  - today, annotation companies may not share information on which measures they have taken towards quality assurance of the annotations
  - client may run automated checks (e.g. use current version of their model to find missing annotations in the new annotated dataset)
  - backloop from AIModel to AnnotatedData is needed (but an expert must judge: the object is missing in the annotations, or the old model did misclassify here)

|Reference|Status|Comment|
|---:|---:|---|
|FAMER IM|Okay|Testresults may need refinement|
|ISO880|Okay||
|ISO21448|Okay||

<treqs-link type="training-data-for" target="4134ca2ab0434822aa98c16f18b4db0d" />

<treqs-link type="evaluation-data-for" target="4134ca2ab0434822aa98c16f18b4db0d" />

</treqs-element>

---

<treqs-element id="4134ca2ab0434822aa98c16f18b4db0d" type="ai-model" version="Model Version" architecture="Model Architecture" model-type="Model Type" training-technique="Training Technique">

AI Model
---

A specific AI model that is trained and/or evaluated with Dataset Annotations.
The AI model shall be clearly described based on the following attributes:

- The Model Architecture / Model Name (e.g. ChatGPT)
- Its version
- Its configuration (e.g. parameters, Dataset Annotations used for training or fine tuning)
- Its type (Deep Learning, Large Language Model, ...)

Participant 1:

- Model is a collection of a lot of information items
  - Model design (number of nodes/neurons)
  - Several Dataset Annotationssets (or versions) relate to the model

|Reference|Status|Comment|
|---:|---:|---|
|FAMER IM|Needs work|add Template and example|
|ISO8800|Needs work|add Template and example|
|ISO21448|okay||

Todos:

- [ ] Provide an example
- [ ] Add attributes for version, model type, ...
  - [x] Make model version an attribute of AI Model
- [x] Renamed ``Model``to ``AI Model`` to align with IM
- [ ] Add Training measures (augmentation, hyperparameter tuning, etc.) as implementation details of `ai-model` training process, e.g. by creating templates for AI-Model descriptions to satisfy ISO8800
- [ ] Add training-technique as attribute (suppervised, unsupervised, ...) to satisfy ISO8800

<treqs-link type="satisfies" target="b46bb22119ac47028bee515844fcbf33" />
<treqs-link type="satisfies" target="5a0039ffee7a4924bfe423956918f750" />
</treqs-element>

---

<treqs-element id="9f336b1a28b7439899012241f15623ec" type="dataset-annotation-check">

Dataset Annotation Check
---

Changed from Test Scenario to Dataset Annotation Check based on discussion today.

|Reference|Status|Comment|
|---:|---:|---|
|FAMER IM|okay|Provide example|
|ISO8800|Needs work|Change name|
|ISO21448|okay||

Todos:

- [ ] Provide an example
- [x] To align with ISO8800, ``Annotated Data`` should be renamed into ``Data Annotations``. Then, this should likely be renamed to ``Data Annotation Check``.

Text below may be outdated, but expert check is needed.

### FAMER IM Status: needs work/needs expert evaluation

- Can the IM Scenario be used? Perhaps it is a subtype?
- IM Scenario is connected to Edge Case, perhaps it is something different?
- This test scenario should be used for testing the quality of the data
- Participant 2: on system level, scenario is something that happens on the road. Edge case is a specific scenario that may be hard to capture. Test scenario is a scenario used for testing. Do not confuse with scenario-based specification in RE.

- recheck data (Researcher 1)
- Alternative: Scenario and link e.g. from a test to say that this scenario is part of that test
- Alternative: rename to Test or TestCase and clarify

Participant 1:

- 1/3 used for training (often 80% of the available data)
- 1/3 is used for iterative evaluating, --> test data set
  - recall, precision are then the test results
  - so, important to keep track which parts of a data set have been used for training, and which have been used for testing
- 1/3 is kept away, not used in building the model
- Test Scenario might be the wrong wording, or wrong level of abstraction, it is actually the data set that must be distributed over testing and training.
- Researcher 1: Must be clear that this is model level testing, focusing on the Dataset Annotations. There should also be system level testing in context.
  - how many type of data is tested
  - who is responsible
  - real world scenario or model testing

<treqs-link type="checks" target="3eac6b785ba245a284185f6edbfc0767" />
<treqs-link type="produces" target="7b8e858a6fe84f67843584e2f2ba8929" />
</treqs-element>

---

<treqs-element id="7b8e858a6fe84f67843584e2f2ba8929" type="dataset-annotation-check-result">

Dataset Annotation Check Result
---

Changed from ``Test Result`` to ``Dataset Annotation Check Result`` to be consistent in naming to ``Dataset Annotation Check``.

|Reference|Status|Comment|
|---:|---:|---|
|FAMER IM|okay|Renamed|
|ISO8800|okay||
|ISO21448|okay||

Todos:

- [ ] Provide an example
- [x] May depend on ``Test Scenario`` resolution. We should however include it.

### FAMER IM Status: needs expert evaluation

- Not included in IM. Actually needed? Could be important for dashboards.
- Compare with other TIMs if this is usually included
- Participant 2 needed, since it is an iterative process, so the results should likely play into the safety argumentation. unsure

<treqs-link type="validates" target="3eac6b785ba245a284185f6edbfc0767" />
</treqs-element>

---

<treqs-element id="2e6fe9901849498f86d6c514c3c824e2" type="annotation-tool">

Annotation Tool
---

- Changed name from Tool-Version to Annotation-Tool

Todos:

- [ ] Provide an example
- [ ] Decide whether to keep it

### FAMER IM Status: needs expert evaluation

Tool version (and tool) is missing in information model. Do we need it? Perhaps, we would not need it if only internal, but since customers start to ask for standardized tools and generated annotations become more important, it could be a valuable addition. That would be an addition... Ask Participant 2?

- [x] rename to AnnotationTool

- Participant 2: Could be too detailed and a specific need for annotation supplier, but at the same time might systematically affect annotation data and might be important meta data, in particular in light of automoatic annotation
- Researcher 1: Standards and tools can be a demand of the customer
  - Example: OpenLabel (may be important, because standardizes the label format)
- Participant 1: hard to distinguish issues coming from the tool and issues coming from the annotator
  - so more important to have quality assurance in the TIM, while tooling might be too specific
  - Researcher 1 to check examples from interview data, otherwise, candidate to remove from TIM
- Participant 1: versioning and clarifying the plausibility checks may be more valuable here

<treqs-link type="creates" target="3eac6b785ba245a284185f6edbfc0767" />

</treqs-element>

---

## FAMER discussion

Participant 3: Connect to their TIM (ISO 8800 missing in their view atm)

Participant 2: Do we need only safety requirements? Otherwise, we should treat them as a subset of the requirements

- Important to support safety argumentation
- Important to keep the model simple for the lower levels of abstraction
  - Should that be on a specific, consolidated annotation requirement or on the annotation guideline?

Participant 3: connect FAMER to distributed sensor, actuator, control (including protocols and network topology)

- But would we have to have a specific tracelink?

Next steps:

- Participant 3 to share his model on Miro
- Participant 1 and Researcher 2 (+Researcher 3, Researcher 1) to meet to understand the lower abstraction levels of our tim
