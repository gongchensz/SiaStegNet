# SiaStegNet Pytorch
A Siamese CNN for Image Steganalysis

## Overview
This repository contains a implementation of SiaStegNet, along with pre-trained models and examples.

We hope that our SiaStegNet design can provide some inspiration for future research in arbitrary-size image steganalysis, although a specific methodology of this novel framework has yet to be developed.

## Table of contents
1. About SiaStegNet
2. Usage

### About SiaStegNet
***Abstract*** Image steganalysis is a technique for detecting data hidden in images. Recent research has shown the powerful capabilities of using convolutional neural networks (CNN) for image steganalysis. However, due to the particularity of steganographic signals, there are still few reliable CNN-based methods for applying steganalysis to images of arbitrary size. In this paper, we address this issue by exploring the possibility of exploiting a network for steganalyzing images of varying sizes without retraining its parameters. On the assumption that natural image noise is similar between different image sub-regions, we propose an end-to-end, deep learning, novel solution for distinguishing steganography images from normal images that provides satisfying performance. The proposed network first takes the image as the input, then identifies the relationships between the noise of different image sub-regions, and, finally, outputs the resulting classification based upon them. Our algorithm adopts a Siamese, CNN-based architecture, which consists of two symmetrical subnets with shared parameters, and contains three phases: preprocessing, feature extraction, and fusion/classification. To validate the network, we generated datasets composed of steganography images with multiple sizes and their corresponding normal images sourced from BOSSbase 1.01 and ALASKA #2. Experimental results produced by the data generated by various methods show that our proposed network is well-generalized and robust.

### Usage
#### Quickstart
```
python train.py --train-cover-dir ... --val-cover-dir ... --train-stego-dir ... --val-stego-dir ... --model kenet --ckpt-dir ...
```
(''kenet'' is the SiaStegNet, because my name is ''ke''. ^_^)
#### Other Parameters
* --epoch
* --lr
* --wd
* --eps
* --alpha Two supervised signals (cross-entropy loss and contrastive loss) are weighted by hyperparameter λ (i.e., alpha) in the loss function used for SiaStegNet. default=0.1.
* --margin The margin of contrastive loss. defalut=1.
* --random-crop Obtain random rectangular patches of random sizes.
* --random-crop-train Random crop & On-the-fly embedding (Very Expensive!).
* --batch-size default=32
* --num-workers
* --finetune Load a pretrained model
* --gpu-id
* --seed
* --log-interval
* --lr-strategy

To be continued
