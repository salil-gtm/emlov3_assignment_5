# EMLOv3 | Assignment 4

[![pytorch](https://img.shields.io/badge/PyTorch_2.0+-ee4c2c?logo=pytorch&logoColor=white)](https://pytorch.org/get-started/locally/)
[![lightning](https://img.shields.io/badge/-Lightning_2.0+-792ee5?logo=pytorchlightning&logoColor=white)](https://pytorchlightning.ai/)
[![hydra](https://img.shields.io/badge/Config-Hydra_1.3-89b8cd)](https://hydra.cc/)
[![black](https://img.shields.io/badge/Code%20Style-Black-black.svg?labelColor=gray)](https://black.readthedocs.io/en/stable/)


## Adamantium 

<em>The name is inspired by the metal alloy which is bonded to the character Wolverine's skeleton and claws.</em>

Adamantium is a custom python package which currently supports usage of any model available in TIMM for training & evalution on CIFAR10 dataset. All functionalities can be controlled by hydra configs.

The setup can be run in two ways:

## Using Dev Container

1. Clone the repository.

```bash
git clone https://github.com/salil-gtm/emlov3_assignment_4.git
```

2. Open the repo in VS Code.

```bash 
cd emlov3_assignment_4
code .
```

3. Install the Dev Container Extension in VS Code.

4. Use Command Palette > Dev Container: Build and Open in Container.

5. Now you can use the terminal in VS Code to run the commands mentioned below.

Training can be done using the following commands:

```bash
python adamantium/train.py data.num_workers=4
```

Evaluation can be done using the following commands:

```bash
python adamantium/eval.py data.num_workers=4
```

Note: The above commands will run the training & evaluation using the default config file.


## Using Docker Image

1. Pull the docker image.

```bash
docker pull salilgtm/emlov3_assignment_4:latest
```

2. To run the docker image for training & evaluation, use the following command:

```bash
docker run -it salilgtm/emlov3_assignment_4:latest sh -c "python adamantium/train.py data.num_workers=4 && python adamantium/eval.py data.num_workers=4"
```

Note: The above commands will run the training & evaluation using the default config file.


## Config Structure

```bash
.
├── __init__.py
├── data
│   └── cifar10.yaml
├── eval.yaml
├── hydra
│   └── default.yaml
├── model
│   └── hf.yaml
├── paths
│   └── default.yaml
├── train.yaml
└── trainer
    ├── cpu.yaml
    └── default.yaml

5 directories, 9 files
```

Paramters can be overriden by passing them as arguments to the command line. For example, to change the batch size, use the following command:

```bash
python adamantium/train.py data.num_workers=4 data.batch_size=64
```

## Author

- Salil Gautam
