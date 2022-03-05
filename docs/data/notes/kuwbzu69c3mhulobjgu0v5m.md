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

$$c_{nb} = \text{arg max}_{c \in C} P(c) \product_{k = 1}^N P(x_k | c)$$

**Slide 18** every class observed $\frac{1}{3}$
