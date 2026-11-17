# Beyond Accuracy: Multi-Metric Evaluation of Grad-CAM Interpretability (EuroSAT)

Code for the paper **"Beyond Accuracy: Multi-Metric Evaluation of Grad-CAM Interpretability for Binary EuroSAT Classification"**, published in the *Journal of Artificial Intelligence Research and Applications* (Korean Artificial Intelligence Association), Vol. 2, No. 1, pp. 91–103, 2025.

- Paper (official page): https://www.e-jara.org/journal/view.html?pn=current_issue&uid=1534&vmd=Full
- Paper (PDF): [paper.pdf](paper.pdf)
- Keywords: Deep Learning, Grad-CAM, Explainable AI, Interpretability, Satellite Imagery

## Motivation

Models with almost identical accuracy can still base their decisions on very different evidence. This study asks whether high accuracy means a model's Grad-CAM explanations can also be trusted, and evaluates explanation quality with several quantitative metrics instead of visual inspection alone.

## Setup

- **Task**: EuroSAT reformulated as binary classification (green vs. non-green land cover)
- **Models**: ResNet50, DenseNet121, EfficientNet-B0, trained under the same conditions (all around 98% test accuracy)
- **Explanation method**: Grad-CAM
- **Evaluation metrics**
  - **AOPC** (MoRF / LeRF): deletion-based faithfulness, measured by how much the prediction drops when the most (or least) important regions are removed first
  - **SaCo**: agreement between the attribution ranking and the actual effect of each region
  - **SC**: stability of the explanation under input scale changes
- Evaluation samples are drawn by class-stratified sampling, and relationships between metrics are tested with Spearman correlation.

## Key Findings

- EfficientNet-B0 achieved the highest AOPC (Macro 0.450), but its SaCo coefficient was 0.098, close to random. ResNet50 (0.376) and DenseNet121 (0.282) showed higher ranking agreement.
- A significant positive correlation between the two faithfulness views appeared only for DenseNet121 (Spearman ρ = 0.543, p = 0.013).
- The metrics capture different properties of an explanation, so judging explanation quality with a single metric can distort model selection. The paper proposes choosing a combination of metrics that fits the task.

## Repository Contents

| File | Description |
|---|---|
| [`paper.pdf`](paper.pdf) | Published paper |
| [`paper_XAI.ipynb`](paper_XAI.ipynb) | End-to-end notebook: data preparation, model training, Grad-CAM generation, AOPC / SaCo / SC evaluation, statistical analysis and visualization |

The EuroSAT dataset is not included. Download it from the [official repository](https://github.com/phelber/EuroSAT) before running the notebook.

## Citation

```bibtex
@article{kim2025beyondaccuracy,
  title   = {Beyond Accuracy: Multi-Metric Evaluation of Grad-CAM Interpretability for Binary EuroSAT Classification},
  author  = {Kim, Jiyeon},
  journal = {Journal of Artificial Intelligence Research and Applications},
  volume  = {2},
  number  = {1},
  pages   = {91--103},
  year    = {2025}
}
```

## License

See [LICENSE](LICENSE).
