# Pixel-wise Warping for Video Stabilization (PWNet)
This is a [PyTorch](http://pytorch.org/) implementation of Pixel-wise Warping for Video Stabilization.

Source code and models will be opened soon!

If you have any questions, please contact with me:
zmd1992@mail.ustc.edu.cn

### Table of Contents
- <a href='#Prerequisites'>Prerequisites</a>
- <a href='#datasets'>Datasets</a>
- <a href='#training-ssd'>Train</a>
- <a href='#performance'>Performance</a>
- <a href='#demos'>Demos</a>
- <a href='#references'>Reference</a>

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Prerequisites
- Linux
- Python 3
- NVIDIA GPU (12G or 24G memory) + CUDA cuDNN
- pytorch 0.4.0+
- numpy
- cv2

## Datasets
The dataset for is the DeepStab dataset (7.9GB) http://cg.cs.tsinghua.edu.cn/download/DeepStab.zip thanks to Miao Wang [1]. 

## Training 
- First download the fc-reduced [VGG-16](https://arxiv.org/abs/1409.1556) PyTorch base network weights at:              https://s3.amazonaws.com/amdegroot-models/vgg16_reducedfc.pth
- By default, we assume you have downloaded the file in the `/weights` dir:

```Shell
mkdir weights
cd weights
wget https://s3.amazonaws.com/amdegroot-models/vgg16_reducedfc.pth
```

- To train PWNet using the train script simply specify the parameters listed in `./lib/cfg.py` as a flag or manually change them.
- The default parameters are set for the use of two NVIDIA 1080Ti graphic cards with 24G memory.

```Shell
CUDA_VISIBLE_DEVICES=0,1 python3 main.py
```

- Note:
  * For training, an NVIDIA GPU is strongly recommended for speed.
  * Before training, you should ensure the location of preprocessed dataset, which will be supplied soon.

## Evaluation
To evaluate a trained network:

```Shell
python eval.py
```

You can specify the parameters listed in the `eval.py` file by flagging them or manually changing them.


## Performance

Detailed performance can be seen in our paper.
- Pixel-wise Warping for Video Stabilization with
Deep Generative Adversarial Networks



## Demos

### Use a pre-trained PWNet for video stabilization

#### Download a pre-trained network
- We are trying to provide a pre-trained model.
- Currently, we provide the following PyTorch models:
       model wil be opened soon!
- You can test your own unstable videos by changing the parameter "train" with False and adjust the path yourself in function "process()".
    




## Authors
- Minda Zhao

## References
[1] M. Wang, G.-Y. Yang, J.-K. Lin, S.-H. Zhang, A. Shamir, S.-P. Lu,
and S.-M. Hu, “Deep online video stabilization with multi-grid warp-
ing transformation learning,” IEEE Transactions on Image Processing,
vol. 28, no. 5, pp. 2283–2292, 2019