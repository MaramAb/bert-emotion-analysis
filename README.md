# Emotion Analysis Using BERT
This repository represents a section of my graduation project where we use BERT-base with fine-tuning to predict emotions from English and Arabic tweets. 
<!-- In this project, we test the performance of the pre-trained language model BERT-base on the task of emotion analysis in English and Arabic tweets. -->

## Dataset
In this project, we use the SemEval-2018 Task 1: Affect in Tweets [(AIT-2018)](https://competitions.codalab.org/competitions/17751#learn_the_details-datasets) dataset, specifically, El-oc. 

The dataset contains four classes: 
* Anger
* Joy
* Fear
* Sadness

To simplify the process, we neglected the emotion's intensity and only focused on the emotion class. Furthermore, we performed stratified sampling to split the data into training (70%), validation (10%), and testing (20%) sets. Each of which contains a representative sample of the original data with consistent proportions for each emotion.

## Hyperparameters
We tested the following values for the max sequence length, batch size, and learning rate hyperparameters:
* max sequence length: 64, 128, 256
* batch size: 8, 16, 32
* learning rate: 1e-4, 2e-5, 5e-5

The number of epochs was set to 3 for both English and Arabic experiments. 

We found that the best set of hyperparameters for English were 64, 16, and 5e-5 as the max sequence length, batch size, and learning rate respectively. For Arabic, the best hyperparameters were 64, 16, and 2e-5 as the max sequence length, batch size, and learning rate respectively.

## Performance
These were the best achieved results for English and Arabic. 

**English**
```
              precision    recall  f1-score   support

         joy       0.89      0.78      0.83       618
     sadness       0.80      0.89      0.84       605
        fear       0.91      0.90      0.91       592
       anger       0.82      0.85      0.84       404

    accuracy                           0.86      2219
   macro avg       0.86      0.86      0.85      2219
weighted avg       0.86      0.86      0.86      2219

```
**Arabic**
```
              precision    recall  f1-score   support

           0       0.71      0.65      0.68       280
           1       0.73      0.83      0.78       160
           2       0.90      0.93      0.91       280
           3       0.67      0.64      0.66       160

    accuracy                           0.77       880
   macro avg       0.75      0.76      0.76       880
weighted avg       0.77      0.77      0.77       880

```



