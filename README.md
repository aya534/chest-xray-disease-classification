# Chest X-Ray Disease Classification with VGG19 and ResNet50

A graduation project exploring transfer learning for multi-class chest X-ray image classification. Two approaches are included: a VGG19-based model with additional CNN layers and a ResNet50-based model.

> **Research/educational project only.** This repository is not a medical device and must not be used to diagnose, screen, or make treatment decisions for patients.

## Project overview

The notebooks use pretrained ImageNet feature extractors and classify images into seven classes represented in the notebooks:

- COVID
- Cardiomegaly
- Lung_Opacity
- NORMAL
- PNEUMONIA
- Pleural
- TURBERCULOSIS (spelling as present in the notebook labels; confirm against the source dataset)

Both experiments use 224 × 224 RGB images and report results after 10 training epochs.

## Model approaches

- **VGG19 + custom CNN:** VGG19 is used without its top classification layer, followed by additional layers for classification.
- **ResNet50:** ResNet50 is used without its top classification layer, followed by global average pooling and a dense softmax output layer.

## Recorded results

The table below summarizes the metrics already saved in the notebooks. These are existing notebook outputs, not results from a fresh run.

| Metric | VGG19 + CNN | ResNet50 |
|---|---:|---:|
| Training accuracy | 99.80% | 93.29% |
| Validation accuracy | 89.32% | 91.02% |
| Test accuracy | 90.03% | 89.89% |
| Test images | 1,464 | 1,464 |

The recorded test accuracies are close. These values alone do not establish that one architecture is superior. The VGG19 notebook shows a larger training-to-validation accuracy gap, which may indicate overfitting. The experiments should be compared carefully, including data splitting, preprocessing, class-wise metrics, and reproducibility.

## Repository structure

```text
.
├── README.md
├── notebooks/
│   ├── vgg19_cnn.ipynb
│   └── resnet50.ipynb
├── results/
│   └── model_comparison.md
├── requirements.txt
└── .gitignore
```

## Dataset

The dataset is **not included** in this repository. The notebooks were developed in Kaggle and refer to dataset files under `/kaggle/input/`. To rerun them:

1. Open a notebook in Kaggle.
2. Attach the appropriate chest X-ray dataset that contains the expected folder structure.
3. Check and update the dataset path in the notebook if the mounted path differs.
4. Run the notebook in order.

Before redistributing any dataset files, check the dataset's license and terms. This repository does not claim ownership of the images.

## Run locally

The notebooks were originally run on Kaggle. To explore them locally, create a Python environment, install the packages in `requirements.txt`, and update the dataset paths. TensorFlow training may require compatible hardware and software; Kaggle's configured environment may be easier to reproduce.

```bash
python -m venv .venv
```

Activate the environment, then install dependencies:

```bash
python -m pip install -r requirements.txt
```

Open the project in VS Code and run the notebooks with the Jupyter extension.

## Limitations

- Results are dependent on the dataset, data split, preprocessing, and training configuration.
- The class distribution is uneven, so overall accuracy does not tell the whole story. Review the class-wise precision, recall, F1-score, and confusion matrix in each notebook.
- The notebooks use dataset paths specific to Kaggle and may need edits to run elsewhere.
- The recorded results have not been independently reproduced as part of preparing this repository.
- Chest X-ray classification is a high-stakes medical task. These models are for educational experimentation only, not clinical use.

## Acknowledgment

This repository presents the author's graduation-project experiments using VGG19 and ResNet50. Add the original dataset citation and any project-team/supervisor acknowledgments here, as appropriate.
