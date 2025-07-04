# ReDiffDet

> [ReDiffDet: Rotation-equivariant Diffusion Model for Oriented Object Detection](https://openaccess.thecvf.com/content/CVPR2025/html/Zhao_ReDiffDet_Rotation-equivariant_Diffusion_Model_for_Oriented_Object_Detection_CVPR_2025_paper.html)

The baseline of ReDiffDet is avaliable at [ai4rs](https://github.com/wokaikaixinxin/ai4rs/blob/main/projects/GSDet_baseline/README_ReDiffDet_baseline.md)

## Abstract

<div align=center>
<img src="./rediffdet_overview.png" width="800"/>
</div>

The diffusion model has been successfully applied to various detection tasks. However, it still faces several challenges when used for oriented object detection: objects that are arbitrarily rotated require the diffusion model to encode their orientation information; uncontrollable random boxes inaccurately locate objects with dense arrangements and extreme aspect ratios; oriented boxes result in the misalignment between them and image features. To overcome these limitations, we propose ReDiffDet, a framework that formulates oriented object detection as a rotation-equivariant denoising diffusion process. First, we represent an oriented box as a 2D Gaussian distribution, forming the basis of the denoising paradigm. The reverse process can be proven to be rotation-equivariant within this representation and model framework. Second, we design a conditional encoder with conditional boxes to prevent boxes from being randomly placed across the entire image. Third, we propose an aligned decoder for alignment between oriented boxes and image features. The extensive experiments demonstrate ReDiffDet achieves promising performance and significantly outperforms the diffusion-based baseline detector.



## Insight

- 模型能将随机输入学习得到目标。随机输入都可行，其他类型的输入大概率也是可行的。
- 旋转框可以表征为概率分布，如高斯分布。万物都可以表征为不同的概率分布。
- 扩散模型、高斯泼溅等都涉及概率分布，都涉及随机性。
- 架构是decoder-only型，由多层decoder layer堆叠。代码借用了openmmlab 中two-stage类作为父类，事实上，将one-stage或transformer作为父类都可以。

- The model can learn targets from random inputs. If random inputs work, other types of inputs are likely feasible as well.  
- Rotated boxes can be represented as probability distributions, such as Gaussian distributions. Everything can be characterized by different probability distributions.  
- Diffusion models, Gaussian splatting, etc., all involve probability distributions and randomness.  
- The architecture is decoder-only, stacked with multiple decoder layers. The code borrows the two-stage class from OpenMMLab as the parent class, though using one-stage or Transformer as the parent is also possible.


## Citation

```
@inproceedings{zhao2025rediffdet,
  title={ReDiffDet: Rotation-equivariant Diffusion Model for Oriented Object Detection},
  author={Zhao, Jiaqi and Ding, Zeyu and Zhou, Yong and Zhu, Hancheng and Du, Wen-Liang and Yao, Rui},
  booktitle={Proceedings of the Computer Vision and Pattern Recognition Conference},
  pages={24429--24439},
  year={2025}
}
```