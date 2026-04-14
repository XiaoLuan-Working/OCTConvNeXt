# OCTConvNeXt

OCTConvNeXt is a ConvNeXt-based classifier for optical coherence tomography (OCT) images. It combines convolutional feature extraction with lightweight self-attention in late stages to improve long-range retinal structure modeling while keeping the computational overhead modest.

This repository accompanies the manuscript on multi-dataset OCT classification and is intended for reproducible experimentation, ablation studies, and implementation reference.

## Project Highlights

- ConvNeXt backbone adapted for OCT classification.
- Lightweight multi-head self-attention inserted at late feature stages.
- Consistent training and evaluation across multiple public OCT datasets.
- Metrics, confusion matrices, Grad-CAM visualization, and efficiency analysis.

## Supported Datasets

The current implementation is designed for the following OCT classification datasets:

- OCTDL: 7 classes, including AMD, DME, ERM, NO, RAO, RVO, and VID.
- Retinal OCT-8: 8 classes, including AMD, CNV, DR, CSR, DRUSEN, MH, DME, and NO.
- OCT2017: 4 classes, including CNV, DME, DRUSEN, and NO.

## Requirements

Install the dependencies listed in `requirements.txt`.

Typical packages include:

- torch
- torchvision
- timm
- hydra-core
- omegaconf
- scikit-learn
- tensorboard
- opencv-python
- tqdm

## Data Preparation

The code expects a folder-style dataset layout such as:

```text
dataset
  train
    class_1
    class_2
    ...
  val
    class_1
    class_2
    ...
  test
    class_1
    class_2
    ...
```

Use `preprocessing.py` to prepare the dataset structure and image preprocessing pipeline if needed.

Example:

```bash
python preprocessing.py
```

## Training

Train the model with:

```bash
python main.py
```

Hydra configuration can be adjusted through the files in `configs/`.

Common command-line options:

- `-c` to specify the config file.
- `-p` to print the configuration before training.

## Outputs

The training pipeline can generate:

- Model checkpoints
- Training and validation curves
- Classification metrics
- Confusion matrices
- Grad-CAM visualizations

## Code Availability

The implementation code will be made publicly available in a Git repository upon publication of the manuscript. This repository is currently prepared as a release draft for reproducibility and will be opened once publication is finalized.

## Notes

- The repository is organized around the training and evaluation pipeline used in the manuscript.
- Dataset download links and any required preprocessing steps should be documented separately if redistribution is restricted.
