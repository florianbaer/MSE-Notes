
[[mse.ss22.sw04]]
[[MSE]] Topic: [[DeLearn]]

## Recap

## Learning Model from Data

form probability distribution denoted by $ Z \approx P(\cdot)$

supervised learning
- features with given labels

unspuervised learning
- e.g. density estimation without labels

define a loss function $f,z \to L(f,z) \ge 0$
- CE Loss
- MSE Loss

minimize statistical / expected risk of the model
### Statistical Risk
Not tractable (handhabbar)

### Empirical Risk, Cost

create a model from samples and sum the loss of all the sample 
![Empirical Risk (Cost)](/assets/images/2022-03-17-13-34-13.png)
Does not generalize 

### Parametric Empirical Risk minimazation

Transform model into parametric model to find optimal parameters

### Shaping solutions
- increate numebr of samples
- selection of a suitable class of parametric model
  - crucial that the solution work with new data
  - choose the most simple model if multiple models performe equally well (what is simple?)
- adjust the loss function (make the solution less dependent on the training data)
  - regularization
  - margin maximization
  - ensemble methods

### Error Decomposition
Error contains the following components:
- variance
- bias
![Variance and Bias in Model](/assets/images/2022-03-17-13-48-46.png)
which both are dependent on the performance of the model

Visual overfitting for further analysis as in the image below
![Furhter analysis of overfitting](/assets/images/2022-03-17-14-03-39.png)

**Neural Networks are rather low variance learners**
![Neural Network learning](/assets/images/2022-03-17-14-12-01.png)


### Deep double descent
Problem of neural Networks which increase performance with more layers. But inference time is decreasing with more layers.
![deep double descent](/assets/images/2022-03-17-14-36-32.png)

# Overfitting problems 

Regularization methods

- contrain model parameters (weight penalty)
- early stopping (before high variance occurs)
- add noise to training process
- increase variety in training data
## weight penalty
$C = C_0 + \lambda\Omega(W) \quad \text{where} \quad (\lambda \ge 0)$ 

## Gradient Descent

![Gradient Descent with weight decay](/assets/images/2022-03-17-14-52-37.png)

there is $L_1$ and $L_2$ regularization. 
green is $L_1$ and red is $L_2$

![Regularization](/assets/images/2022-03-17-15-00-25.png)

## Dropout
Very versatile (vielseitig)

Example of dropout $\to$ flip coin if you should go to work. Company would be less dependent on single employees but has to adapt the organization.

# Model selection
- Big model
  - 98% / 1% / 1%
- small model
  - 60% / 20% / 20%

## Hyper Parameters
- number of neurons
- number of layers
- learning rate
- batch size
- epochs
- dropout
- weight decay (regularization)

## Learning curve analysis

## k-fold cross validation












