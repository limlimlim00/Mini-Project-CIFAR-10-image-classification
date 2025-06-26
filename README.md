# Understanding CNN Robustness Under Label and Input Corruption

This repository contains code and results for the project **"Understanding CNN Robustness: A Comparative Study on Label and Input Corruptions"**, conducted as part of the **Artificial Intelligence** course mini-project at Seoul National University.

The goal of this project is to systematically analyze the effect of different types of **training-time corruption on the generalization performance of a CNN classifier** trained on the CIFAR-10 dataset.

## 📁 Repository Structure

```
.
├── Baseline/
│   ├── baseline.ipynb
│   └── Figures/              # Training curve & confusion matrix (2 images)
├── Random Label Shuffle/
│   ├── random_label_shuffle.ipynb
│   └── Figures/
├── Label Noise/
│   ├── label_noise.ipynb
│   └── Figures/
├── Input Perturbation/
│   ├── input_perturbation.ipynb
│   └── Figures/
├── Understanding CNN Robustness Under Label and Input Corruption.pdf
└── README.md
```

Each directory includes:

- A Jupyter notebook (`.ipynb`) that runs the corresponding experiments.
- A `Figures/` folder that stores the resulting plots from both clean and corrupted input settings.

## 🧪 Experiments Overview

We evaluated the same CNN architecture under four conditions:

1. **Baseline**  
   Clean images and labels.

2. **Random Label Shuffle**  
   Training labels are randomly shuffled, removing semantic meaning.

3. **Label Noise (20%)**  
   20% of labels are replaced with incorrect ones.

4. **Input Perturbation**  
   Images are augmented with cropping, blur, jitter, and grayscale conversion.

All models were trained from scratch using identical hyperparameters (100 epochs, batch size 128, Adam optimizer).

## 📊 Key Results

| Condition              | Train Acc. (%) | Test Acc. (%) |
|------------------------|----------------|---------------|
| Baseline               | 99.63          | 89.36         |
| Label Noise (20%)      | 99.13          | 76.87         |
| Random Label Shuffle   | 10.38          | 9.58          |
| Input Perturbation     | 96.14          | 90.32         |

- **While label corruption severely degrades generalization, input perturbation acts as an effective regularizer, even improving test performance over the baseline.**

## 📌 Notes

- All experiments were run on NVIDIA A100 GPU (Colab).
- The model architecture is based on a simplified VGG16 variant.
