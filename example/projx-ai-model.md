<treqs-element id="61d5c2be189b11f1bd0d8adebfb72d7d" type="ai-model">

Label: CAS Object Detection Model
===

<treqs-link type="satisfies" target="629232fa4abe11f1b4ee467a017f3d7e">

> Satisfies the needs for the intended functionality of CAS object detection.
</treqs-link>

<treqs-link type="satisfies" target="efb61a8e77fb4332b26ffd229dd3a55e">
Satisfies the relevant AI Safety Requirements
</treqs-link>

> In this section, one would expect an AI model that is trained/evaluated with annotated data.
> This model should also be explained, ideally using treqs-elements corresponding to the Project X Information Model.

## Attributes

> In this section, all AI models shall be documented with the following attributes:

### 1. Model Architecture / Name

> Base architecture (e.g. 'YOLOv8')

### 2. Version

> Specific version for this training instance (e.g. 'YOLOv8-large-v2.3')

### 3. Training Configuration

> Supervised / Unsupervised / Reinforcement learning.
> Number of parameters and training epochs.
> Learning rate, batch size.

### 4. Performance Metrics

> Quantifiable validation performance (F1-score, accuracy, precision, recall)
> Performance in different ODD conditions.

### 5. Datasets Used

> Refers to all annotated data used for training (e.g. training / validation datasets)

### 6. AI Model Validation Procedures

> Describe the procedures used to validate the AI model (e.g. metrics, pass criteria)

</treqs-element>
