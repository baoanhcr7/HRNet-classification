# High-resolution networks (HRNets) for Image classification

- [Root Reponsitory](https://github.com/HRNet/HRNet-Image-Classification)
- [Root Paper](https://arxiv.org/pdf/1908.07919.pdf)

## Update 
  1. Remove all version of requirements.txt
  2. Replace ".size " with ".reshape" in file 'HRNet-Image-Classification/lib/core/evaluate.py'
  3. If you train on collab with sigle GPU you must  change to "GPUS: (0,)" in config file 
   ``` bash
   Exp: HRNet-Image-Classification/experiments/cls_hrnet_w18_sgd_lr5e-2_wd1e-4_bs32_x100.yaml
            Line 1: GPUS: (0,1,2,3) => GPUS: (0,)
  ```
### Data preparation
 1. Train data should be under '/HRNet-Image-Classification/imagenet/images/train'
 1. Test data should be under '/HRNet-Image-Classification/imagenet/images/test'
 1. Val data should be under '/HRNet-Image-Classification/imagenet/images/val'
### Train and test
Please specify the configuration file.

For example, train the HRNet-W18 on ImageNet with a batch size of 128 on 1 GPUs:
````bash
python tools/train.py --cfg experiments/cls_hrnet_w18_sgd_lr5e-2_wd1e-4_bs32_x100.yaml
````

For example, test the HRNet-W18 on ImageNet on 1 GPUs:
````bash
python tools/valid.py --cfg experiments/cls_hrnet_w18_sgd_lr5e-2_wd1e-4_bs32_x100.yaml --testModel hrnetv2_w18_imagenet_pretrained.pth
````
