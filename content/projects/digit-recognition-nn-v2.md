---
title: "MNIST Digit Recognition — V2"
description: "From-scratch Java MLP (256 → 128, ReLU + Softmax) trained with mini-batch SGD and cross-entropy loss on MNIST, with no external ML libraries. Paired with a responsive web playground for live in-browser sketching, real-time inference, and top-5 prediction visualization."
tech_stack:
  - "Java"
  - "JavaScript"
  - "HTML"
  - "CSS"
live_url: "https://luisapr1.github.io/Digit-Recognition-NN-V2/"
live_label: "Try the live demo"
group: "Data Engineering & Machine Learning"
weight: 50
---

<div class="mt-8">

The end-to-end pipeline is **live online** — sketch a digit, watch the network classify it: <a href="https://luisapr1.github.io/Digit-Recognition-NN-V2/" target="_blank">luisapr1.github.io/Digit-Recognition-NN-V2</a>.

## Network architecture

```
Input  : 784 neurons (flattened 28×28)
Hidden : 256 neurons, ReLU
Hidden : 128 neurons, ReLU
Output : 10 logits + Softmax
```

- **Loss**: Cross-Entropy (with combined Softmax + Cross-Entropy gradient `softmax − target`)
- **Optimizer**: Mini-batch SGD, batch size 64, learning rate 0.1
- **Early stopping**: training halts when average loss drops below 0.05 or rises for 10 epochs

## What I built

### Pure-Java training backend

No PyTorch, no TensorFlow, no NumPy — just `double[][]`. I implemented:

- **`MnistLoader`**: streams the IDX binary files and normalizes each pixel with the standard MNIST stats (`mean=0.1307`, `std=0.3081`), matching PyTorch byte-for-byte.
- **Forward / backward propagation** for a fully-connected network with ReLU hidden layers and a Softmax output, including the analytic derivative of ReLU.
- **Mini-batch SGD** with gradient accumulation across the batch and a single weight update afterwards.
- **Loss logging** to disk so I can plot training curves outside the JVM.

### Responsive web playground

A clean HTML/CSS/JS frontend that mirrors the Java preprocessing pipeline pixel-perfectly:

- 400×400 sketch canvas, downscaled and centered to 28×28 using the bounding box.
- Same standardization the trainer used (`(value/255 − 0.1307) / 0.3081`).
- The browser loads the Java-trained `pesos.csv` weights, recreates the same architecture in JavaScript, and runs Softmax inference directly in the browser.
- Live preview of the actual 28×28 input the network sees, plus top-5 predictions with confidence bars.

### Why this approach

Building a neural network from scratch — instead of calling `model.fit()` — forces you to actually understand the math. Every class in the code corresponds to a concept on paper: `Layer`, `Neuron`, `ActivationType`, the analytic derivative of ReLU, the combined Softmax + Cross-Entropy gradient. Re-implementing the exact same preprocessing pipeline in JavaScript so the browser can run inference on the Java-trained weights was a satisfying systems-level constraint to satisfy.

</div>
