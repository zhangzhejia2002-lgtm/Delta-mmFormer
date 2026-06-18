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

**Contrast track**:

Cirrhosis Detection (S1-3 VS S4)  
https://drive.google.com/drive/folders/17-I36mVvuftEaw8Wz-OZXQgUmidNRPVg?usp=sharing

Substantial Fibrosis Detection (S1 VS S2–S4)  
https://drive.google.com/drive/folders/1m3OLWHy-VZjxMoGQ3DTPPAVtBL5GvtcR?usp=sharing

## License

This project is released under the Apache License 2.0.

## Citation

If you find this work useful, please cite:

```bibtex
@InProceedings{10.1007/978-3-032-16271-7_17,
author="Zhang, Zhejia
and Wang, Junjie
and Zhang, Le",
editor="Zhuang, Xiahai
and Ding, Wangbin
and Liu, Yuanye
and Ma, Yingliang
and Zhao, Jichao
and Wang, Bomin",
title="Improved mmFormer for Liver Fibrosis Staging via Missing-Modality Compensation",
booktitle="Comprehensive Analysis and Computing of Real-World Medical Images",
year="2026",
publisher="Springer Nature Switzerland",
address="Cham",
pages="180--189",
abstract="In real-world clinical settings, magnetic resonance imaging (MRI) frequently suffers from missing modalities due to equipment variability or patient cooperation issues, which can significantly affect model performance. To address this issue, we propose a multimodal MRI classification model based on the mmFormer architecture with an adaptive module for handling arbitrary combinations of missing modalities. Specifically, this model retains the hybrid modality-specific encoders and the modality-correlated encoder from mmFormer to extract consistent lesion features across available modalities. In addition, we integrate a missing-modality compensation module which leverages zero-padding, modality availability masks, and a Delta Function with learnable statistical parameters to dynamically synthesize proxy features for recovering missing information. To further improve prediction performance, we adopt a cross-validation ensemble strategy by training multiple models on different folds and applying soft voting during inference. This method is evaluated on the test set of Comprehensive Analysis {\&} Computing of REal-world medical images (CARE) 2025 challenge, targeting the Liver Fibrosis Staging (LiFS) task based on non-contrast dynamic MRI scans including T1-weighted imaging (T1WI), T2-weighted imaging (T2WI), and diffusion-weighted imaging (DWI). For Cirrhosis Detection and Substantial Fibrosis Detection on in-distribution vendors, our model obtains accuracies of 66.67{\%} and 74.17{\%}, and corresponding area under the curve (AUC) scores of 71.73{\%} and 68.48{\%}, respectively.",
isbn="978-3-032-16271-7"
}
