# DAPNet: multi-view graph contrastive network incorporating disease clinical and molecular associations for disease progression prediction

## 1. Introduction

This repository contains source code and datasets for paper "[DAPNet: multi-view graph contrastive network incorporating disease clinical and molecular associations for disease progression prediction](https://link.springer.com/article/10.1186/s12911-024-02756-0)". In this study, we proposed DAPNet, a deep learning-based disease progression prediction model that solely utilizes the comorbidity duration (without relying on multi-modal data or comprehensive medical records) and disease associations from biomedical knowledge graphs to deliver high-performance prediction. DAPNet is the first to apply multi-view graph contrastive learning to disease progression prediction tasks. Compared with other studies on comorbidities, DAPNet innovatively integrates molecular-level disease association information, combines disease co-occurrence and ICD-10, and fully explores the associations between diseases;

## 2. Overview
![Fig1-20240114](https://github.com/user-attachments/assets/a2a6622e-457c-478c-b938-4d8fd96dd41a)

Fig. 1 Overview of disease progression prediction framework. A Clinical representation module based on clinical features. B Network representation module based on multi-source disease association networks. C Feature fusion and disease progression prediction module
## 3. A Quick Start
Before our program runs, we need to make some preparations.

### Install Python libraries needed


```shell
$ conda create -n DP python=3.7
$ conda activate DP
$ pip install -r requirements.txt
```
We recommend using version 1.15 of TensorFlow 1.

## 4. Basic Usage
### Diseases network
Based on the relationship data of diseases, this study sorted and constructed three disease networks from different perspectives. The construction process is detailed in section 2.1 of the paper. Although their sources are different, the file format is consistent. For each network, we need
- Adjacency matrix(data/adj_matrix.csv). And their row and column sizes are the same.
- Feature matrix(data/Graph_embeddingfull.npy). The rows correspond to the number of diseases, and the columns correspond to initial weights, such as text embedding.

### Datasets
To better represent the phenotypes of patients, this study proposed a new method for calculating illness duration to reflect the impact of disease duration. The process of constructing the dataset is detailed in section 2.2 of the paper, and the codes are in the  '/pre' folder. The final file can refer to 'data/train_demo'.csv.

### Running
Jump to /model folder, and run the Python file.
```shell
nohup python -u train.py > DAPNet.txt 2>&1 &
```
## 5. Citation and Contact
If you find PresRecST useful for your research, please consider citing the following paper:

Tian, H., He, X., Yang, K. et al. DAPNet: multi-view graph contrastive network incorporating disease clinical and molecular associations for disease progression prediction. BMC Med Inform Decis Mak 24, 345 (2024). https://doi.org/10.1186/s12911-024-02756-0

@article{tian2024dapnet,
  title={DAPNet: multi-view graph contrastive network incorporating disease clinical and molecular associations for disease progression prediction},
  author={Tian, Haoyu and He, Xiong and Yang, Kuo and Dai, Xinyu and Liu, Yiming and Zhang, Fengjin and Shu, Zixin and Zheng, Qiguang and Wang, Shihua and Xia, Jianan and others},
  journal={BMC Medical Informatics and Decision Making},
  volume={24},
  number={1},
  pages={345},
  year={2024},
  publisher={Springer}
}
