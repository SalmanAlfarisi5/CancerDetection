## 🔬 cf-DNA Cancer Detection — Summary

Early detection matters: **false-negatives are costlier than false-positives**.  
This repo benchmarks several models on an imbalanced cf-DNA fragment-length dataset.

| Item | Details |
|------|---------|
| **Train / Test** | 850 / 400 samples |
| **Features** | 350 fragment-length frequencies (`length_51` … `length_400`) |
| **Label** | `class_label` → `healthy` (0) vs `cancer` (1) |
| **Imbalance** | ≈ 13 : 1 (cancer ≫ healthy) |
| **Metric focus** | Tune threshold for **Recall ≥ 0.95**; report Precision |

### ⚙️ Pipeline
1. **Standardise** each feature (z-score).  
2. **Model** with `class_weight="balanced"` or equivalent.  
3. **Threshold sweep** on PR-curve → pick highest precision at Recall ≥ 0.95.  
4. **Report** confusion matrix & PR-curve.

### 📊 Benchmark Results (test set)

| Model | Threshold | Recall | Precision |
|-------|-----------|--------|-----------|
| Logistic Regression | 0.765 | 0.951 | **0.975** |
| Decision Tree | 0.600 | **0.962** | 0.937 |
| Random Forest | 0.647 | 0.951 | 0.941 |
| SVM (RBF) | 0.713 | 0.959 | 0.944 |

*Decision Tree* leads on recall; *Logistic Regression* yields the best precision while meeting the recall target.

