# What I've learnt from fastai


## Definitions

**Batch size** - Batch size refers to the number inputs that are processed in one iteration when training a model.  
**Epoch** - Epoch refers to the number of time a training batch is passed through a model.  

## What is a confusion matrix?

A confusion matrix is used to evaluate a classification model. It compares predictions to the accurate results, and can also show when mistakes are made by the model. It can also be used to see which classes the model can get confused by.  

![image](https://github.com/user-attachments/assets/47dc746f-2ac8-440f-88b9-3ee1c1635de6)  
Example matrix from A2  

As you can see from the cell with 4 in it, there are cases where matrix has confused birds with planes. (Is it a bird? Is it a plane?)  

To create this matrix:  
```
interp = ClassificationInterpretation.from_learner(learn)
interp.plot_confusion_matrix()
```  
where "learn" is the vision_learner
