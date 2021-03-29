-----------
 This repo is used to share the implementations of our paper **Unsupervised Cross-Modality Adaptation with Consistency-regularized Appearance and Uncertainty-aware Feature Alignment for Medical Image Segmentation**.<br/>
-----------

## Paper
[Unsupervised Cross-Modality Adaptation with Consistency-regularized Appearance and Uncertainty-aware Feature Alignment for Medical Image Segmentation]
<br/>
IEEE Transactions on Image Processing
<br/>
<br/>
<p align="center">
  <img src="img/pipeline4.jpg">
</p>

## Installation
* Install TensorFlow 1.10 and CUDA 9.0
* Clone this repo
```
git clone https://github.com/zongdaoming/cruea
cd cruea
```

# Environments



## Data Preparation
* Raw data needs to be written into `tfrecord` format to be decoded by `./data_loader.py`. The training data can be downloaded [here](https://drive.google.com/file/d/1m9NSHirHx30S8jvN0kB-vkd7LL0oWCq3/view). The testing CT data can be downloaded [here](https://drive.google.com/file/d/1SJM3RluT0wbR9ud_kZtZvCY0dR9tGq5V/view). The testing MR data can be downloaded [here](https://drive.google.com/file/d/1RNb-4iYWUaFBY61rFAnT2XT0mtwlnH1V/view).

* Put `tfrecord` data of two domains into corresponding folders under `./data` accordingly.
* Run `./create_datalist.py` to generate the datalists containing the path of each data.

## Code Structure
```shell
├── include
│   └── add2.h # header file of add2 cuda kernel
├── kernel
│   └── add2_kernel.cu # add2 cuda kernel
├── pytorch
│   ├── add2_ops.cpp # torch wrapper of add2 cuda kernel
│   ├── time.py # time comparison of cuda kernel and torch
│   ├── train.py # training using custom cuda kernel
│   ├── setup.py
│   └── CMakeLists.txt
├── tensorflow
│   ├── add2_ops.cpp # tensorflow wrapper of add2 cuda kernel
│   ├── time.py # time comparison of cuda kernel and tensorflow
│   ├── train.py # training using custom cuda kernel
│   └── CMakeLists.txt
├── LICENSE
└── README.md
```


## Train
* Modify paramter values in `./config_param.json`
* Run `./main.py` to start the training process

## Evaluate
* Specify the model path and test file path in `./evaluate.py`
* Run `./evaluate.py` to start the evaluation.

## Todo List
:bowtie:

- [x] Tensorflow Impletation  :full_moon_with_face:
- [x] Function Wrapper :full_moon_with_face:
- [x] Code Tree :full_moon_with_face:
- [ ] Pytorch Impletation  :new_moon_with_face:
- [ ] Adding More Backbone :new_moon_with_face:
- [:new_moon_with_face:] Pre-training weight Upload  


## Note
* The repository is being updated
* Contact: Daoming Zong (ecnuzdm@gmail.com)



## Acknowledgement
Part of the code is borrowed from the Tensorflow implementation of [CycleGAN](https://github.com/leehomyc/cyclegan-1) and [SIFA](https://github.com/cchen-cc/SIFA).
