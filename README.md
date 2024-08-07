### MachineLearningNotes
##### Notes on Machine Learning
  
Notes built from:  
 - Google Devleopers Machine Learning Series YouTube videos https://www.youtube.com/watch?v=cKxRvEZd3Mw
 - Coursera Machine Learning course (Stanford University/Andrew Ng) https://www.coursera.org/learn/machine-learning/
 - ISL (Introduction to Statistical Learning) Textbook http://www-bcf.usc.edu/~gareth/ISL/
 - Kaggle's 30 Days of Machine Learning
 - Approaching Almost Any Machine Learning Problem by Abhishek Thakur  
 
From Coursera Lecture "What is Machine Learning"  
https://www.coursera.org/learn/machine-learning/lecture/Ujm7v/what-is-machine-learning  
Machine Learning is having a computer learn how to succeed in a task by watching experience and improving performance on a task based on that experience  

##### Supervised Learning v Unsupervised Learning  
Supervised: you teach the computer - ie looking for a prediction  
Unsupervised: Computer learns for itself - not predictive, but more classification and descriptive. 


##### Supervised Learning:
#### Regression v Classification
##### Regression problem
Example - have data, can use straight line or quadratic equation to calculate an expected result
  - an age of a person, a price of a house, a closing price of a stock 

##### Classification problem   
Example: 0 or 1 problem, need to choose between defined choices
  - a yes or no answer, a stock up or down 
    - may have two categories, may have more than two
  
##### Unsupervised Learning
 - given this dataset, can the machine find structure?
 - Clustering - how to identify groupings?   
###### K Means
 - Randomly assign cluster centroid
   - Compute mean of points assigned to each group, then move the cluster centroid to the mean point
   - recompute which points are now assigned to the centroid, and repeat process  
 - Parameters
 
#### Model and Cost Function Section
 - Hypothesis (h) is tested on how X maps to Y
    - Hypothesis probably not best word, but is standard terminology
    - Choose Intercept and slope (Theta 0, Theta 1) to minimize square of diffs between h(x) and actual y
    - J() is what we are minimizing - the squared error cost function - The MSE
  
##### From ISLR 2.2 pg 29 (7th ed)    
>There is no free lunch in statistics: no one method dominates all others over all
possible data sets. On a particular data set, one specific method may work
best, but some other method may work better on a similar but different
data set. Hence it is an important task to decide for any given set of data
which method produces the best results. Selecting the best approach can
be one of the most challenging parts of performing statistical learning in
practice.    
##### Overfitting and Underfitting  
Overfitting: Tuning to the training data perfectly, but doesn't translate to test data - ie model is too specific to training data  
Underfitting: Model isn't granular enough to give a useful result, dive deeper into training data to see what else can be used  
Ultimately want the lowest MSE on validation data  
Example of looping through numbers of leaf nodes to reduce MSE:  
https://github.com/Jazielinho/kaggle-30-days/blob/master/day_10/underfitting-and-overfitting.ipynb

##### ISLR 2.2.1 pg 32 (7th ed)
>When a given method yields a small training MSE but a large test MSE, we are
>said to be overfitting the data. This happens because our statistical learning
>procedure is working too hard to find patterns in the training data, and
may be picking up some patterns that are just caused by random chance
rather than by true properties of the unknown function f. When we overfit
the training data, the test MSE will be very large because the supposed
patterns that the method found in the training data simply don’t exist
in the test data. 

#### Variable and bias in training data, ISLR pgs 34-35
>__Variance__ refers to the amount by which ˆf would change if we
estimated it using a different training data set. Since the training data
are used to fit the statistical learning method, different training data sets
will result in a different ˆf. But ideally the estimate for f should not vary
too much between training sets  
>__Bias__ refers to the error that is introduced by approximating
a real-life problem, which may be extremely complicated, by a much
simpler model. 
>Generally, more flexible methods result in less bias.  
__Bias Variance Trade Off__ p36 ISLR  
>Good test set performance of a statistical learning method re- bias-variance
quires low variance as well as low squared bias. This is referred to as a trade-off
trade-off because it is easy to obtain a method with extremely low bias but
high variance (for instance, by drawing a curve that passes through every
single training observation) or a method with very low variance but high
bias (by fitting a horizontal line to the data). The challenge lies in finding
a method for which both the variance and the squared bias are low.

#### Bayes Classifier  (ISLR pg 37-39)
>Simple classifier, gives prob of Y category given value of X. In theory we would always like to predict qualitative responses using the Bayes classifier. But for real data, we do not know the conditional distribution
of Y given X, and so computing the Bayes classifier is impossible.
Therefore, the Bayes classifier serves as an unattainable gold standard
against which to compare other methods.  

  
  
#### ISL 3.2.2 - Multiple Regression: deciding which variables are important  
 - Forward Selection: test all variables individually, selected lowest RSS, then select remaining variables with that selection, repeat until reasonable criteria satisfied  
 - Backward Selection: test all variables in one model, remove variable with highest P Value, repeat until no P Value requires elimination  
 - Mixed Selection: Start with Forward Selection process, but then remove variables where P Value then rises as testing continues. This fixes issues with Forward Selection where variables become redundant.    
##### Model Fit
 - A small increase in R^2 does not indicate an additional variable was valuable - needs to be a fair sized increase
##### Prediction Error (ISL p 82)
>Prediction intervals are always wider than confidence intervals, because they
incorporate both the error in the estimate for f(X) (the reducible
error) and the uncertainty as to how much an individual point will
differ from the population regression plane (the irreducible error).  

#### Handling Missing Data  
<b>Imputation</b> - Imply a value based on other similar values in data  
Can also note in data what values were imputed: https://github.com/Jazielinho/kaggle-30-days/blob/master/day_12/missing-values.ipynb  
  - may give additional error reduction  
  
#### Qualitative Variables (ISL 3.3.1)
 - Can be signified with dummy variables (0 or 1) 
   - Male/Female, East/West
   - can go multiple levels with a series of dummy variables (ie if have five choices, use 1 as baseline and 4 dummy variables)
#### Categorical variables  
  Have limited number of values, sometimes a ranking, or sometimes purely qualatative  
  <b>Ordinal Encoding</b> - can use on ranked variables, where there is a logical "0", "1", "2", etc  
  <b>One Hot Encoding</b> - creates a new set of columns for each choice, denoting the existence of that choice as a 0/1  
  
#### Interaction terms (ISL 3.3.2)
 - account for the combination of two linear factors
 - include multiplied x1 * x2 as a separate factor in model
 - if including interaction multiplier, should also keep both the base x1 and x2 even if high P value for one of them
 
#### Non-linear data (ISL 3.3.2)
 - Polynomial Regression is a simple way to attempt to fit non linear data. 
   - Can use X^2, X^3, X^4, as many polynomial terms as seem to smooth out fit
   - Can also use logX, sqrtX  
    
#### Collinearity (ISL 3.3)
Variables that have high correlation may throw off model results
 - Inspect correlation matrix between variables
 - Having two highly correlated variables will increase the std error and the P Value for one/both
 - Can eliminate one variable, or combine both into one new variable  
   
### Classification (ISL 4)  
Classification problems look for a qualitative response  
  
##### Logistic Regression (ISL 4.3)  
 - Models the probability of being in 1 of 2 categories given input
   - ie Yes/No questions, pass/fail, win/loss, etc
    
##### Linear Discriminant Analysis (ISL 4.4)   
 - is often more stable than Logistic Regression  
 - Can handle multipe classes, while Logistic is better for 2 classes (though Logistic can handle more)  
 - Approximates Bayes Classifier  
 - From ISL 4.4.2:
   - > LDA classifier results from assuming that the observations within each class come from a normal distribution with a class-specific mean vector and a common variance σ2, and plugging estimates for these parameters into the Bayes classifier  
 - With LDA, can change threshold of classification (so instead of needed 50% of criteria, can flag at 20%, etc.  
   - for use when you may not care about how one group performs, but want flags for anyone possible in another group  
   
##### ROC Curve (ISL 4.4.3)
 - go back and review, perhaps look up another source. interesting/useful but i didn't quite grok it.
  
##### KNN - K Nearest neighbors  
- non-parametric approach, as opposed to LDA, Logistic regression  
  - performs better then LDA and Logistic when decision boundary is non-linear  
  - KNN does not tell us which predictors are important  
- looks at data point, see what the K nearest neighbors to that data point by distance are, and the majority of K that have the same result is your result  
   - KNN should be scaled, see http://scikit-learn.org/stable/modules/preprocessing.html  
 - Need to have right fitting for K to reduce error on test data
   - 1 will be perfect on training data, but too granular to be useful for test data
   - ISLR 2.2.3 pgs 40-42 demonstrates examples of the impact of this
   - Too high K, and starts to turn into linear regression  
 - Two common modifcation (from ISL):  
   - Kernel methods use weights that decrease smoothly to zero with distance from the target point, rather than the effective 0/1 weights used by k-nearest neighbors.
   - In high-dimensional spaces the distance kernels are modified to emphasize
some variable more than others.  
   
 
#### Decision Tree  
 - series of True/False questions developed by the code to get to an end decision  
#### Random Forest  
 - Uses a series of trees, decision made by averaging predictions of each tree  
   
##### Support Vector Machine (SVM)  
Good outline:  
https://medium.com/machine-learning-101/chapter-2-svm-support-vector-machine-theory-f0812effc72   
##### Gridsearch in SVM    
Gridsearch is a method to test an array of settings to find best output:  
https://github.com/juinc/python_data_science_and_machine_learning_bootcamp/blob/master/Machine%20Learning%20Sections/Support-Vector-Machines/Support%20Vector%20Machines%20with%20Python.ipynb   
 
 ##### Other notes
 Accuracy, precision and F1 score:  
 basics here: http://blog.exsilio.com/all/accuracy-precision-recall-f1-score-interpretation-of-performance-measures/
  - Accuracy: overall accuracy, intuitively  
  - Precision: True Positives/(True Positives + False Positives)  
  - Recall: True Positives/(True Positives + False Negatives)  
  - F1 Score: Formula balances Precision and Recall. 
  
#### Resampling - Cross Validation and Bootstrap
##### k-fold cross validation
 - Slicing the data up in fixed chunks so the fitting and validation is performed on different combinations each time and results are overall combined
 - Can be useful for smaller data sets with limited observations, larger data sets may not need cross validation      
  https://github.com/justmarkham/scikit-learn-videos/blob/master/07_cross_validation.ipynb
  https://github.com/Jazielinho/kaggle-30-days/blob/master/day_13/cross-validation.ipynb

##### Ensemble Methods
 - combine results of several models to get an overall improved result
 - Random Forest is an example
 
##### Gradient Descent  
Basic concept outlined with code: https://medium.com/@rohanjoseph_91119/implement-gradient-descent-in-python-9b93ed7108d1  
Another conceptual outline with code: http://ml-cheatsheet.readthedocs.io/en/latest/gradient_descent.html

##### XGBoost
 - Software library for gradient descent, works well with tabular data
 - https://github.com/Jazielinho/kaggle-30-days/blob/master/day_14/xgboost.ipynb
 
 

