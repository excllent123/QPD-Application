## Why Quad‑Pixel (QPD)?

Quad‑Photodiode (Quad‑Pixel) sensors split each pixel into four sub‑aperture views (UL, UR, DL, DR) under a single microlens, providing multi‑directional phase information. Compared to conventional Dual‑Pixel (left/right), QPD unlocks **both horizontal and vertical disparity cues**, enabling richer geometry and sharper imaging. This page presents two CVPR 2025 projects that leverage QPD technology: **Image Defocus Deblurring** and **All‑Directional Disparity Estimation**.

---

# Quad-Pixel Image Defocus Deblurring: A New Benchmark and Model

**CVPR 2025 Poster**

This is the official project page for our paper **"Quad-Pixel Image Defocus Deblurring: A New Benchmark and Model"**, accepted as a **Poster** at *CVPR 2025*. In this work, we address the task of defocus deblurring using Quad Photodiode (QPD) sensors, which are widely used in modern smartphone cameras. Our contributions include:

-  A large-scale **QP defocus deblurring (QPDD) dataset**, consisting of **4,935** defocus and all-in-focus image pairs, available in both RAW and sRGB formats.
-  A novel network **LMNet** for defocus deblurring, which fully utilizes information from the sub-aperture views of QP/DP images and enables effective capture of global and local dependencies.
-  Extensive experiments evaluate our QP-based deblurring approach and demonstrate its clear advantages over DP‑based methods.

## 📁 Dataset: QPDD

We introduce **QPDD**, the first real-world defocus deblurring dataset dedicated to Quad‑Pixel sensors, containing:

- 200 indoor scenes comprising **4,935** pairs of defocus/all-in-focus images.
- 100 extra multi‑depth test images.

| Modality                         | Count  |
|----------------------------------|--------|
| QPD Defocus Images (RAW + sRGB)  | 4,935  |
| All‑in‑Focus Ground Truths       | 4,935  |
| Multi‑depth Test Images          | 100    |

**Overview of QPDD Generation Pipeline**  
*(Figure – see paper for details)*  
![QPDD_pipeline](https://github.com/excllent123/QPD-Application/blob/main/figs/QPDD_pipeline.jpg)

More details about the dataset can be found in the paper.

##  Method Overview

We propose **LMNet** (Local‑gate assisted Mamba Network), tailored for QPD defocus deblurring:

- **LMNet Architecture Overview**  
A dual‑branch encoder processes the four sub‑aperture views (UL, UR, DL, DR) of QPD, followed by a Simple Fusion Module (SFM) and a decoder built with LAMB blocks.  
![LMNet](https://github.com/excllent123/QPD-Application/blob/main/figs/LMNET.jpg)


##  BibTeX

If you find this dataset or method useful in your research, please cite our paper:

```bibtex
@inproceedings{chen2025quadpixel,
  author    = {Chen et al.},
  title     = {Quad-Pixel Image Defocus Deblurring: A New Benchmark and Model},
  booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year      = {2025}
}
```

# All-directional Disparity Estimation for Real-world QPD Images

**CVPR 2025 Highlight Paper**

This is the official project page for our paper **"All-directional Disparity Estimation for Real-world QPD Images"**, accepted as a **Highlight paper** at *CVPR 2025*. In this work, we address the task of disparity estimation using Quad Photodiode (QPD) sensors, which are widely used in modern smartphone cameras. Our contributions include:

- The first large-scale real-world **QPD disparity dataset** (named **QPD2K**) with 2,100 high-resolution QPD image and ground-truth disparity pairs.
- We propose the **DPNet** for DP disparity estimation and the **QuadNet** for QPD disparity estimation, with three novel modules fully considering the characteristics of QPD sensors. Our experiments demonstrate that our networks achieve SOTA performance in DP and QPD disparity estimation.

## 📁 Dataset: QPD2K

We introduce **QPD2K**, the first real-world dataset containing:
- 2,100 high-quality QPD raw images captured under diverse real-world scenarios.
- Corresponding disparity maps generated via calibrated stereo setups.

| Modality       | Count |
|----------------|-------|
| QPD Images     | 2,100 |
| Disparity Maps | 2,100 |

**Overview of QPD2K Generation Pipeline**
![QPD2K](https://github.com/excllent123/QPD-disparity/blob/main/figs/QPD2K_pipeline.jpg)

More details about the dataset can be found in the paper.

## Method Overview

We propose two deep learning architectures:

- **DPNet Architecture Overview**
The DPNet comprises two novel modules: an illumination-invariant module and a coarse-to-fine module.
![DPNet](https://github.com/excllent123/QPD-disparity/blob/main/figs/Figure_network_DPNet.jpg)

- **QuadNet Architecture Overview**
QuadNet integrates two-directional information via an edge-aware fusion module for QPD data. A Census-based refinement further refines the fused disparity
![QuadNet](https://github.com/excllent123/QPD-disparity/blob/main/figs/Figure_network_Quad.jpg)


##  BibTeX

If you find this dataset or method useful in your research, please cite our paper:

```bibtex
@inproceedings{yu2025qpd,
  author    = {Hongtao Yu  and Shaohui Song and Lihu Sun  and Wenkai  and Su Xiaodong Yang  and Chengming Liu},
  title     = {All-directional Disparity Estimation for Real-world QPD Images},
  booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year      = {2025}
}
