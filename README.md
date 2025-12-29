# Delta-mmFormer

Delta-mmFormer is a multimodal Transformer framework developed for the CARE 2025 Liver Fibrosis Staging (LiFS) Challenge, addressing MRI-based classification under missing-modality scenarios. Built upon the mmFormer architecture, the framework introduces a Delta-based missing-modality compensation mechanism that calibrates available modality features and synthesizes attenuated proxy representations for missing modalities. This design explicitly accounts for the uncertainty of inferred information and enables robust liver fibrosis staging without relying on external data or lesion segmentation.

## Paper

Improved mmFormer for Liver Fibrosis Staging via Missing-Modality Compensation  
Zhejia Zhang, Junjie Wang, Le Zhang  

arXiv: https://arxiv.org/abs/2509.16436

## Method Overview

Delta-mmFormer retains the modality-specific encoders and the modality-correlated Transformer from mmFormer to extract both modality-unique and cross-modal representations. To address missing-modality scenarios commonly encountered in real-world MRI acquisition, a Delta-based compensation module is introduced.

The proposed compensation mechanism performs learnable statistical calibration on available modality features and aggregates them to construct reference tokens. Proxy features for missing modalities are then synthesized from the reference representation and explicitly attenuated to prevent over-reliance on inferred information. The resulting calibrated and attenuated features are fused through a modality-correlated Transformer for final classification.

## Dataset and Task

The model is evaluated on the official CARE 2025 LiFS dataset, which consists of non-contrast and contrast MRI scans including T1-weighted imaging (T1WI), T2-weighted imaging (T2WI), and diffusion-weighted imaging (DWI). The task focuses on liver fibrosis staging under arbitrary missing-modality conditions, following the challenge protocol.

## License

This project is released under the Apache License 2.0.

## Citation

If you find this work useful, please cite:

```bibtex
@article{zhang2025improved,
  title={Improved mmFormer for Liver Fibrosis Staging via Missing-Modality Compensation},
  author={Zhang, Zhejia and Wang, Junjie and Zhang, Le},
  journal={arXiv preprint arXiv:2509.16436},
  year={2025}
}
