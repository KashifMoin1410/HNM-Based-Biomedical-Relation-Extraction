# **HNM-Based Biomedical Relation Extraction**

## **Overview**

This repository presents an implementation of biomedical relation extraction models, emphasizing the integration of Hard Negative Mining (HNM) to enhance model performance. The project encompasses baseline models and HNM-enhanced models, trained and evaluated on biomedical datasets formatted in BioC JSON. All code, pretrained models, and sample data for reproducing experiments are provided.

## **Data**

The datasets used are in the BioC JSON format, which is a standard for sharing biomedical text data. The filtered\_data.csv file contains preprocessed data derived from these JSON files, formatted for efficient model training and evaluation.

## **Models**

* **Baseline Model**: A standard relation extraction model trained without any specialized sampling techniques.  
* **HNM Model**: An enhanced model that incorporates Hard Negative Mining during training to improve the model's ability to distinguish between closely related biomedical entities.

## **Training and Evaluation**

1. **Baseline Model Training**:  
   * Open and run Baseline Model Training.ipynb to train the baseline model.  
2. **HNM Model Training**:  
   * Open and run HNM Model Training.ipynb to train the model with Hard Negative Mining.  
3. **Sample Prediction and Evaluation**:  
   * Use Sample Prediction and Evaluation.ipynb to generate predictions and evaluate model performance on sample data.  
4. **Test Dataset Evaluation**:  
   * Use Test Dataset \- Model Evaluation.ipynb to assess model performance on the test dataset.

## **Approach**

* **Baseline:** Standard supervised neural relation extraction model.  
* **HNM Model:** Baseline model enhanced with *Hard Negative Mining*, using contrastive learning to explicitly select difficult (hard) negative samples and improve relation cluster separation.

### **Key Steps**

1. **Data Preprocessing:** Parse BioC files, create training/validation/test splits, and filter entities/relations.  
2. **Model Training:**  
   * Run Baseline Model Training.ipynb for standard model.  
   * Run HNM Model Training.ipynb for HNM-augmented training.  
3. **Evaluation:**  
   * Use Sample Prediction and Evaluation.ipynb for qualitative predictions and metrics.  
   * Use Test Dataset \- Model Evaluation.ipynb for benchmarking on held-out test set.  
4. **Weights:** Pretrained model checkpoints (.pth files) for both approaches.

## **Results**

| Model | Macro-F1 | Precision | Recall | Clustering ARI |
| ----- | ----- | ----- | ----- | ----- |
| Baseline | 27% | 25% | 29% | Low |
| HNM \+ Contrastive | 84% | 82% | 85% | High |

* HNM outperforms the baseline by a wide margin in macro F1, precision, recall, and clustering quality.  
* Major gains are seen in distinguishing fine-grained biomedical relationships.

The incorporation of Hard Negative Mining has shown to significantly improve model performance in biomedical relation extraction tasks. Detailed evaluation metrics and comparisons between the baseline and HNM models are provided in the evaluation notebooks.