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
    
##### Support Vector Machine (SVM)  
Can handle an infinite number of features (X variables?)  
  
##### Unsupervised Learning
 - given this dataset, can the machine find structure?
 - Clustering - how to identify groupings?  
 -  
  
  
##### From Google Devleopers Machine Learning Series:
 - KNN - K Nearest neighbors - looks at data point, see what the K nearest neighbors to that data point by distance are, and the majority of K that have the same result is your result  
 - Decision Tree - series of True/False questions developed by the code to get to an end decision  
 
 
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
 https://www.google.com/amp/www.dataschool.io/machine-learning-with-scikit-learn/amp/

