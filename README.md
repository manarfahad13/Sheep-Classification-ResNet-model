
# 🐑 Sheep Breed Classification (Eid Al-Adha Dal 2025 Challenge)

This project presents a deep learning model developed to classify images of 7 Arabian sheep breeds using ResNet-50 and PyTorch. It was built as part of the **Eid Al-Adha 2025: Sheep Classification Challenge** hosted on Kaggle.

---

## Dataset

<img width="555" height="334" alt="4" src="https://github.com/user-attachments/assets/207b8d96-e83e-40e3-8d25-fd6ad22721e6" />

The dataset includes images of the following sheep breeds:
- Naeimi
- Najdi
- Harri
- Goat
- Sawakni
- Roman
- Barbari

Images were divided into training and testing sets.However, the training set was initially imbalanced, with some classes (e.g., Barbari) having significantly fewer samples than others (e.g., Naeimi).  
To address this issue and ensure fair learning, the dataset was balanced using **data augmentation techniques** to generate additional images for the underrepresented classes.This ensured that all classes have an equal number of images (255 per class), helping the model learn more effectively without being biased toward the majority classes.

## Original Class Distribution

|Breed     | Original Count |
|----------|----------------|
| Naeimi   | 255            |
| Najdi    | 71             |
| Harri    | 62             |
| Goat     | 107            |
| Sawakni  | 80             |
| Roman    | 72             |
| Barbari  | 35             |



## Augmented Class Distribution

|Breed     | Augmented Count|
|----------|----------------|
| Naeimi   | 255            |
| Najdi    | 255            |
| Harri    | 255            |
| Goat     | 255            |
| Sawakni  | 255            |
| Roman    | 255            |
| Barbari  | 255            |





---
## Model Architecture

- Pretrained **ResNet-50**
- Final layer adapted to 7 output classes
- Weighted CrossEntropy loss to handle class imbalance
- Optimizer: Adam
- Learning rate: 3e-5

---
## Cross Validation Details

To ensure robust model evaluation and reduce overfitting, I applied 5 fold cross-validation on the full training dataset.

- **Model Used**: ResNet-50 (pretrained on ImageNet)
- **Folds**: 5
- **Epochs per fold**: 5
- **Learning Rate**: 3e-5 with StepLR scheduler
- **Loss Function**: CrossEntropy with class weights
- **Evaluation Metric**: Macro-averaged F1-score and Accuracy

### Results Across Folds
| Fold | F1 Score | Accuracy |
|------|----------|----------|
| 1    | 0.91     | 0.93     |
| 2    | 0.92     | 0.93     |
| 3    | 0.92     | 0.94     |
| 4    | 0.91     | 0.93     |
| 5    | 0.91     | 0.92     |


Confusion matrices for each fold:

#### Fold 1 :
<img width="810" height="598" alt="k1 con" src="https://github.com/user-attachments/assets/7fa296b8-78c2-45da-a03d-88bbe0031317" />


#### Fold 2 : 
<img width="891" height="601" alt="k2" src="https://github.com/user-attachments/assets/1597c27b-d77b-4b08-ba4e-b8be441e4d5e" />



#### Fold 3 :
<img width="861" height="598" alt="k3" src="https://github.com/user-attachments/assets/f88a2d8f-5c43-49ae-8177-4c410d7c0c11" />



#### Fold 4 :
<img width="793" height="596" alt="k4" src="https://github.com/user-attachments/assets/dfa3de81-e87d-4b34-babb-644645ae702b" />



#### Fold 5 :
<img width="831" height="598" alt="k5" src="https://github.com/user-attachments/assets/62a47f8c-b213-4e12-b947-3730b7f09648" />


***Average F1 Score***: `0.917`  
***Average Accuracy***: `0.931`

---



## DAL Submission — Eid Al-Adha 2025: Sheep Classification Challenge

After cross-validation, I trained the final model on the **entire training dataset**, then used it to generate predictions for the test set provided by the competition.

Since the test labels are hidden, no metrics (e.g., F1, confusion matrix) can be calculated.  
Instead, I visualized the **prediction distribution** across the 7 classes.

### Prediction Statistics:
| Class   | Count | Percentage |
|---------|-------|------------|
| Goat    | 36    | 25.0%      |
| Roman   | 33    | 22.9%      |
| Sawakni | 21    | 14.6%      |
| Najdi   | 15    | 10.4%      |
| Naeimi  | 15    | 10.4%      |
| Barbari | 12    | 8.3%       |
| Harri   | 12    | 8.3%       |

<img width="1153" height="501" alt="Capture" src="https://github.com/user-attachments/assets/03580ccf-f988-43b1-8152-464baaff6dd3" />

<img width="515" height="702" alt="2" src="https://github.com/user-attachments/assets/c9cf2b45-168c-4ceb-95c9-ac48b0d3bb23" />

---


## Competition Info

This project was submitted to the following competition:

> **Eid Al-Adha 2025: Sheep Classification Challenge**  
> Celebrate Eid Al-Adha with Dal! Build an AI model to classify 7 Arabian sheep breeds.

📎 **Citation**:  
Dal. *Eid Al-Adha 2025: Sheep Classification Challenge*.  
[https://kaggle.com/competitions/sheep-classification-challenge-2025](https://kaggle.com/competitions/sheep-classification-challenge-2025), 2025. Kaggle.

---

## Notes

- The test predictions were submitted to Kaggle for final evaluation.
- The dataset was only partially labeled (no labels for test set).


