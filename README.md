<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <img src="./image/icon.png" alt="DragOSM Logo" width="256" height="256">
  <h2 align="center">DragOSM: Aligning Building Roof and Footprint Labels with Off-Nadir Images</h2>
  <p align="center">
    Official codebase for our IEEE TPAMI 2025 paper.<br>
    <a href="https://arxiv.org/abs/your-arxiv-link">[Paper]</a> | <a href="https://github.com/likaiucas/DragOSM">[Project HomePage]</a>
    <br><br>
    <img src="./image/model.png" alt="DragOSM Model Structure" width="80%">
    <br>
    <i>DragOSM: Interactive Label Correction for Off-Nadir Aerial Imagery</i>
  </p>
</div>

---

## Table of Contents

- [About DragOSM](#about-dragosm)
- [Key Contributions](#key-contributions)
- [Installation](#installation)
- [Dataset: ReBO](#dataset-rebo)
- [Quick Start](#quick-start)
- [Results](#results)
- [Code Structure](#code-structure)
- [License](#license)
- [Citation](#citation)
- [Contact](#contact)

---

## About DragOSM

DragOSM is a new framework to accurately align and correct building roof and footprint labels in off-nadir (oblique) aerial images, especially where historical labels (e.g., from OpenStreetMap) are outdated or spatially misaligned. Our method formulates label correction as an interactive "dragging" process, introducing the novel concept of the **Alignment Token**, and adopts denoising training to robustly learn spatial offsets.

<details>
<summary>Click to expand for an intuitive task illustration</summary>

<p align="center">
  <img src="./image/model.png" alt="Model structure" width="80%">
</p>

</details>

For more details, see our paper:  
**DragOSM: Aligning Building Roof and Footprint Labels with Off-Nadir Images** (IEEE TPAMI 2025)

---

## Key Contributions

- **Alignment Token & Interactive Label Correction:**  
  We introduce the *alignment token* concept and formulate historical label correction as a two-step interactive dragging process for off-nadir images, solving the mismatch between outdated labels and current imagery.

- **Denoising Training & Inference Scheme:**  
  DragOSM uses dynamic Gaussian noise to simulate label displacements during training and learns to iteratively denoise and align annotations.

- **ReBO: A New Benchmark Dataset:**  
  We curated the Repairing Buildings in OSM (ReBO) dataset with over 179,000 buildings and detailed instance-level polygon corrections (roof, footprint, OSM) across 41 cities.

- **Strong Empirical Performance:**  
  DragOSM achieves state-of-the-art results on label alignment tasks, outperforming both extraction-based and prompt-based baselines in both accuracy and robustness.

---

## Installation

**DragOSM** is built upon [MMDetection](https://github.com/open-mmlab/mmdetection) and reuses parts of [BONAI](https://github.com/jwwangchn/BONAI).  
**Please follow the official installation guides for these dependencies:**

- [BONAI Installation Guide](https://github.com/jwwangchn/BONAI)
- [MMDetection Installation](https://github.com/open-mmlab/mmdetection)

Make sure you are using a compatible environment (e.g., PyTorch 1.7+, CUDA 11.1+, Python 3.8+) and properly install all dependencies.

```bash
# Example (do not run as-is, refer to official docs for details)
conda create -n dragosm python=3.8
conda activate dragosm
pip install torch torchvision
# Install MMDetection and BONAI following their instructions
