
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







<img width="1979" height="780" alt="output (2)" src="https://github.com/user-attachments/assets/ba4373f4-830c-4988-a9db-049795580ba6" />





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







<img width="1979" height="780" alt="output (3)" src="https://github.com/user-attachments/assets/cb2fa604-e922-485f-b2ab-bf6b9cccda0c" />




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
| Fold   | F1 Score | Accuracy |
|--------|----------|----------|
| 1      | 0.9944   | 0.9944   |
| 2      | 0.9944   | 0.9944   |
| 3      | 0.9887   | 0.9888   |
| 4      | 0.9912   | 0.9910   |
| 5      | 0.9925   | 0.9930   |

- **Average F1 across folds**: 0.9910
 
- **Average Accuracy across folds**: 0.9910

<img width="738" height="599" alt="cm" src="https://github.com/user-attachments/assets/09137364-e622-44ea-8745-7e111e23f7ae" />






---



## DAL Submission — Eid Al-Adha 2025: Sheep Classification Challenge

After cross-validation, I trained the final model on the **entire training dataset**, then used it to generate predictions for the test set provided by the competition.

Since the test labels are hidden, no metrics (e.g., F1, confusion matrix) can be calculated.  
Instead, I visualized the **prediction distribution** across the 7 classes.

### Prediction Statistics:
| Class   | Count | Percentage |
|---------|-------|------------|
| Goat    | 39    | 27.1%      |
| Roman   | 33    | 22.9%      |
| Sawakni | 19    | 13.2%      |
| Najdi   | 17    | 11.8%      |
| Naeimi  | 14    | 9.7%       |
| Barbari | 11    | 7.6%       |
| Harri   | 11    | 7.6%       |


<img width="991" height="493" alt="prr" src="https://github.com/user-attachments/assets/b4402880-306a-4b9a-aa39-c1a4e48875a3" />

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


