---
id: kuwbzu69c3mhulobjgu0v5m
title: Textclassification
desc: ''
updated: 1646908950394
created: 1646295448228
---
# Text Classification
Sentitment analysis is not simple text classification

- Lot of people still do hand coded rules to classify text: Needs a lot of work (expert knowledge)
- Supervised machine learning (Labeling is required)
  - Learn the relationship between text and label

- a set of document $D$
- a fixed set of $N$ classes $C$
- a training set of $M$ hand-labeled documents ($d_1$, $c_1$), . . . ,($d_M, c_M$)

- a mapping $D \to C$ that associates a predicted class $c \in C$ to each
document $d \in D$

- Naïve Bayes
- Logistic regression
- Support-vector machines (SVM)
- k-Nearest Neighbors

![Naïve Bayes concept](/assets/images/2022-03-03-09-28-57.png)
Its called naive because it assumes that the features are independent of each other. 
![Bayes theorem](/assets/images/2022-03-03-09-31-50.png)

[[MAPClassifier]] is also called maximum a posteriori (MAP) classifier.

$argmax_{c \in C} \frac{P(d|c)P(c)}{P(d)} = argmax_{c \in C} P(d|c)P(c)$

Bernoulli model (if word is in document) or multinominal model when $f_i$ is a count of the number of times the word $i$ appears in the document.

Naive bayes is the probability of class c with the product of conditioanl probabilities of each word in the document.

$$c_{nb} = \text{arg max}_{c \in C} P(c) \prod_{k = 1}^N P(x_k | c)$$

**Slide 18** every class observed $\frac{1}{3}$

## Evaluation

### Accuracy
### Precision
Fraction of test documents classified as c that have been correctly classified - only look at the predicted class

$$P_c = \frac{TP}{TP + FP}$$
### Recall
The fraction of test document labeld as c that have been correctly classified - look a the test labels given by the data

$$R_c = \frac{TP}{TP + FN}$$
### $F_1$ Score
Harmoic mean of precision and recall

### Confusion Matrix
Gives an overview about the performance of your model. 

![Confusion Matrix](/assets/images/2022-03-10-09-50-12.png)
Accuarcy is 2/3 - sum of diagonal from top right to bottom left divided by the overall sum.

Precision: given a column (i.e., a predicted label), element on main diagonal over sum of matrix column - geneva example: $\frac{1}{1}$


Recall: given a row (i.e., a test label), element on main diagonal over sum of matrix row - bern example $\frac{1}{2}$
**Only works this when test labels on the left handed side and predicted labels on the bottom - caution - it could flip!**

# Final Exam Help
- [ ] Recalculate all the Metrics

[[mse.ss22.finalexams]]



