Label: Meaningful name for AI Model
===

<treqs-link type="satisfies" target="">

> Refer to annotation-requirement(s) that this model satisfies.
</treqs-link>

## Summary

> In this section, one would expect an AI model that is trained/evaluated with annotated data.
> This model should also be explained, ideally using treqs-elements corresponding to the FAMER Information Model.

## Technical Details

> In this section, all AI models shall be documented with the following attributes:

### 1. Model Architecture / Name

> Base architecture (e.g. 'YOLOv8')

### 2. Version

> Specific version for this training instance (e.g. 'YOLOv8-large-v2.3')

## AI Model Training and Validation Proceedures

### 3. Training Configuration

> Supervised / Unsupervised / Reinforcement learning.
> Number of parameters and training epochs.
> Learning rate, batch size.

### 4. Performance Metrics

> Quantifiable validation performance (F1-score, accuracy, precision, recall)
> Performance in different ODD conditions.

### 5. Datasets Used

> Refers to all annotated data used for training (e.g. training / validation datasets)

### 6. AI Model Validation Proceedures

> Describe the procedures used to validate the AI model (e.g. metrics, pass criteria)
