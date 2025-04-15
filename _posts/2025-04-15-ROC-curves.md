# ROC curves  

## What is an ROC curve?  

ROC (Receiving Operating Characteristic) curves are used to evaluate binary classification models (i.e models where the machine is required to asnwer a "yes" or "no" question). 
![image](https://github.com/user-attachments/assets/e5a07f69-68fe-4409-bf52-756d40f73105)
ref: [links](https://spotintelligence.com/2024/06/17/roc-auc-curve-in-machine-learning/)



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


##### Links you should check out:  
[links](https://machinelearningmastery.com/roc-curves-and-precision-recall-curves-for-classification-in-python/)  

