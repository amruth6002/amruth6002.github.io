---
layout: post
title: Optimizers in machine learning and deeplearning from scratch
---

In this blog i will explain the optimizers in machine learning and deeplearning from scratch. I will explain the following optimizers:

1.) [vanilla Gradient Descent](#vanilla-gradient-descent)

2.) [Stochastic Gradient Descent (SGD)](#stochastic-gradient-descent-sgd)

3.) [Momentum](#momentum)

4.) [RMSprop](#rmsprop)

5.) [Adam](#adam)

## Vanilla Gradient Descent

Vanilla Gradient Descent is the most basic optimization algorithm used in machine learning and deep learning. It updates the model parameters by calculating the gradient of the loss function with respect to the parameters and moving in the opposite direction of the gradient.

[Why gradient points in the direction of steepest ascent?](https://www.youtube.com/watch?v=QQPz3eXXgQI&pp=ygUwd2h5IGRpZXMgZ3JhZGllbnQgcG9pbnRzIHR3b2FyZHMgc3RlZXBlc3QgYXNjZW50)

lets take 50 random points and implement gradient descent-:
<details>
<summary>Click to see raw data points</summary>

**X values:**
```
[ 0.          0.20408163  0.40816327  0.6122449   0.81632653  1.02040816
  1.2244898   1.42857143  1.63265306  1.83673469  2.04081633  2.24489796
  2.44897959  2.65306122  2.85714286  3.06122449  3.26530612  3.46938776
  3.67346939  3.87755102  4.08163265  4.28571429  4.48979592  4.69387755
  4.89795918  5.10204082  5.30612245  5.51020408  5.71428571  5.91836735
  6.12244898  6.32653061  6.53061224  6.73469388  6.93877551  7.14285714
  7.34693878  7.55102041  7.75510204  7.95918367  8.16326531  8.36734694
  8.57142857  8.7755102   8.97959184  9.18367347  9.3877551   9.59183673
  9.79591837 10.        ]
```

**Y values:**
```
[-1.84906502  0.14796499  5.76343969  3.29772247  1.33574199  7.55969436
  3.07641734  2.29625206  3.11890568  2.83164312  8.86090267  2.88772778
  6.25586976  4.80492513  4.24172485  6.30030025  8.94647707  8.73120931
  8.16654723  7.66207554  8.05660718  7.61485529  7.33576776  7.58932481
 11.64422524 12.52849745 13.12640632 11.82546752 11.80469967 12.17155883
 15.4460859  15.0538789  18.26404008 17.07964007 10.91760557 13.23503321
 12.16853572 19.50415138 15.46385096 13.79271726 18.39178177 19.47646076
 18.08185461 20.35487431 18.55772308 20.53339024 17.35817452 20.47327344
 21.03137291 21.40791631]
```
</details>

we can see vizualization of data below:

![](/images/vanilla_gd_input.png)

Let's perform 100 iterations and see values of loss function and parameters at every 10th iteration.:

```
Iteration 0:  Loss=158.2773, m=1.4396, c=0.2184
Iteration 10: Loss=4.2799,  m=2.0871, c=0.3446
Iteration 20: Loss=4.2722,  m=2.0830, c=0.3719
Iteration 30: Loss=4.2653,  m=2.0791, c=0.3978
Iteration 40: Loss=4.2590,  m=2.0754, c=0.4225
Iteration 50: Loss=4.2533,  m=2.0719, c=0.4460
Iteration 60: Loss=4.2482,  m=2.0686, c=0.4683
Iteration 70: Loss=4.2436,  m=2.0654, c=0.4895
Iteration 80: Loss=4.2394,  m=2.0624, c=0.5096
Iteration 90: Loss=4.2356,  m=2.0595, c=0.5288
```

we can see the final values of parameters and loss function below:

![](/images/vanilla_gd_output.png)


full python code -:
[github](https://github.com/amruth6002/Optimizers/blob/main/vanilla.ipynb)



