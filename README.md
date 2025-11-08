# 🧮 Coreset (CRAIG) — Data-Efficient Learning on MNIST

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat&logo=python)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/wajason/Coreset-CRAIG-MNIST-DataEfficiency?style=social)](https://github.com/wajason/Coreset-CRAIG-MNIST-DataEfficiency/stargazers)
[![Run in Colab](https://img.shields.io/badge/Open%20in-Colab-4C8EDA?style=for-the-badge&logo=googlecolab)](https://colab.research.google.com/github/wajason/Coreset-CRAIG-MNIST-DataEfficiency/blob/main/Coreset.ipynb)

> 💡 *"Smarter data beats more data."*  
> A minimal yet powerful demonstration of **data-efficient learning** through **Coreset selection (CRAIG)**.

---

## 🚀 Overview

This notebook presents a **hands-on experiment** on *data-efficient deep learning*, inspired by the paper  
📘 *"Foundations of Data-efficient Learning"*.

It explores how the **CRAIG (Coreset Selection)** algorithm can select a small yet highly representative subset of data (only 20% of MNIST) — achieving **comparable or even better accuracy** than training on the full 10K dataset.

---

## 🧠 What’s Inside

| Section | Description |
|----------|-------------|
| **Algorithm Walkthrough** | Explains the intuition behind CRAIG and its facility-location based optimization. |
| **Implementation Notes** | Clean, annotated implementation in Python/Jupyter. |
| **Performance Comparison** | Full dataset vs. 20% weighted coreset — accuracy, loss, and training time. |
| **Data Efficiency Discussion** | Insights on how fewer, higher-quality samples can outperform more data. |

---

## 📊 Experiment Summary

| Metric | Full Dataset (10K) | Coreset (2K, weighted) | Δ (Difference) | Observation |
|:--|:--:|:--:|:--:|:--|
| **Test Accuracy** | 0.8296 | 0.8366 | +0.0070 | ✅ Coreset slightly better — filters redundant samples |
| **Test Loss** | 0.7285 | 0.7168 | −0.0117 | ✅ Lower loss — improved generalization |
| **Training Time** | 5.4s | 5.9s | +0.5s | ⚖️ Slightly longer due to weighted sampling |

> 🎯 **Conclusion:** Data-efficiency verified — *fewer samples, same (or better) performance.*

---

## ⚙️ How It Works

CRAIG (Coreset for Regularized Adaptive Importance Gradients) approximates data influence using gradients:

$$ g_i = p_i - e_y $$

Then, it uses **Facility Location Optimization** to select a small subset that best represents the full gradient space.  
Weighted sampling via γ preserves the original distribution.

---

## 🧩 Dependencies

```bash
pip install numpy torch torchvision matplotlib tqdm
```

## 📘 How to Run  

1. Clone this repository  
```bash
git clone https://github.com/wajason/Coreset-CRAIG-MNIST-DataEfficiency.git
cd Coreset-CRAIG-MNIST-DataEfficiency
```

2. Open the notebook  
```bash
jupyter notebook Coreset.ipynb
```

3. Follow along — every section is self-documented and ready to experiment with.

## Research Context
This work is inspired by the “Foundations of Data-efficient Learning” paper, which formalizes how intelligent subset selection can drastically reduce training data without sacrificing performance.  
CRAIG, in particular, uses gradient similarity and facility location objectives to ensure that the selected coreset spans the same “learning space” as the full dataset.  

## 🧭 Insights

- Efficiency: 80% fewer samples, similar accuracy
- Interpretability: Transparent selection rationale
- Scalability: Potential to extend to larger datasets and models
- 🧩 Coreset selection is not just about compression — it’s about learning what truly matters.

## 🌟 Contribute & Cite

If this project helps your research or learning, please ⭐ the repo!  
Contributions, issues, and suggestions are welcome via GitHub.


> ⚡ "Train less, learn more — powered by Coreset (CRAIG)."
