# Bank marketing
## Introduction

A term deposit is a fixed-term investment that includes the deposit of money into an account at a financial institution. Term deposit investments usually carry short-term maturities ranging from one month to a few years and will have varying levels of required minimum deposits. The investor must under- stand when buying a term deposit that they can withdraw their funds only after the term ends. In some cases, the account holder may allow the investor early termination or withdrawal if they give several days notification. Also, there will be a penalty assessed for early termination.
The data is related with direct marketing campaigns (phone calls) of a Portuguese banking institution. The classification goal is to predict if the client will subscribe a term deposit by using the Bank Marketing Data set provided by Moro et al.

---

Final project for the Mathematics in Machine Learning course @ PoliTo

---

## EDA
The Bank Marketing Data Set is composed by 768587 records. For each record we have information about the personal data about the potential clients. Infor- mation about the previous investment can be also found. The target variable indicates whether a term deposit will be subscribed or not. We can distinguish both numerical and categorical features.

---

## Preprocessing
### Features encoding

The encoding techniques that we used are:
- one-hot encoding: Assigns vectors to each category. The vector represent whether the corresponding feature is present (1) or not (0)
- label encoding: it is based on the idea of converting each value in a column to a number

### Features scaling
Feature scaling is a method used to normalize the range of independent vari- ables or features of data. In our case we transformed our distribution in order to have μ = 0 σ = 1 This step will be fundamental for the following parts of the process, both for PCA and model training.

### PCA (Dimensionality reduction)
Principal Component Analysis, or PCA, is a dimensionality-reduction method to find lower-dimensional space by preserving the variance as measured in the high dimensional input space. It is an unsupervised method for dimensionality reduction. PCA transformations are linear transformations.
PCA can be also seen as a Variance maximization problem, so the main idea is to find a sort of balance between the number of components selected and the portion of variance explained. Generally, we want to achieve an explained variance at least in the range of [80% - 90%].
Of course, with the reduction of the number of features we will have a decrease of the accuracy of the model too, but the benefits will be more in- fluential. We can analyze, visualize and explore data in a simpler way, all of this with a minor computational complexity. The key point of this algorithm is to reduce the number of features while preserving information as much as possible.

### Resampling
Resampling is a very important preprocessing technique which consists of work- ing on the training set in order to reach a more balanced working space than the inital one. Resampling can be done in different ways.
- Undersampling: This technique consists of removing records from the majority class in order to balance. The simplest undersampling technique involves randomly selecting examples from the majority class and deleting them from the training dataset. Altough simple, it is not very effective, so the idea is to use heuristics based algorithm to remove useless records
- Oversampling:It consists of adding synthetic samples of the minority. The goal can be achieved by simply duplicating examples from the minority class in the train- ing dataset prior to fitting a model.The most effective algorithm in this scenario is SMOTE (Synthetic Minority Oversampling Technique) which works by selecting examples that are close in the feature space, drawing a line between the examples in the feature space and drawing a new sample at a point along that line.

## Model evaluation
An evaluation metric quantifies the performance of a predictive model. This typically involves training a model on a dataset, using the model to make predictions on a holdout dataset not used during training, then comparing the predictions to the expected values in the holdout dataset. The most used metrics to evaluate a classification model are:
• Accuracy = TP+TN TP+TN+FP+FN
 •Precision= TP TP+FP
•Recall= TP TP+FN
• F 1 = 2×P recision×Recall = P recision+Recall
2×T P
2×T P +F P +F N


