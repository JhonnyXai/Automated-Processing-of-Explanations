# Automated-Processing-of-Explanations
This work proposes a novel methodology that processes GradCAM explanations with Deep Semi-Supervised Anomaly Detection to automatically identify anomalous explanations that deviate from explanations of correctly classified images. 

# Citation and Contact

# Abstract

# The need for Automated-Processing-of-Explanations
# Installation
This code is written in Python 3.7 and requires the packages listed in requirements.txt.

Clone the repository to your machine and directory of choice:


```
git clone https://github.com/JhonnyXai/Automated-Processing-of-Explanations.git
```

To run the code, we recommend setting up a virtual environment, e.g. using conda:

## `conda`
```
cd <path-to-APEXP-PyTorch-directory>
conda create --name myenv
source activate myenv
while read requirement; do conda install -n myenv --yes $requirement; done < requirements.txt
```
# Running experiments
We have implemented the [`IDID`](https://ieee-dataport.org/competitions/insulator-defect-detection) dataset, from IEEE as reported in the paper. 
