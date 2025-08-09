## Cats vs Dogs Classifier (VGG16 Transfer Learning + Fine-Tuning)
This project trains a binary image classifier to distinguish between cats and dogs using **VGG16** as a pretrained base model with transfer learning and fine-tuning.
---

## Dataset
The dataset should be organized as follows:

```bash
dataset/
 │
 ├── train/
 │ ├── cats/
 │ └── dogs/
 │
 ├── val/
 │ ├── cats/
 │ └── dogs/

test/
 ├── 1.jpg
 ├── 2.jpg
 └── ...
```

 - `train/` : Training images separated into class folders.
 - `val/` : Validation images separated into class folders.
 - `test/` : Test images for generating predictions.

## Installation

1. Clone the repository:
```bash
git clone https://github.com/AbhijatSahu/Cats-VS-Dogs-Classifier.git
```

2. Install the required dependencies:
```bash
pip install -r Requirements.txt
```

## Training
Training Process
 - Phase 1: Transfer Learning (VGG16 Frozen)

   Base model: VGG16 pretrained on ImageNet

   Additional Dense layers with Batch Normalization & Dropout

   Trained for 10 epochs

   Result:

    - Train Accuracy: 93.77%

    - Validation Accuracy: 92.86%

 - Phase 2: Fine-Tuning (Last 4 Convolutional Layers Unfrozen)

   Learning rate reduced to 1e-5

   Trained for 10 more epochs

   Result:

    - Train Accuracy: 99.32%

    - Validation Accuracy: 96.14%

## After training, the model is saved as:
```bash
model.save('model.h5')
```

## Generating Predictions for Submission
To create a submission file:
 - Load model.h5
 - Preprocess images in dataset/test/
 - Predict probabilities
 - Save a CSV with columns:
   - id, label

## model and dataset
```bash
https://drive.google.com/drive/folders/1tiLGCosrELzsTbpQIi2PQq-GIoTUuShm?usp=sharing
```
