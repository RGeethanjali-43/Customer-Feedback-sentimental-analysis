# Customer-Feedback-sentimental-analysis
**Objective:**

The objective is to compare different models and ensemble techniques to select the best

model for prediction and deploy the model using Docker and Flask API.

---

 **Data Description:**

**Dataset Overview:**

**Source**: The data was full of customer reviews and  ratings for the particular clothing.

Format: The dataset in CSV format, containing both numerical and categorical features related to

customer reviews about the clothing

 Features(Columns):

**Numerical Features**:

Clothing ID:  This Id refers the unique id for the dress
Age:    Age of the customer
Rating: Ratings for the clothing and quality of the dress the ratings come till 5
Positive Feedback Count: The count of positive feedbacks

**Categorical Features:**

Title: It refers the reviews which is written shortly like a title
Review Text: The reviews of the customers about the clothing they bought.
Recommended IND: This indicates the review is positive or negative, it comes in binary values(0 or 1)  1- positive 0- negative
Division Name: This refers to the name of the division
Department Name: It refers to the name of the department
Class Name: This refers to the name of the class

---

## Data preparation:

### Data cleaning:

For filling null values used mode imputation of the column

### Text Pre processing:

Converted the upper case to lower case

And removed all the punctuations

Removed all the numbers in the text
Stemming:  It stems the word meaninglessly, used this in order to clean the text
Lematizing: It lematize the word meaningfully
TF-IDF vectorizer: It allocates a number to each word and it is tabularized 
Word to vector: It converts each word into vector, used genism for word to vector

## Visualizing the majority of words in reviews:

Used Word cloud for visualizing the majority of words in  the reviews, it is found that

most of the words are positive.

---

## Machine learning model Development:

After many researches in machine learning model logistic regression with grid search 

gave 85% accuracy

## Hyper parameter tuning:
Gridsearch - Grids used to get best accuracy

python
param_grid = {
    'C': [0.01, 0.1, 1, 10, 100],         # Inverse of regularization strength
    'penalty': ['l1', 'l2'],              # Regularization types
    'solver': ['liblinear']               # Solver to use
}


### Word to vector:

Also tried word to vector with logistic regression, but it gave less accuracy <85% so  
TF-IDF vectorizer was selected for the good accuracy

**Deep Learning Models**:
LSTM`-  Gave 86% accuracy, it is a good accuracy, but there is seemed to be some bias in it.

**Transformers**:

Used Roberta for sentimental analysis, it predicted and gave result in binary values

and also gave score for each reviews for its findings, overall performance was good.

## Classification analysis:

And also done analysis in classification to identify the class name by the model

**Best model for classification analysis:**

Logisticregression with hyper parameter tuning Gridsearch gave the average accuracy 

of 64%

**Deep Learning lstm model:**

It gave the accuracy of 61%, less compared to  logisticregression

Evaluation metrics:

The following evaluation metrics are used to evaluate the performance of the model

Precision , Recall, F1score

It is finalized that logisticregression with gridsearch gave the best accuracy without any bias.
