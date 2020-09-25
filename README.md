<h1 align="center">Dirichlet-Derived Multiple Topic Scene Classification Model (DMTM)</h1>
<h5 align="center">Dirichlet-Derived Multiple Topic Scene Classification Model Fusing Heterogeneous Features for High Resolution Remote Sensing Imagery</h5>

<h5 align="right">by <a>Bei Zhao</a>, <a href="http://rsidea.whu.edu.cn/">Yanfei Zhong</a>,  <a href="http://www.captain-whu.com/xia.html">Guisong Xia</a>, and <a href="http://www.lmars.whu.edu.cn/prof_web/zhangliangpei/rs/index.html">Liangpei Zhang</a></h5>


This is an official implementation of DMTM in our TGRS 2016 paper ["Dirichlet-Derived Multiple Topic Scene Classification Model Fusing Heterogeneous Features for High Resolution Remote Sensing Imagery"](https://ieeexplore.ieee.org/document/7329997).

Abstract

Due to the complex arrangements of the ground objects in high spatial resolution (HSR) imagery scenes, HSR imagery scene classification is a challenging task, which is aimed at bridging the semantic gap between the low-level features and high-level semantic concepts. A combination of multiple complementary features for HSR imagery scene classification is considered to be a potential way to improve the performance. However, the different types of features have different characteristics, and how to fuse the different types of features is a classic problem. In this paper, a Dirichlet-derived multiple topic model (DMTM) is proposed to fuse heterogeneous features at a topic level for HSR imagery scene classification. An efficient algorithm based on a variational expectation-maximization framework is developed to infer the DMTM and estimate the parameters of the DMTM. The proposed DMTM scene classification method is able to incorporate different types of features with different characteristics, no matter whether these features are local or global, discrete or continuous. Meanwhile, the proposed DMTM can also reduce the dimension of the features representing the HSR images. In our experiments, three types of heterogeneous features—local spectral features, local structural features, and global textural features—were employed. The experimental results with three different HSR imagery datasets show that the three types of features are complimentary, and the proposed DMTM is able to reduce the dimension of the features representing the HSR images, fuse the different types of features efficiently, and improve the performance of the scene classification over that of other scene classification algorithms based on spatial pyramid matching (SPM), probabilistic latent semantic analysis (PLSA), and latent Dirichlet allocation (LDA).


## News
1. 2020/08/28, We release the code of DMTM.


## Features
1.  Combine the spectral, structural and texture information
2.  Incorporate different types of features with different characteristics at a topic level for HSR imagery scene classification.


## Citation
If you use DMTM in your research, please cite the following paper:
```text
@article{article,
author = {Zhao, Bei and Zhong, Yanfei and Xia, Guisong and Zhang, Liangpei},
year = {2016},
month = {04},
pages = {2108-2123},
title = {Dirichlet-Derived Multiple Topic Scene Classification Model Fusing Heterogeneous Features for High Resolution Remote},
volume = {54},
journal = {IEEE Transactions on Geoscience and Remote Sensing},
doi = {10.1109/TGRS.2015.2496185}
}
```
 

## Getting Started
### 1. Installation
System Requirements: linux

Compiler Environment:
```bash
cd DMTM/code/topic_model/code
run make
```
The “HOME” path in the makefile should be changed to the path of DMTM/code/topic_model/code
### 2. Prepare datasets

The project should be organized as:
```text
DMTM
├── code
│   ├── feat_coding       /feature coding
│   ├── libsvm-3.20       //tools of SVM classifier
│   ├── scenefeature      //feature extraction
│   ├── topic_model       //LDA for scene classification
│   ├── util
│   ├── vlfeat-0.9.17       //tools of K-means
│   ├── demo_cal_MeanStd_KM.m
│   ├── demo_cal_SIFT_KM.m
│   ├── demo_cal_Texture_KM.m
│   ├── DMTM_main.m
├── data        // dataset
│   ├── Google dataset of SIRI-WHU (http://rsidea.whu.edu.cn/resource_sharing.htm)

```

### 3. run experiments

#### 1. Scene feature extraction
```bash
run 'DMTM_main.m'
```
Meaning of Variables:

"12class_tif": a folder for storing image data
image_data_dir: the path of "12class_tif" , the folder name in the path cannot have spaces.
out_meanstd_feature_dir, out_sift_feature_dir, out_siti_feature_dir, : The output path of final feature 

*The folder name in the path cannot have spaces.

*Texture feature extraction (siti) needs to be carried out in the c++ 2010 environment.

#### 2. Scene classification by SVM
```bash
cd DMTM/code/topic_model
run  './mflda dmtm_google.txt'  (dmtm_google.txt is the configuration file)
```


### License
The copyright belongs to Intelligent Data Extraction, Analysis and Applications of Remote Sensing(RSIDEA) academic research group,State Key Laboratory of Information Engineering in Surveying, Mapping, and Remote Sensing (LIESMARS),Wuhan University. This program is for academic use only. For commercial use, please contact Professor.Zhong(zhongyanfei@whu.edu.cn). The homepage of RSIDEA is: http://rsidea.whu.edu.cn/index.html