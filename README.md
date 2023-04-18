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


## Citation
```
@inproceedings{he2022elic,
  title={Elic: Efficient learned image compression with unevenly grouped space-channel contextual adaptive coding},
  author={He, Dailan and Yang, Ziming and Peng, Weikun and Ma, Rui and Qin, Hongwei and Wang, Yan},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={5718--5727},
  year={2022}
}

@article{tong2023qvrf,
  title={QVRF: A Quantization-error-aware Variable Rate Framework for Learned Image Compression},
  author={Tong, Kedeng and Wu, Yaojun and Li, Yue and Zhang, Kai and Zhang, Li and Jin, Xin},
  journal={arXiv preprint arXiv:2303.05744},
  year={2023}
}
```
