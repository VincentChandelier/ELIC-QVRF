# ELIC-QVRF


# Elic: Efficient learned image compression with unevenly grouped space-channel contextual adaptive coding + QVRF: A Quantization-error-aware Variable Rate Framework for Learned Image Compression
Pytorch implementation of the paper "Elic: Efficient learned image compression with unevenly grouped space-channel contextual adaptive coding" + “QVRF: A Quantization-error-aware Variable Rate Framework for Learned Image Compression”

We make the ELIC into variable rate model
This repository is based on [ELiC-ReImplemetation](https://github.com/VincentChandelier/ELiC-ReImplemetation). We kept network scripts, and removed other components. The major changes are provided in `network.py`. For the official code release, see the [ELiC-ReImplemetation](https://github.com/VincentChandelier/ELiC-ReImplemetation).

## About
This repo defines ELIC in varibale rate model for learned image compression in "Elic: Efficient learned image compression with unevenly grouped space-channel contextual adaptive coding" + “QVRF: A Quantization-error-aware Variable Rate Framework for Learned Image Compression”.

## Related links
 * CompressAI: https://github.com/InterDigitalInc/CompressAI
 * ELiC-ReImplemetation：https://github.com/VincentChandelier/ELiC-ReImplemetation
 * QVRF：https://github.com/bytedance/QRAF
 
## Installation


```bash
conda create -n compress python=3.7
conda activate compress
pip install compressai=1.1.5
pip install pybind11
pip install ptflops
```

$$Usage
### Training
stage 1
```
python train.py -d ./dataset  -e 2000 -lr 1e-4 -n 8 --batch-size 8 --test-batch-size 64 --aux-learning-rate 1e-3 --patch-size 256 256 --cuda --save --seed 1926 --clip_max_norm 1.0  --stage 1 --ste 0  --loadFromPretrainedSinglemodel 0
```
stage 2
```
python3 train.py  -d ./dataset  -e 500 -lr 1e-4 -n 8 --batch-size 8 --test-batch-size 64 --aux-learning-rate 1e-3 --patch-size 256 256 --cuda --save --seed 1926 --clip_max_norm 1.0  --stage 2 --ste 0  --refresh 1 --loadFromPretrainedSinglemodel 0 --checkpoint checkpoint_best_loss.pth.tar
```
stage 3
```
python3 train.py  -d ./dataset  -e 500 -lr 1e-4 -n 8 --batch-size 8 --test-batch-size 64 --aux-learning-rate 1e-3 --patch-size 256 256 --cuda --save --seed 1926 --clip_max_norm 1.0  --stage 3 --ste 1 --refresh 1 --loadFromPretrainedSinglemodel 0 --checkpoint checkpoint_best_loss.pth.tar
```

###Inference
```
python3 Inference.py --dataset ./dataset/Kodak --s 8 --output_path ELICVR -p ./checkpoint_best_loss.pth.tar --patch 64 --factormode 0 --factor 0
```
## Citation
```
@inproceedings{he2022elic,
  title={Elic: Efficient learned image compression with unevenly grouped space-channel contextual adaptive coding},
  author={He, Dailan and Yang, Ziming and Peng, Weikun and Ma, Rui and Qin, Hongwei and Wang, Yan},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={5718--5727},
  year={2022}
}

@INPROCEEDINGS{10222717,
  author={Tong, Kedeng and Wu, Yaojun and Li, Yue and Zhang, Kai and Zhang, Li and Jin, Xin},
  booktitle={2023 IEEE International Conference on Image Processing (ICIP)}, 
  title={QVRF: A Quantization-Error-Aware Variable Rate Framework for Learned Image Compression}, 
  year={2023},
  volume={},
  number={},
  pages={1310-1314},
  doi={10.1109/ICIP49359.2023.10222717}}
```
```
