# Adversarial Attacks on Semantic Segmentation Models

![Example of adversarial attack](https://via.placeholder.com/800x400?text=Adversarial+Attack+Visualization)  
*Visualization of targeted adversarial perturbations on segmentation models*

## 📌 Project Overview
This project implements **adversarial attacks** against semantic segmentation models (DeepLabV3 and FCN) to study their vulnerability to:
- **Untargeted attacks** (disrupting predictions)
- **Targeted attacks** (forcing specific misclassifications)
- **Transferability** between different architectures

Built with PyTorch and optimized for GPU acceleration.

## 🔧 Key Features
- **White-box attacks**:
  - Gradient-based perturbation generation
  - Patch-based attacks
- **Model Support**:
  - DeepLabV3 (ResNet50 and MobileNetV3 backbones)
  - FCN ResNet50
- **Analysis Tools**:
  - Visual comparison of original/attacked predictions
  - Transferability evaluation across models
  - Perturbation norm vs performance analysis

## 🚀 Quick Start
1. **Requirements**:
   ```bash
   pip install torch torchvision matplotlib
   ```
2. **Run in Google Colab**:
   - Open [the notebook](https://colab.research.google.com/drive/1unCX5wrZaGOeF6r4sE2IG7jmxes0T-VT) 
   - Use T4 GPU runtime for best performance

## 📊 Key Findings
1. **Effectiveness**:
   - Global perturbations > localized patches
   - Targeted attacks require careful tuning
2. **Transferability**:
   ```python
   # Attack trained on DeepLabV3-MobileNet
   success_rate_on_fcn = 0.32  # Low cross-model transfer
   ```
3. **Performance Impact**:
   - Attack strength ∝ computation time (linear relationship)

## 🎯 Sample Usage
```python
# Generate untargeted attack
attack = descente_grad_non_ciblee(
    perturbation, 
    nb_iter=10,
    limite_perturb=10
)

# Visualize results
compare_predictions(
    clean_preds, 
    attacked_preds,
    "Attack Effectiveness"
)
```

## 📂 Project Structure
```
├── adversarial_attacks.ipynb       # Main notebook
├── coco_sample.pth                 # Sample dataset
├── utils/                          # Helper functions
│   ├── visualization.py            # Prediction comparison tools
│   └── attacks.py                  # Attack implementations
```
