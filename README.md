# Numerical-Optimization

## 1- Gradient Descent:
is a first-order iterative optimization algorithm for finding a local minimum of a differentiable function, It's based on a convex function.
The idea is to take repeated steps in the opposite direction of the gradient of the function at the current point, because this is the direction of steepest descent.
### GD Applied to LR (Single Variable):
step1:Intialize parameters (theta_1& theta_2) with randum parameters or simply zeros, and also choose the learning rate 
step2: use theta_1 &theta_@ to predict the output (h(x))
step3: Calculate the cost funcation (j)
step4:Calculate the Gradient 
step5:upsate the parameters 
step6: Repeat from 2 to 5 until converge to the minimum or achieve maximum iterations

## Batch GD:
Standard Gradient descent updates the parameters only after each epoch i.e., after calculating the derivatives for all the observations it updates the parameters.
This phenomenon may lead to the following problems:
It can be very slow for very large datasets because only one-time update for each epoch. Large number of epochs is required to have a substantial number of updates.
#### Different variants of GD can address these challenges
## Stochastic GD(SGD):
Update the parameters for each observation
### However, minibatch is the optimum between Batch and SGD.
## MiniBatch:
instead of going overall examples, mini batch GD sums up over lower number of examples based on the batch size.

### There are two frequent problems in Deep Learning: exploding gradient and vanishing gradient.

## 2-Momentum-based GD
Consider a case where in order to reach to your desired destination you are continuously being asked to follow the same direction and once you become confident that you are following the right direction then you start taking bigger steps and you keep getting momentum in that same direction.

Similar to this if the gradient is in a flat surface for long term, then rather than taking constant steps it should take bigger steps and keep
the momentum continue. This approach is known as momentum based gradient descent.

### Issues with momentum based Gradient descent:
Momentum based GD oscillates in and out of the minima valley i.e., making U-turns near the minima (however it converges faster vanilla GD).

## 3- To overcome this issue Nesterov accelerated GD (NAG) is used.
first make a big jump in the direction of the previous accumulated gradient; (looking ahead step)
then measure the gradient where you end up and make a correction. 
It is always better to correct a mistake right after you have made it.

## 4-Adagrad: 
Adagrad adopts the learning rate(η) based on the sparsity of features. So, the parameters with small updates (sparse features) have high learning rate whereas parameters with large updates (dense features) have low learning rate.

### adagrad makes the learning rate decay very aggressively as the denominator grows (not good for parameter corresponding to dense feature).
### Hence there is no update in value of parameter. solve this by using RMS.

## 5-RMS:
Instead of accumulating squared gradients from the beginning, it accumulates the previous gradients in some portion(weight).

## 6- ADAM:
Adaptive Moment Estimation (Adam) computes the exponentially decaying average of previous gradients m(t) along with an adaptive learning rate.
Adam is a combined form of Momentum-based GD and RMSProp.
In Momentum-based GD, previous gradients (history) are used to compute the current gradient whereas, in RMSProp previous gradients (history) are used to
adjust the learning rate based on the features.
Adam deals with adaptive learning rate and adaptive momentum

# Second Order Optimization:
## Newton’s Method:
Unlike gradient descent, which ensures that we’re always going downhill by always going in the direction opposite the gradient, Newton’s method fits a paraboloid to the local curvature and proceeds to move to the stationary point of that paraboloid.
