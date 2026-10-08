# CS5720 Neural Network and Deep Learning — Home Assignment 2

**University of Central Missouri | Department of Computer Science & Cybersecurity**  
**Term:** Fall 2026  
**Student Name:** Supriya Shree Basnyat  
**Student ID:** 700788000  

---

## Assignment Overview

This assignment focuses on understanding and implementing fundamental concepts of **Convolutional Neural Networks (CNNs)** and **Transfer Learning** using Python, NumPy, and TensorFlow/Keras.

The assignment consists of two main tasks:

### 1. Implementing Convolution from Scratch
The first task involves implementing a 2D convolution operation manually using NumPy without relying on built-in convolution functions. It demonstrates how a convolutional filter moves across an input matrix, performs element-wise multiplication, and generates an output feature map. It also explores how changing the stride affects the output dimensions and the amount of information captured.

### 2. Transfer Learning: Freezing vs. Fine-Tuning
The second task explores transfer learning using a pretrained VGG16 model on the CIFAR-10 image classification dataset. Two approaches are compared:

- **Feature Extraction:** Freezing the pretrained convolutional layers and training only a newly added classification head.
- **Fine-Tuning:** Unfreezing the final convolutional block and updating its weights along with the classifier.

Both approaches are evaluated based on trainable parameters, training time, classification accuracy, and training loss.

### Learning Objectives
- Understand how 2D convolution works internally.
- Implement convolution manually using NumPy.
- Explore the effects of stride on feature map dimensions.
- Understand the concepts of transfer learning and pretrained CNNs.
- Differentiate between freezing layers and fine-tuning layers.
- Compare model performance, computational cost, and training efficiency.

**Overall, this assignment provides practical experience with CNN operations and demonstrates how pretrained deep learning models can be adapted efficiently to new image classification tasks.**