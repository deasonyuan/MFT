:trophy:News: **MFT got the "winning tracker" award at the VOT2018 challenge**
# MFT/MHIT
This repository includes matlab code for reproducing the results on VOT2018 (MFT).

[Multi-hierarchical Independent Correlation Filters for Visual Tracking](http://arxiv.org/abs/1811.10302)

By Shuai Bai, Zhiqun He, Tingbing Xu, Zheng Zhu, Yuan Dong, Hongliang Bai
<img src='img/fig1.png' width='800'>
### Introduction

MFT tracker is the VOT2018 version of MHIT. It is based on correlation filtering algorithm. Firstly, we combine different multi-resolution features with continuous convolution operator~\cite{danelljan2017eco}. Secondly, we train multi-solution independently using different features and fuse multi-solutions optimally to predict target location, which drastically improves robustness. Respectively. At last, we reasonably choose different combinations of Res50, SE-Res50, Hog, CN features as our final feature to adapt to different tracking situation.

<img src='img/vot2017.png' width='800'>


# License
Licensed under an MIT license.


### Usage
* Supported OS: the source code was tested on 64-bit CentOS Linux release 7.3.1611 (Core), and it should also be executable in other linux distributions.
* Dependencies: 
 * A modified version of matconvnet (included in the ./external_libs/matconvnet folder).
 * autonn(https://github.com/vlfeat/autonn) is included in the (./external_libs/autonn) folder.
 * MATLAB 2016b, and all different version will change a lot.
 * Cuda 8.0 enabled GPUs

###  Preparation
cd ./feature_extraction/networks

wget http://www.vlfeat.org/matconvnet/models/imagenet-resnet-50-dag.mat

wget http://www.robots.ox.ac.uk/~albanie/models/se-nets/SE-ResNet-50-mcn.mat

Setting export CUDA_CACHE_MAXSIZE=8000000000" in the ./~bash_profile so that gpuDevice(1) will take fewer time.


## Demo
run demo_MFT.m()

### VOT
[VOT Intergration] ./vot2018_main/MFT.m
change ./tracker_MFT.m
tracker_repo_path = 'your MFT path'
