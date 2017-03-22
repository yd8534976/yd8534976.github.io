# Dropout: an efficient way to combine neural nets

## Two ways to average models

 1. mixture: combine models by averaging their output probabilities

    (Model A + Model B) / 2

 2. product: combine models by taking the geometric means of thier output probabilities

    sqrt(Model A * Model B) / sum

## An efficient way to average many large neural nets

 1. Consider a neural net with one hidden layer

 2. Each time we present a training example,we randomly omit each hidden unit with probability 0.5

 3. So we are randomly sampling from 2^H different architectures

    - All architectures share weights

## Dropout as a form of model averaging

 1. We sample from 2^H models. So only a few of the models ever get trained, and they only get one training example

    - This is as extreme as bagging can get

 2. The sharing of the weights means that every model is very strongly regularized

    - It's a much better regularizer than L2 or L1 penalties that pull the weights towards zero

## What do we do at test time?

 1. We could sample many different architectures and take the geometric mean of their output distributions.

 2. It's better to use all of the hidden units, but to halve their outgoing weights.
 	- This exactly computes the geometric mean of the predictions of all 2^H models.

## What if we have more hidden layers?

 1. Use dropout of 0.5 in every layer.

 2. At test time, use the "mean net" that has all the outgoing weights halved.

 3. Alternatively, run the stochastic model several times on the same input.

## What about the input layer?

 1. It helps to use dropout there too, but with a higher probability of keeping an input unit.

## How well does dropout work?

 1. The record breaking object recognition net developed by Alex Krizhevsky uses dropout and it helps a lot.

 2. If your deep neural net is significantly overfitting, dropout will usually reduce the number of errors by a lot.

 3. If your deep neural net is not overfitting you should be using a bigger one!

## Another way to think about dropout

 1. If a hidden unit knows which other hidden units are present, it can co-adapt to them on the training data.

 2. If a hidden unit has to work well with combinatorially many sets of co-workers, it is more likely to do something that is individually useful.


> Hinton


