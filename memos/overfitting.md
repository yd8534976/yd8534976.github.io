# Dropout: an efficient way to combine neural nets

## - Two ways to average models

 1. mixture: combine models by averaging their output probabilities

    (Model A + Model B) / 2

 2. product: combine models by taking the geometric means of thier output probabilities

    sqrt(Model A * Model B) / sum

## - An efficient way to average many large neural nets

 1. Consider a neural net with one hidden layer

 2. Each time we present a training example,we randomly omit each hidden unit with probability 0.5

 3. So we are randomly sampling from 2^H different architectures

    - All architectures share weights

## - Dropout as a form of model averaging
