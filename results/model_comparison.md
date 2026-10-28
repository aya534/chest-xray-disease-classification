# Model comparison

This note summarizes the existing outputs saved in the two notebooks.

| Metric | VGG19 + custom CNN | ResNet50 |
|---|---:|---:|
| Training accuracy | 99.80% | 93.29% |
| Validation accuracy | 89.32% | 91.02% |
| Test accuracy | 90.03% | 89.89% |
| Test set size | 1,464 | 1,464 |

## Initial observations

- Test accuracy differs by approximately 0.13 percentage points, with VGG19 + CNN higher in the saved outputs.
- VGG19 + CNN has a larger training/validation accuracy gap, which may suggest overfitting.
- ResNet50 has higher saved validation accuracy, but this alone does not establish better generalization.
- The saved classification reports show that class-wise performance differs; inspect recall and F1-score alongside overall accuracy.

## Important caveat

This is a descriptive comparison of existing notebook outputs, not a controlled benchmark. Before drawing strong conclusions, verify identical data splits, preprocessing, label mapping, and evaluation procedure. The notebooks should be rerun if a reproducible comparison is required.
