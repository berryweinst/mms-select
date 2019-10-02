# mms-select

This is a complete training example for Deep Convolutional Networks on various datasets (ImageNet, Cifar10, Cifar100, MNIST).

It is based off [imagenet example in pytorch](https://github.com/pytorch/examples/tree/master/imagenet) with helpful additions such as:
  - Training on several datasets other than imagenet
  - Complete logging of trained experiment
  - Graph visualization of the training/validation loss and accuracy
  - Definition of preprocessing and optimization regime for each model
  - Distributed training
 
 To clone:
 ```
 git clone --recursive https://github.com/paper-submissions/mms-select
 ```
 
This code can be used to replicate results from "selective sampling for accelerating  training of deep neural networks"
    
1) Training the resnet44 in Cifar10:
```
python main.py --dataset cifar10 --model resnet --model-config "{'depth': 44, 'regime':'normal_selective'}" -b 64 --epochs 2000 --save resnet44_cifar10_select_mms --device-ids 0 -sb 640
```
1) Training the WRN-28-10 on Cifar100:
```
python main.py --dataset cifar100 --model resnet --model-config "{'depth': 28, 'width': [160, 320, 640], 'regime':'resnet-wide_selective'}" -b 64 --epochs 2000 --save resnet28_wide_cifar100_select_mms --device-ids 1 --cutout --autoaugment -sb 640
```

## Dependencies

- [pytorch](<http://www.pytorch.org>)
- [torchvision](<https://github.com/pytorch/vision>) to load the datasets, perform image transforms
- [pandas](<http://pandas.pydata.org/>) for logging to csv
- [bokeh](<http://bokeh.pydata.org>) for training visualization


## Data
- Configure your dataset path with ``datasets-dir`` argument
- To get the ILSVRC data, you should register on their site for access: <http://www.image-net.org/>
