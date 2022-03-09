---
id: me7llsjqm8u04nhwpg98pkl
title: Learningandoptimization
desc: ''
updated: 1646317261196
created: 1646309519136
---
# Learning and Optimization

Target for this week: Gradient Descent / stochastic gradient descent


## General Regression Problem

Learning a numeric value from a set of datapoints.

## Classification Problem

Classification of a set of datapoints into a set of classes.

Full Batch Gradient Descent
Mini-Batch Gradient Descent or Stochastic Gradient Descent
- You need to make the learning rate smaller with stochastic gradient descent
- Less epochs needed - as per Batch the calculation is done
- Calculation-Time is increaed per Epoch, as calculation is done per batch

## Hyperparameters
- Batch Size
  - $\epsilon \sim \frac{1}{\sqrt{\text{batchsize}}}$
- Learning rate
  - $\epsilon \sim \alpha$

Error bars scale with the learning rate $\alpha$

Watch `torch.nn.CrossEntropyLoss`

# ToDos
- [ ] Watch the math behind DeLearn