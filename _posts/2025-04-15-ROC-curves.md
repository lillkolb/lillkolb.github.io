# ROC curves  

## What is an ROC curve?  

ROC (Receiving Operating Characteristic) curves are used to evaluate binary classification models (i.e models where the machine is required to asnwer a "yes" or "no" question). 
![image](https://github.com/user-attachments/assets/e5a07f69-68fe-4409-bf52-756d40f73105)
ref: [link for image](https://spotintelligence.com/2024/06/17/roc-auc-curve-in-machine-learning/)

An important aspect of the ROC curve is the **Area Under Curve (AUC)**. As we can see from the image above, the better the performance of 
the model, the more curved it is to the top left corner of the graph. As the AUC directly corresponds to the bend of the curve, we can 
essentially numerically evaluate the model, with larger AUC values suggesting a more effective model. Furthermore, if the AUC value is 
less than 0.5, it suggests that the model is not effective at all, and is no better than random guessing. 

## Distinguishing between TP, TN, FP, FN  

Suppose we are comparing 2 colours, a and b respectively:  
**True Positive** - when a == b and the machine finds a == b as well  
**False Positive** - when a != b but the machine finds a == b  
**True Negative** - when a != b and the machine finds a != b as well  
**False Negative** - when a == b but the machine finds a != b  
To make it easier to remember, you can associate the 2nd word with what the machine thinks, and the 1st on if it's right or wrong.   

## How to calculate TPR (sensitivity) and FPR (1 - specificity)  

The **True Positive Rate** and **False Positive Rate** are used as the axis for an ROC curve.  

To calculate the **True Positive Rate** we use the following equation:  
TPR = $\frac{True Positives}{(True Positives + False Negatives)}$  
We aim to have a larger true positive rate. 

To calculate the **False Positive Rate** we use the following equation:  
FPR = $\frac{False Positives}{(False Positives + True Negatives)}$  
We aim to have a samller false positive rate.  


## Creating an ROC curve in python

In python, we can import the sklearn.metrics module (with `from sklearn.metrics import roc_auc_score, roc_curve`) to help us plot the 
curve. (We will also use numpy and matplotlib.pyplot libraries)  
**roc_curve** `fpr, tpr, thresholds = roc_curve(true_values_array, scores_array)`  
fpr - an array of false positive rate values  
tpr - an array of true positive rate values  
thresholds - an array of thresholds  
true_values_array - an array which indicates (with 1's and 0's) whether the input at the position should evaluate to true or false  
scores_array - an array that stores the score for each input from the machine  

e.g suppose we want our machine to evaluate whether an image colour is red or not red. We are given and input order of r-g-b-b-r-r-g.  
Then true_values_array = \[1 0 0 0 1 1 0\]  
and scores_array = \[0.78 0.45 0.34 0.31 0.67 0.82 0.53\] (example scores)  


**Example code:**  
``
    fpr, tpr, thresholds = roc_curve(true_values_array, scores_array)  
    plt.plot(fpr, tpr)  
    plt.title(template_filename)  
    plt.xlabel('False Positive Rate')  
    plt.ylabel('True Positive Rate')  
    plt.show()  
    print(f'AUC score: {roc_auc_score(true_values_array, scores_array)}')  
``


### Links you should check out:  
[Machine learning mastery](https://machinelearningmastery.com/roc-curves-and-precision-recall-curves-for-classification-in-python/)  

