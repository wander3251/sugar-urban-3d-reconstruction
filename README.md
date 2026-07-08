# SuGaR Urban 3D Reconstruction

<p align="center">
  <img src="images/pipeline.png" width="850">
</p>

An academic reproduction of the **SuGaR (Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering)** method proposed at **CVPR 2024**, using a custom dataset composed of urban monuments and objects.

This project was developed as part of the **Computer Graphics** course at the **Federal University of Maranhão (UFMA)**. The objective was to reproduce the original SuGaR methodology using a custom image dataset collected by our team, replacing the dataset used in the original publication. The reconstructed scenes were quantitatively evaluated using the same metrics adopted by the original paper.

---

# Original Paper

Guédon, A., & Lepetit, V.

**SuGaR: Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering**

*Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2024.*

📄 Paper: https://arxiv.org/abs/2311.12775

💻 Official Repository: https://github.com/Anttwo/SuGaR

> **Disclaimer**
>
> This repository **is not the official implementation of SuGaR**.
> It is an academic reproduction developed for educational and research purposes using a custom dataset of urban monuments and objects.

---

# Project Objectives

- Reproduce the complete SuGaR reconstruction pipeline.
- Replace the original dataset with a custom dataset.
- Reconstruct real urban monuments in 3D.
- Compare SuGaR against two methods evaluated in the original paper:
  - 3D Gaussian Splatting (3DGS)
  - Instant-NGP
- Evaluate the reconstructed scenes using:
  - PSNR
  - SSIM
  - LPIPS

---

# Dataset

The dataset used in this project was created by our team and contains photographs of four urban objects located in **São Luís, Maranhão, Brazil**:

- Artur Azevedo Bust
- Lion Sculpture
- Cannon
- Historic Light Pole

Unlike the original paper, the official dataset was replaced by a custom image collection captured specifically for this project.

---

# Experimental Pipeline

The reconstruction workflow followed the steps below:

1. Image acquisition
2. Camera pose estimation using COLMAP
3. Sparse scene reconstruction
4. Training of 3D Gaussian Splatting (3DGS)
5. Surface alignment and mesh extraction using SuGaR
6. Reconstruction using Instant-NGP
7. Quantitative evaluation using PSNR, SSIM and LPIPS

---

# Repository Structure

```text
.
├── docs/
├── images/
│   └── pipeline.png
├── notebooks/
├── paper/
├── results/
├── LICENSE
└── README.md
```

---

# Folder Description

### notebooks/

Google Colab notebooks used during the implementation and evaluation of the reconstruction pipeline.

### images/

Images illustrating the experimental pipeline and qualitative reconstruction results.

### results/

Generated outputs produced during the experiments, including model checkpoints (`.pt`), point clouds (`.ply`) and reconstructed meshes (`.obj`).

### paper/

Portuguese and English versions of the final paper.

### docs/

Additional documentation related to the project.

---

# Experimental Environment

The experiments were performed using:

- Google Colab
- NVIDIA A100 GPU (40 GB)
- Python 3.10
- COLMAP
- 3D Gaussian Splatting (3DGS)
- SuGaR
- Instant-NGP

---

# Evaluation Metrics

The reconstruction quality was evaluated using the same metrics adopted in the original SuGaR paper:

- **PSNR** — Peak Signal-to-Noise Ratio
- **SSIM** — Structural Similarity Index
- **LPIPS** — Learned Perceptual Image Patch Similarity

---

# Results

The qualitative evaluation demonstrated that SuGaR successfully reconstructed the evaluated urban monuments while enabling high-quality mesh extraction from Gaussian representations.

The quantitative evaluation was performed by comparing SuGaR with **3D Gaussian Splatting (3DGS)** and **Instant-NGP** using the metrics **PSNR**, **SSIM**, and **LPIPS**.

The experiments also showed that reconstruction quality strongly depends on image coverage. Objects photographed without sufficient upper viewpoints produced incomplete meshes, while the cannon, which presented better image coverage, achieved the most complete reconstruction.

---

# Paper

The complete paper produced during this project is available in both languages.

- Portuguese version: `paper/article_pt.pdf`
- English version: `paper/article_en.pdf`

---

# Citation

If you use this repository, please also cite the original SuGaR paper.

```bibtex
@inproceedings{guedon2024sugar,
  title={SuGaR: Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering},
  author={Guédon, Antoine and Lepetit, Vincent},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2024}
}
```

---

# Authors

This repository was developed by the project team for the **Computer Graphics** course at the **Federal University of Maranhão (UFMA)**.

---

# Acknowledgements

We gratefully acknowledge the authors of the original SuGaR paper for making their implementation publicly available. Their work enabled this academic reproduction and served as the foundation for our experiments.
