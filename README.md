example for SELECTIVE SAMPLING FOR ACCELERATING THE TRAINING  OF DEEP NEURAL NETWORKS:
 
 1) CIFAR10:
 ```
 python main.py --dataset cifar10 --model resnet --model-config "{'depth': 44, 'regime':'normalselective'}" -b 64 --epochs 2000 --save resnet44_cifar10_accelerate --device-ids 3 -sb 640
```
 2) CIFAR100:
 ```
 python main.py --dataset cifar100 --model resnet --model-config "{'depth': 28, 'regime':'wide-resnet_selective','width': [160, 320, 640]}" -b 64 --epochs 2000 --save resnet28_wide_cifar100_accelerate --device-ids 3 --autoaugment --cutout -sb 640
```
