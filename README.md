## Predicting Loan Eligibility
Loan companies make their major profit from loan interests. Loan companies grant a loan after an intensive process of verification and validation. However, these loan companies do not know if the applicants will repay the loans without difficulties.

The purpose of this project is to build various predictive models to help determine if an applicant will be able to repay his or her loan, and to test the accuracy of the various models. 
The models inlcude the following:
* K Nearest Neighbor(KNN)
* Decision Tree
* Support Vector Machine
* Logistic Regression

## Getting the system ready and loading the data
We will be using Python for this course along with the below-listed libraries:
* Python
* pandas
* seaborn
* sklearn

## About the dataset
This dataset is about past loans. The Loan_train.csv data set includes details of 346 customers whose loan are already paid off or defaulted. It includes following fields:

| Field          | Description                                                                           |
|----------------|---------------------------------------------------------------------------------------|
| Loan_status    | Whether a loan is paid off or in collection                                           |
| Principal      | Basic principal loan amount                                                    |
| Terms          | Origination terms which can be weekly (7 days), biweekly, and monthly payoff schedule |
| Effective_date | When the loan got originated and took effects                                         |
| Due_date       | Since it’s one-time payoff schedule, each loan has one single due date                |
| Age            | Age of applicant                                                                      |
| Education      | Education of applicant                                                                |
| Gender         | The gender of applicant                                                               |


## Analyzing each of the ML models:

#### K Nearest Neighbor(KNN)
First, we will find the best k to build the model with the best accuracy. For that, we will split our train_loan.csv into train and test to find the best __k__. We calculate the accuracy score of KNNs for different Ks and plot model accuracy for different number of Neighbors.

#### Decision Tree
We construct an image of the actual decision tree in terms as a flowchart using all features (independent variables).

#### Support Vector Machine
We iterate for different kernels like Linear, Polynomial, Radial basis function (RBF) and Sigmoid to arrive at the one which best fits the data curve.

#### Logistic Regression
For this model, we use a User Defined Fun-ction to plot the coloured confusion matrix (without normalization so that we can analyze the distribution of True Positives/ False Positives/ True Negatives/ False Negatives 

## Model Evaluation using Test set
We finally evaluate the accuracy of each of these models against a separate test set (on which the model was not trained), to check the out-of-fold prediction capability of the models. We do this using by calculating 2 indicative parameters: __Jaccard Index__ & __F1 score__. Additionally we also plot the precision and recall values (True Positives/ False Positives/ True Negatives/ False Negatives) for each model to get better visibility on the cases where it is failing. For the Logistic Regression model, we use an adiditional parameter called the Log Loss.

# Conclusion
Lastly, we report the accuracy of the built models using different evaluation metrics:

| Algorithm          | Jaccard | F1-score | LogLoss |
|--------------------|---------|----------|---------|
| KNN                | 0.74    | 0.73    | NA      |
| Decision Tree      | 0.74    | 0.75     | NA      |
| SVM                | 0.74    | 0.63     | NA      |
| LogisticRegression | 0.75    | 0.69     | 0.58    |

In general we see high sensitivity/recall values (F1 scores) in our models for the head of 'PAIDOFF'. This seems to be because of a higher number of entries which have been paid off in the source dataset. Therefore to predict default, we need more test data. The same can be verified via the confusion matrix which shows higher number of false negatives (i.e for 'Collection' loan repayment status)

Though we see that the Decision Tree Algorithm provides the best output, other algorithms are not far behind. These models can be improved further using different solvers and higher number of iterations to make them slightly better.
