---
id: 62cc8vdtyhx5uaodpdgndpw
title: Multi-Layer Perceptron
desc: ''
updated: 1646917257202
created: 1646914145439
---
[[mse.ss22.sw03]]
# Recap
First forward propagation and then the backward propagation

In Mini-Batch GD - you get further performance by using a mini-batch of data.
CrossEntropy does not use the softmax output but it uses the logits.

**Keep a n eye on the shapes of the Tensors** - print shapes etc...

# Multi Layer Perceptrons (MLP)

## Rosenblatt (1958)
Only returns values {0, 1}
Needs to be linearly separable and works only with one perceptron
XOR Problem not solved by Rosenblatt perceptron as it is not linearly seperable

- sigmoid 
- tanh
- Recti-Linear Unit (ReLU)

MLP are not linear anymore as we have the non-linear activation functions

## Forward pass

We have forward and backward pass 
- forward - calc results
- backwards - calc gradients

BackProp was formulated in the 1975
Compuntational Graph possible

## MLP Layer
1. Activation from previous layer
2. Weights and Bias caluclated
3. Activation applied to weights and bias

Weights are in a $n_l * n_{l-1}$ matrix

![Composed Graphs](/assets/images/2022-03-10-13-48-27.png)

Implies nested function calls

## Chain rule
![Chain rule -nested](/assets/images/2022-03-10-13-50-47.png)
Chain rule because we have nested function calls

$$f'(g(x)) = f'(g(x))*g'(x)$$
$$J_{f o g(x)}(x) = J_f(g(x)) * J_g(x)$$ jacobian

Slide 33 is good for learning

Starting with the green derivative and then go to the green one which gives teh result of all these derivatives (g\*r\*b)

![MLP with two inputs](/assets/images/2022-03-10-13-58-35.png)
We have two input variables and therefore ned to multiply the deriviatives

![MLP with two outputs](/assets/images/and%20now%20wit.png)
here the calculation is done with two outputs - apply them together as the sum



