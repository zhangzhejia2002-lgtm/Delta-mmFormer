# Delta-mmFormer

Delta-mmFormer is a multimodal Transformer framework developed for the CARE 2025 Liver Fibrosis Staging (LiFS) Challenge, addressing MRI-based classification under missing-modality scenarios. Built upon the mmFormer architecture, the framework introduces a Delta-function missing-modality compensation mechanism that calibrates available modality features and synthesizes attenuated proxy representations for missing modalities. This design explicitly accounts for the uncertainty of inferred information and enables robust liver fibrosis staging without relying on external data or lesion segmentation.

## Paper

**Improved mmFormer for Liver Fibrosis Staging via Missing-Modality Compensation**  
Zhejia Zhang, Junjie Wang, Le Zhang  

arXiv: https://arxiv.org/abs/2509.16436

## Method

Delta-mmFormer retains the modality-specific encoders and the modality-correlated Transformer from mmFormer to extract both modality-unique and cross-modal representations. To address missing-modality scenarios commonly encountered in real-world MRI acquisition, a Delta-function compensation module is introduced.

The proposed compensation mechanism performs learnable statistical calibration on available modality features and aggregates them to construct reference tokens. Proxy features for missing modalities are then synthesized from the reference representation and explicitly attenuated to prevent over-reliance on inferred information. The resulting calibrated and attenuated features are fused through a modality-correlated Transformer for final classification.

## Dataset

The model is evaluated on the official CARE 2025 LiFS dataset. The dataset comprises 610 liver fibrosis patients from multiple centers and three MRI vendors. Multi-phase MRI sequences include T2WI, DWI, and Gd-EOB-DTPA–enhanced MRI covering T1WI (non-contrast), arterial, venous, delayed, and hepatobiliary phases.

## Checkpoints

The trained model checkpoints have been properly stored for reproducibility and further evaluation on Google Drive.

**Non-Contrast track**:

Cirrhosis Detection (S1-3 VS S4)  
https://drive.google.com/drive/folders/1r59lZKcGHDUe1_uZWPTVzmxuhYEne7A6?usp=drive_link

Substantial Fibrosis Detection (S1 VS S2–S4)  
https://drive.google.com/drive/folders/1az4shu_EzAmkSpTlYa2R8_wNQKeRbkkz?usp=drive_link

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
