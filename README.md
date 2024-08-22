# DigitRecognizerANN
IMPLEMENTATION OF HANDWRITTEN DIGITS USING FULLY CONNECTED ANN
---

# Detecting Handwritten Digits Using a Fully Connected Artificial Neural Network in FPGA

![Neuron Block Diagram](./Proposed_Architecture_of_neuron.png)
 <!-- Add a relevant image or illustration -->

## Overview

This project implements a **5-layer fully connected Artificial Neural Network (ANN)** on an FPGA to recognize handwritten digits from the MNIST dataset. The goal is to leverage the advantages of FPGAs, such as low power consumption and minimal latency, making them a viable alternative to GPUs for AI/ML applications.

### Key Features

- **Accuracy:** Achieved 98% accuracy using a fully connected ANN.
- **Efficiency:** Lower power consumption and memory usage compared to traditional GPUs.
- **Scalability:** Flexible architecture capable of adapting to various input sizes and datasets.
- **Hardware Utilized:** Vivado 2022.1 and Zynq 7000 board.

## Table of Contents

1. [Introduction](#introduction)
2. [Project Architecture](#project-architecture)
3. [Methodology](#methodology)
4. [Results and Comparison](#results-and-comparison)
5. [Conclusion](#conclusion)
6. [References](#references)

## Introduction

Artificial Neural Networks (ANNs) are proving to be a powerful tool in AI/ML, particularly when implemented in FPGAs. This project explores the feasibility of replacing GPUs with FPGAs for digit recognition tasks. The FPGA implementation demonstrates superior memory and power efficiency while maintaining high accuracy, making it ideal for low-latency applications.

## Project Architecture

The project implements a fully connected, feed-forward ANN with 5 layers:
- **Input Layer:** 784 inputs (28x28 pixels)
- **Hidden Layers:** Three hidden layers with 30, 30, and 10 neurons respectively.
- **Output Layer:** 10 neurons corresponding to the digits 0-9.

### Block Diagram of the Neuron

![Neuron Block Diagram](./neuron.pdf) <!-- Add neuron block diagram image -->

The basic operation of a neuron involves a weighted sum of inputs followed by an activation function. This project implements both Sigmoid and ReLU as activation functions.

## Methodology

### Neuron Implementation

Each neuron is implemented using Verilog, with weights and biases pre-trained in Python. The binary files for weights and biases are loaded into the FPGA during execution. The neuron processes inputs using fixed-point arithmetic, ensuring efficient hardware utilization.

### Activation Functions

- **Sigmoid:** Ideal for small-scale networks, providing smooth gradient transitions.
- **ReLU:** Provides faster convergence but may lead to dead neurons in some cases.

## Results and Comparison

### Performance Metrics

| Metric            | ReLU   | Sigmoid |
|-------------------|--------|---------|
| Flip-Flops        | 66     | 52      |
| LUTs              | 58     | 47      |
| Dynamic Power     | 93%    | 99%     |
| Accuracy          | 91%    | 98%     |

### Comparison with GPU Implementation

The ANN implemented on FPGA outperformed the TensorFlow-based GPU implementation in terms of accuracy, power consumption, and memory efficiency. The FPGA used significantly fewer resources while achieving higher accuracy.

## Conclusion

The FPGA-based ANN implementation for handwritten digit recognition not only meets but exceeds expectations in terms of accuracy and efficiency. This project demonstrates that FPGAs can be a viable alternative to GPUs for specific AI/ML tasks, especially in environments where power and latency are critical factors.

## References

1. Charles Rajesh Kumar J, et al. "VLSI design and implementation of High-performance Binary-weighted convolutional artificial neural networks for embedded vision-based IoT."
2. Daniel Jonasson, "Object Recognition Through Convolutional Learning For FPGA."
3. MD Shahbaz Khan, et al. "FPGA Simulation of Fingertip Digit Recognition Using CNN."

<!-- Add more references as needed -->

---

This `README.md` file provides a comprehensive and structured overview of your project, emphasizing its key features and the significance of FPGA-based implementations for AI/ML tasks. You can further enhance it by adding images, diagrams, or any other visuals that make your repository more engaging and informative.
