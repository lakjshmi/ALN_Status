# ALN_Status
Predictive Modelling of ALN Status and Clinical Outcomes Using Machine Learning Techniques

## Introduction
### Project Overview
This project aims to utilize machine learning techniques to predict Axillary Lymph Node (ALN) status based on clinical data, emphasizing its significance in oncology and predictive medicine. Accurately predicting ALN status is crucial as it informs treatment decisions and prognosis for breast cancer patients. The predictive models developed here not only contribute to personalized medicine but also enhance clinical decision-making by providing insights into the likelihood of lymph node metastasis.
### Problem Statement
The primary objective of this project is to develop predictive models that can accurately classify ALN status using patient clinical data. ALN status is a critical indicator in breast cancer staging, influencing treatment strategies such as surgery and chemotherapy. Traditional methods rely heavily on invasive procedures like lymph node dissection, which can be avoided or minimized if accurately predicted non-invasively through computational models. Hence, the need for accurate predictive modelling is of great significance in clinical oncology to improve patient outcomes and quality of life.
By leveraging machine learning algorithms on comprehensive clinical datasets, this project seeks to enhance the accuracy and reliability of ALN status predictions. This approach not only aims to streamline treatment planning but also aims to contribute to the broader goal of personalized medicine in oncology.


## Data Collection and Preprocessing

### Data Source
The BCNB dataset was introduced in the paper “Predicting Axillary Lymph Node Metastasis in Early Breast Cancer Using Deep Learning on Primary Tumour Biopsy Slides,” published in Frontiers in Oncology. The dataset includes core-needle biopsy whole slide images (WSIs) of 1058 early breast cancer patients, annotated by two independent and experienced pathologists. The WSIs are provided in .jpg format, and the clinical data is available in .xlsx format. The dataset has been desensitized to remove any patient privacy information.
### Data Description
The dataset comprises clinical characteristics of 1058 patients, including:
*	Patient ID
*	Age (years)
*	Tumor Size (cm)
*	Tumor Type
*	ER (Estrogen Receptor)
*	PR (Progesterone Receptor)
*	HER2 (Human Epidermal Growth Factor Receptor 2)
*	HER2 Expression
*	Histological Grading
*	Surgical Method
*	Ki67 (a marker of proliferation)
*	Molecular Subtype
*	Number of Lymph Node Metastases
*	ALN Status (Axillary Lymph Node status)

### Data Cleaning
The data cleaning process involved several steps to ensure the dataset was suitable for model training and analysis:
1.	Handling Missing Values:
	Identified and handled missing values in the dataset. For example, rows with missing values in critical columns like histological_grading were dropped.
2.	Encoding Categorical Variables:
	Categorical variables such as tumour_type, er, pr, her2, her2_expression, molecular_subtype, aln_status, and surgical were encoded using LabelEncoder to convert them into numerical values.
3.	Scaling Numerical Features:
	Applied scaling to numerical features to ensure they are on a comparable scale for model training.
## Predictive Modelling
The cleaned dataset was used to train several predictive models to classify ALN status. Models included:
*	Decision Tree Classifier
*	Support Vector Machine (SVM) with Linear Kernel
*	Logistic Regression

### Model Evaluation
Confusion matrices were generated to evaluate the performance of each model. These matrices helped assess the models' accuracy, precision, recall, and overall effectiveness in predicting ALN status.

## Results and Discussion
The results of the predictive models were analyzed, with the confusion matrices indicating the performance of each model in terms of correctly and incorrectly classified instances of ALN status.

### Confusion Matrix after for the performance of each model
![image](https://github.com/user-attachments/assets/ada9354c-88b3-44aa-adda-00c7d7bf3c9c)

Confusion matrix after Decision Tree Classifier

![image](https://github.com/user-attachments/assets/aadd1092-9be9-47f5-bcc9-e4272f4c5709)

Confusion matrix after Linear SVM Model

![image](https://github.com/user-attachments/assets/f22f7f64-737e-4989-9efe-fada4fc8dee9)

Confusion Matrix after Linear Regression

### Classification Report of each model
![image](https://github.com/user-attachments/assets/106ac856-b563-430a-b7ff-ecaef0f1c0c2)

Classification report of Decision Tree Model

![image](https://github.com/user-attachments/assets/cf923f51-0f5f-4098-9d64-e32183507707)

Classification report of Linear SVM Model

![image](https://github.com/user-attachments/assets/0b21a698-18b7-493a-93f4-42e1e04ce569)

Classification report of Logistic Regression Model

## Conclusion
The project demonstrates the potential of using machine learning to predict ALN status in early breast cancer patients based on clinical data. The developed models can aid in personalized treatment planning and reduce the need for invasive procedures.
### Decision Tree Classification Report
#### Precision, Recall, F1-Score:
  * The Decision Tree model achieved perfect precision, recall, and F1-scores of 1.00 across all classes (0, 1, and 2).
  *	This indicates that the model perfectly identified all instances of each class without any errors.
#### Accuracy:
  * The overall accuracy of the model is 1.00, meaning it correctly classified all instances in the test set.
#### Support:
  * The support, representing the number of true instances for each class, was 149 for class 0, 142 for class 1, and 449 for class 2.
#### Conclusion:
  * The Decision Tree model is highly effective, showing no misclassifications. However, this might indicate overfitting, especially if the model performs significantly worse on a different dataset or in cross-validation.

### Linear SVM Classification Report
#### Precision, Recall, F1-Score:
*	For class 0: The precision is 0.89, recall is 0.28, and F1-score is 0.42, indicating poor performance in identifying class 0 instances correctly.
*	For class 1: The precision is 0.52, recall is 0.96, and F1-score is 0.67, showing that the model correctly identified most class 1 instances but had many false positives.
* For class 2: The precision, recall, and F1-score are very high (1.00, 0.96, and 0.98), suggesting excellent performance for class 2.
#### Accuracy:
*	The overall accuracy of the model is 0.82, which is considerably lower than the Decision Tree and Logistic Regression models.
#### Conclusion:
* The Linear SVM model performs reasonably well but struggles particularly with class 0. Its lower precision and recall for class 0 suggest it often misclassifies instances of this class, and it is less effective compared to the Decision Tree and Logistic Regression models.

### Logistic Regression Classification Report
#### Precision, Recall, F1-Score:
*	The model has near-perfect precision, recall, and F1-scores for all classes.
*	For class 0: Precision is 0.97, recall is 0.99, and F1-score is 0.98.
*	For class 1: Precision is 0.99, recall is 0.96, and F1-score is 0.98.
*	For class 2: Precision, recall, and F1-score are all 1.00.
#### Accuracy:
*	The overall accuracy is 0.99, indicating the model correctly classified nearly all instances.
#### Conclusion:
* The Logistic Regression model shows excellent performance with high precision, recall, and F1-scores, slightly less than perfect but still robust. This model balances complexity and generalization well, making it a reliable choice for predicting ALN status

### Overall Comparison
#### Decision Tree:
*	Perfect accuracy and classification metrics suggest potential overfitting.
#### Linear SVM:
*	Lower accuracy and less effective, particularly for class 0. This model may need tuning or additional features to improve performance.
#### Logistic Regression:
* Near-perfect performance with high accuracy and balanced classification metrics, indicating strong generalizability and robustness.
### Conclusion
#### Best Performing Model:
*	The Logistic Regression model is the most balanced and generalizable among the three, offering high precision, recall, and accuracy without the overfitting concerns observed in the Decision Tree model.
#### Recommendations:
*	Based on the current data and performance metrics, the Logistic Regression model is recommended for predicting ALN status in early breast cancer patients. Further validation on additional datasets is suggested to confirm its robustness and generalizability.

## References
Xu, F., Zhu, C., Tang, W., Wang, Y., Zhang, Y., Li, J., Jiang, H., Shi, Z., Liu, J. and Jin, M., 2021. Predicting Axillary Lymph Node Metastasis in Early Breast Cancer Using Deep Learning on Primary Tumour Biopsy Slides. Frontiers in Oncology, p.4133.
License

	This BCNB Dataset is made freely available to academic and non-academic entities for non-commercial purposes such as academic research, teaching, scientific publications, or personal experimentation. Permission is granted to use the data given that you agree to our license terms bellow:

		1. That you include a reference to the BCNB Dataset in any work that makes use of the dataset. For research papers, cite our preferred publication as listed on our website; for other media cite our preferred publication as listed on our website or link to the BCNB website.
		
		2. That you do not distribute this dataset or modified versions. It is permissible to distribute derivative works in as far as they are abstract representations of this dataset (such as models trained on it or additional annotations that do not directly include any of our data).
		
		3. That you may not use the dataset or any derivative work for commercial purposes as, for example, licensing or selling the data, or using the data with a purpose to procure a commercial gain.
		That all rights not expressly granted to you are reserved by us.
