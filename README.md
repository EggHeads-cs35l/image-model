# image-model
ML image model for detecting vehicles in an image
## Setup development environment
---
Clone the repo using:
```sh
git clone https://github.com/EggHeads-cs35l/image-model.git
```
For the rest of the setup, navigate to the cloned directory and run commands there.

We will be using Conda (Miniconda) to create our development environment: https://anaconda.org

Next, update conda by running:
```sh
conda update -n base -c defaults conda
```

### Step 1: Install Miniconda
Navigate to the miniconda installer page and download your correpsonding file: https://docs.conda.io/en/latest/miniconda.html

The process will enitrely depend on your development platform: Windows, WSL, MacOS, Linux.

Regardless of platform, we recommend installing via the bash script: simply run the downloaded script with the prefix `bash <FILE>`

### Step 2: Create Conda environment
Refer to the Conda cheat sheet for help with commands: https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf

Run the following commands to setup a conda environment:

Make sure to replace "\<NAME\>" with the actual name of the environemnt you wish to create.
```bah
conda create --name <NAME> python=3.9
```
We will be using Python 3.9.

You can activate and deactivate your conda environment using:
```bash
conda activate <NAME>
conda deactivate
```
or
```bash
source activate <NAME>
source deactivate
```
---
# **IMPORTANT: From now on, make sure you activate your conda envrironment**
---
### Step 3 (Only for MacOS): Set Up Apple Metal

If you are using MacOS, we recommend using Apple Metal to enhance training using your GPU on Intel Macs or GPU cores on the new Apple Silicon: https://developer.apple.com/metal/tensorflow-plugin/

If you are on an Apple silicon Mac, run the following command first:
```sh
conda install -c apple tensorflow-deps
```

If you are on MacOS (either Intel or Apple silicon), run these commands:

install TensorFlow for MacOS
```sh
python -m pip install tensorflow-macos
```
install Metal fro TensorFlow
```sh
python -m pip install tensorflow-metal
```

### Step 4: Install dependencies
We will be using TensorFlow for our ML framework: https://www.tensorflow.org

Run the following command (in the directory) to install dependencies:
```sh
conda install numpy pandas matplotlib
conda install -c conda-forge tensorflow pillow
conda install -c anaconda ipykernel
```

### Step 5: Donwload the dataset
We will use the Stanford Cars Dataset: http://ai.stanford.edu/~jkrause/cars/car_dataset.html
>**3D Object Representations for Fine-Grained Categorization**
>
>*Jonathan Krause, Michael Stark, Jia Deng, Li Fei-Fei*
>
>*4th IEEE Workshop on 3D Representation and Recognition, at ICCV 2013 (3dRR-13). Sydney, Australia. Dec. 8, r013.*

run the following commands:
```sh
mkdir data
cd data
mkdir images
curl http://ai.stanford.edu/~jkrause/car196/car_ims.tgz > car_ims.tgz
curl http://ai.stanford.edu/~jkrause/car196/cars_annos.mat > cars_annos.mat
tar -xzf car_ims.tgz -C images/
```

### Now you are ready to develop!
