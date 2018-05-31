### MachineLearningNotes
##### Notes on Machine Learning 

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

  
##### From Google Devleopers Machine Learning Series:
 - KNN - K Nearest neighbors - looks at data point, see what the K nearest neighbors to that data point by distance are, and the majority of K that have the same result is your result  
 - - KNN should be scaled, see http://scikit-learn.org/stable/modules/preprocessing.html
 - Decision Tree - series of True/False questions developed by the code to get to an end decision  
 
   
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
  
#### interesting idea/concept:
k-fold cross validation
 - Essentially slicing the data upbin various ways so the fitting and validation is performed on different oarts each time and results are overall   
 
 https://github.com/justmarkham/scikit-learn-videos/blob/master/07_cross_validation.ipynb. 
 
 Review these. 
 https://www.google.com/amp/www.dataschool.io/machine-learning-with-scikit-learn/amp/. 
 
 scikit flow combines scikiy and tensorflow capabilities:. 
 
https://www.kdnuggets.com/2016/02/scikit-flow-easy-deep-learning-tensorflow-scikit-learn.html. 
