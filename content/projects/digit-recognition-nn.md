---
title: "MNIST Digit Recognition — V1"
description: "Earlier educational feedforward neural network in pure Java (sigmoid activations + backpropagation) with MSE convergence checking and CSV weight serialization. Built without any external ML library, focused on the core mechanics of training and inference."
tech_stack:
  - "Java"
live_url: "https://github.com/LuisAPR1/Digit-Recognition-NN"
live_label: "View on GitHub"
group: "Data Engineering & Machine Learning"
weight: 60
---

<div>

The first iteration of my from-scratch neural network work, built for the **Artificial Intelligence** course. No external libraries — just `double[][]` and the chain rule.

## What's inside

- **`Neuron`**: weights, bias, sigmoid activation, and its derivative; handles forward propagation locally.
- **`Layer`**: a collection of neurons; manages forward propagation for the entire layer; initializes weights randomly.
- **`NeuralNetwork`**: orchestrates training and testing, implements **backpropagation**, computes MSE, and saves/loads trained weights to/from CSV.
- **`Main`**: entry point with three execution modes — full training, test-with-saved-weights, and an interactive console mode.

## Training process

1. **Forward pass**: compute the network output for each sample.
2. **Error**: difference between predicted and expected.
3. **Backward pass**: compute gradients via backpropagation through each layer.
4. **Update**: adjust weights and biases via gradient descent.
5. **Convergence check**: monitor MSE across epochs; stop when below threshold or when MSE starts climbing.

## Defaults

| Parameter | Value |
|---|---|
| Learning rate | 0.1 |
| MSE threshold | 0.0001 |
| Architecture | 1 hidden layer |
| Training data | Lines 1–280 of `dataset.csv` |
| Test data | Lines 1–800 of `dataset.csv` |

## Output artifacts

| File | Contents |
|---|---|
| `pesos.csv` | Saved weights after training |
| `mse_values.txt` | MSE per epoch — useful for plotting the learning curve |

## How it relates to the V2 work

This V1 network laid the groundwork for the much more substantial [MNIST Digit Recognition NN V2](/projects/digit-recognition-nn-v2/), replacing sigmoid with ReLU, adding a softmax output layer with cross-entropy loss, switching to mini-batch SGD, and shipping a live web playground that runs the trained weights directly in the browser.

</div>
