# Neural Network Hyperparameter Optimization on Fashion-MNIST

A PyTorch project exploring neural network hyperparameter optimization using Optuna on the Fashion-MNIST dataset.

Two versions of the experiment are included.

## V1: Architecture Optimization

V1 focuses on optimizing the basic architecture of the neural network.

### Hyperparameters

* Number of hidden layers: 1–5
* Neurons per hidden layer: 8–128

### Fixed Parameters

* Dropout: 0.3
* Learning rate: 0.01
* Epochs: 5
* Batch size: 32
* Optimizer: SGD
* Weight decay: 1e-4

### Purpose

V1 was used to study how the **depth and size of the neural network** affect its performance.

---

## V2: Extended Hyperparameter Optimization

V2 extends V1 by optimizing not only the network architecture, but also the **training and regularization parameters**.

### Hyperparameters

* Number of hidden layers: 1–5
* Neurons per hidden layer: 8–128
* Dropout rate: 0.1–0.5
* Learning rate: 1e-5–1e-1
* Epochs: 10–50
* Batch size: 16, 32, 64, 128
* Optimizer: Adam, SGD, RMSprop
* Weight decay: 1e-5–1e-3

### Changes from V1

**Dropout rate**

V1 uses a fixed dropout of 0.3. V2 allows Optuna to search for a suitable dropout rate to control overfitting.

**Learning rate**

V1 uses a fixed learning rate of 0.01. V2 searches across a wider range because the learning rate affects how quickly and effectively the model converges.

**Epochs**

V1 trains for 5 epochs. V2 allows different training durations from 10 to 50 epochs.

**Batch size**

V1 uses a fixed batch size of 32. V2 tests multiple batch sizes to study their effect on training.

**Optimizer**

V1 uses only SGD. V2 compares Adam, SGD, and RMSprop.

**Weight decay**

V1 uses a fixed value of 1e-4. V2 optimizes the weight decay to find a suitable level of L2 regularization.

---

## V1 vs V2

| Parameter         | V1          | V2                   |
| ----------------- | ----------- | -------------------- |
| Hidden layers     | Optimized   | Optimized            |
| Neurons per layer | Optimized   | Optimized            |
| Dropout           | Fixed: 0.3  | Optimized: 0.1–0.5   |
| Learning rate     | Fixed: 0.01 | Optimized: 1e-5–1e-1 |
| Epochs            | Fixed: 5    | Optimized: 10–50     |
| Batch size        | Fixed: 32   | Optimized: 16–128    |
| Optimizer         | SGD         | Adam / SGD / RMSprop |
| Weight decay      | Fixed: 1e-4 | Optimized: 1e-5–1e-3 |

## Summary

V1 explores **architecture optimization**.

V2 expands the search to include:

* Architecture
* Learning rate
* Training duration
* Batch size
* Optimizer
* Dropout
* Weight decay

The purpose of V2 is to evaluate a wider range of factors that can affect neural network performance rather than changing only the network architecture.
