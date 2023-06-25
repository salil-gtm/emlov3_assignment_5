# EMLOv3 | Assignment 5

[![pytorch](https://img.shields.io/badge/PyTorch_2.0+-ee4c2c?logo=pytorch&logoColor=white)](https://pytorch.org/get-started/locally/)
[![lightning](https://img.shields.io/badge/-Lightning_2.0+-792ee5?logo=pytorchlightning&logoColor=white)](https://pytorchlightning.ai/)
[![hydra](https://img.shields.io/badge/Config-Hydra_1.3-89b8cd)](https://hydra.cc/)
[![black](https://img.shields.io/badge/Code%20Style-Black-black.svg?labelColor=gray)](https://black.readthedocs.io/en/stable/)


## Adamantium 

<em>The name is inspired by the metal alloy which is bonded to the character Wolverine's skeleton and claws.</em>

Adamantium is a custom python package which currently supports:
- Usage of any model available in TIMM for training & evalution on CIFAR10 dataset. 
- VIT model for training, evaluation & inference on Cats-Dogs dataset.

All functionalities can be controlled by hydra configs.

## Using Dev Container

1. Clone the repository.

```bash
git clone https://github.com/salil-gtm/emlov3_assignment_5.git
```

2. Open the repo in VS Code.

```bash 
cd emlov3_assignment_5
code .
```

3. Install the Dev Container Extension in VS Code.

4. Use Command Palette > Dev Container: Build and Open in Container.

This way you will be able to use the dev container for development with all necessary packages installed.

## DVC Setup

1. To track the data folder using DVC, run the following command:

```bash
dvc add data
```

2. To add the data folder to remote storage, run the following command:

```bash
dvc remote add -d local ../dvc_storage
```

3. To push the data folder to remote storage, run the following command:

```bash
dvc push -r local
```

4. To pull the data folder from remote storage, run the following command:

```bash
dvc pull -r local
```

## Training & Evaluation

1. To train the model, run the following command:

```bash
adamantium_train data.num_workers=8 experiment=cat_dog
```

2. To evaluate the model, run the following command:

```bash
adamantium_eval data.num_workers=8 experiment=cat_dog
```

Note: The above commands will run the training & evaluation using the default config file.

## Inference

To run inference on a single image, run the following command:

```bash
adamantium_infer experiment=cat_dog_infer
```

Output includes the class probabilities for the image:

```bash
{'cat': 0.29665568470954895, 'dog': 0.7033442854881287}
```

Note: The above command will run inference on the image mentioned in the config file.

## Past Documentation

- [Assignment 4](https://github.com/salil-gtm/emlov3_assignment_4)

## Author

- Salil Gautam
