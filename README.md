# gradcam-multimetric-evaluation
Code for multi-metric evaluation of Grad-CAM on binary EuroSAT satellite classification.

# Beyond Accuracy: Multi-Metric Evaluation of Grad-CAM Interpretability (EuroSAT)

Code for our XAI study on satellite image classification, focusing on **multi-metric evaluation** of Grad-CAM explanations for a **binary EuroSAT task (green vs. non-green)**.

## What this repo provides
- Training code for image classifiers (e.g., ResNet / DenseNet / EfficientNet)
- Grad-CAM generation pipeline
- Quantitative evaluation of explanations using faithfulness-oriented metrics
  - AOPC (MoRF / LeRF) *(and other metrics used in the paper)*
- Visualization utilities (CAM overlays, examples)

## Citation
If you use this code or find it helpful, please cite:

```bibtex
@inproceedings{kim2025beyondaccuracy,
  title={Beyond Accuracy: Multi-Metric Evaluation of Grad-CAM Interpretability for Binary EuroSAT Classification},
  author={Jiyeon Kim},
  booktitle={},
  year={2025}
}
