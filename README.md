# Automated-Processing-of-Explanations
This work proposes a novel methodology that processes GradCAM explanations with Deep Semi-Supervised Anomaly Detection to automatically identify anomalous explanations that deviate from explanations of correctly classified images. 

## Citation and Contact

## Abstract

## The need for Automated-Processing-of-Explanations
## Installation
This code is written in Python 3.7 and requires the packages listed in requirements.txt.

Clone the repository to your machine and directory of choice:


```
git clone https://github.com/JhonnyXai/Automated-Processing-of-Explanations.git
```

To run the code, we recommend setting up a virtual environment, e.g. using conda:

### `conda`
```
cd <path-to-APEXP-PyTorch-directory>
conda create --name myenv
source activate myenv
while read requirement; do conda install -n myenv --yes $requirement; done < requirements.txt
```
# Running experiments
We have implemented the [`IDID`](https://ieee-dataport.org/competitions/insulator-defect-detection) dataset, from IEEE as reported in the paper. 
## Deep SAD
You can run Deep SAD experiments using the `main.py` script.    

Here's an example on `MNIST` with `0` considered to be the normal class and having 1% labeled (known) training samples 
from anomaly class `1` with a pollution ratio of 10% of the unlabeled training data (with unknown anomalies from all 
anomaly classes `1`-`9`):
```
cd <path-to-Deep-SAD-PyTorch-directory>

# activate virtual environment
source myenv/bin/activate  # or 'source activate myenv' for conda

# create folders for experimental output
mkdir log/DeepSAD
mkdir log/DeepSAD/mnist_test

# change to source directory
cd src

# run experiment
python main.py mnist mnist_LeNet ../log/DeepSAD/mnist_test ../data --ratio_known_outlier 0.01 --ratio_pollution 0.1 --lr 0.0001 --n_epochs 150 --lr_milestone 50 --batch_size 128 --weight_decay 0.5e-6 --pretrain True --ae_lr 0.0001 --ae_n_epochs 150 --ae_batch_size 128 --ae_weight_decay 0.5e-3 --normal_class 0 --known_outlier_class 1 --n_known_outlier_classes 1;
```
Have a look into `main.py` for all possible arguments and options.
