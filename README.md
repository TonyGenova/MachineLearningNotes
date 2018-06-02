### MachineLearningNotes
##### Notes on Machine Learning
  
Notes built from:  
 - Google Devleopers Machine Learning Series YouTube videos https://www.youtube.com/watch?v=cKxRvEZd3Mw
 - Coursera Machine Learning course (Stanford University/Andrew Ng) https://www.coursera.org/learn/machine-learning/
 - ISL (Introduction to Statistical Learning) Textbook http://www-bcf.usc.edu/~gareth/ISL/
 
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

##### - KNN - K Nearest neighbors  
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
 
   
##### Support Vector Machine (SVM)  
Good outline:  
https://medium.com/machine-learning-101/chapter-2-svm-support-vector-machine-theory-f0812effc72   
  
 
 ##### Other notes
 Accuracy, precision and F1 score:  
 basics here: http://blog.exsilio.com/all/accuracy-precision-recall-f1-score-interpretation-of-performance-measures/
  - Accuracy: overall accuracy, intuitively  
  - Precision: True Positives/(True Positives + False Positives)  
  - Recall: True Positives/(True Positives + False Negatives)  
  - F1 Score: Formula balances Precision and Recall. 
  

#### k-fold cross validation
 - Slicing the data up in various ways so the fitting and validation is performed on different Parts each time and results are overall combined.    
  https://github.com/justmarkham/scikit-learn-videos/blob/master/07_cross_validation.ipynb. 
 
 Review these. 
 https://www.google.com/amp/www.dataschool.io/machine-learning-with-scikit-learn/amp/. 
 
 scikit flow combines scikiy and tensorflow capabilities:. 
 
https://www.kdnuggets.com/2016/02/scikit-flow-easy-deep-learning-tensorflow-scikit-learn.html. 
