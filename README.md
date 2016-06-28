# GRU-PredNet
This is a [GRU][] version of [PredNet][] based on [quadjr/PredNet](https://github.com/quadjr/PredNet).

[PredNet]: http://arxiv.org/abs/1605.08104 "Lotter, William, Gabriel Kreiman, and David Cox. \"Deep Predictive Coding Networks for Video Prediction and Unsupervised Learning.\" arXiv preprint arXiv:1605.08104 (2016)."

[GRU]: https://arxiv.org/abs/1412.3555 "Junyoung Chung, Caglar Gulcehre, KyungHyun Cho, Yoshua Bengio \"Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling\" arXiv:1412.3555 (2014)."

ConvLSTM is replaced by ConvGRU, the others are the same as the original version.

## Note
Comparing output-images between this version and original one about images in image_02 in 2011_09_26_drive_0001_sync.zip of KITTI showed some differences, the effectiveness is under investigation.

## Testd on
* Ubuntu 14.04  
* Python 2.7.6  
* chainer 1.9.1  
* CUDA Toolkit 7.5  
* cuDNN v5  

## Usage
1. Train  
On a CPU  
$ python main.py -i dataset/train_list.txt  
On a GPU 0
$ python main.py -i dataset/train_list.txt -g 0  
  
Model files and some images will be generated in models/ and images/ directory.   
Image suffix means x (input), y (predicted), z (correct).  

2. Test  
$ python main.py -i dataset/test_list.txt --test --initmodel models/???.model  
Plase specify the model file with option --initialmodel.  
Test result will be generated in images/ directory.  
Image suffix means x (input), y (predicted).  
