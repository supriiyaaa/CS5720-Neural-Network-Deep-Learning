# CS5720 Neural Network and Deep Learning — Home Assignment 1

**University of Central Missouri | Department of Computer Science & Cybersecurity**  
**Term:** Fall 2026  
**Student Name:** Supriya Shree Basnyat  
**Student ID:** 700788000  

---

## 📌 Submission Overview
* **Repository:** Source code & documentation pushed to GitHub.
* **Demonstration Video:** 2 to 3 minutes video submitted on Brightspace showcasing the code execution, loss/optimizer plots, and TensorBoard dashboard.
* **Log Directory:** TensorBoard logs stored in `logs/fit/`.

---

## ⚙️ Environment & Setup Instructions

### Prerequisites
* Python 3.10 or higher
* `pip` package manager

### Required Packages
Install all required dependencies using `pip`:
```bash
pip install tensorflow numpy matplotlib
```

### Running the Code
Execute the main script to run all tasks (Tensor manipulations, Loss comparisons, Optimizer benchmarks, and TensorBoard logging):
```bash
python main.py
```

### Launching TensorBoard
To visualize loss/accuracy curves and weight histograms:
```bash
tensorboard --logdir=logs/fit
```
Once started, open your web browser and navigate to `http://localhost:6006`.

---

## 📝 Part I. Short Answer Questions

### Question 1
* **a. Difference between traditional programming and machine learning:**  
  Writing step-by-step algorithms and hardcoded logic that converts input to particular outputs is the foundation of traditional programming. Conversely, machine learning employs data to find underlying mathematical representations and relationships; in other words, it trains a model to provide output for new data sets based on its training.
* **b. Relationship among AI, Machine Learning, and Deep Learning:**  
  Artificial Intelligence is a field of Computer Science that simulates human intelligence in recognizing, understanding, and solving problems. Machine learning is a subset of AI that uses data and mathematical formulas to establish a model that trains on data to understand patterns for future predictions. Deep Learning is a subset of machine learning that tries to understand patterns by using multiple layers called neural networks to learn complex patterns from large amounts of data.
* **c. Two reasons deep learning has become successful recently:**  
  1. The exponential increase of enormous digital datasets required to train deep neural networks.  
  2. The tremendous parallel computing capacity provided by modern specialized hardware like GPUs and TPUs.

---

### Question 2
* **a. Roles of layers in a neural network:**  
  * **Input layer:** Receives raw input data.  
  * **Hidden layer:** Performs mathematical transformations on input data.  
  * **Output layer:** Provides the final prediction/output.
* **b. Weights and biases:**  
  Weights and biases are learned parameters that control how an artificial neuron interprets input data. Weight determines the strength/importance of each input feature, while bias acts as a threshold/offset that shifts the activation function to allow the neuron to output signals even when inputs are zero.
* **c. Necessity of activation functions:**  
  Activation functions introduce non-linearity into the network. Without non-linearity, even a multi-layered neural network would behave like a simple single-layer linear model, failing to learn complex patterns.

---

### Question 3
* **a. Perceptron and binary output:**  
  A perceptron is the foundational building block of a neural network. It takes a weighted sum of inputs plus a bias and maps this sum to a binary output (0 or 1) using a step/threshold function.
* **b. Why a perceptron can solve AND and OR problems:**  
  AND and OR gates are linearly separable—their outputs can be cleanly divided by a single linear decision boundary (straight line).
* **c. Why XOR cannot be solved by a single perceptron & how multi-layer networks fix it:**  
  The XOR function is non-linearly separable because its positive and negative targets lie diagonally across from each other. A multi-layer neural network uses hidden layers to transform the feature space, creating non-linear decision boundaries.

---

### Question 4
* **a. Comparison of Sigmoid, Tanh, and ReLU:**  
  * **Sigmoid:** Maps inputs to a $(0, 1)$ range; useful for probabilities.  
  * **Tanh:** Zero-centered S-shaped curve mapping inputs to $(-1, 1)$.  
  * **ReLU:** Returns $0$ for negative inputs and passes positive inputs unchanged, spanning $[0, \infty)$.
* **b. Vanishing gradient problem & ReLU's advantage:**  
  The vanishing gradient problem occurs when gradients grow extremely small as they flow backward through deep layers during backpropagation, stopping earlier layers from learning. For positive inputs, ReLU has a constant gradient of $1$, which prevents gradient saturation and mitigates this problem.
* **c. Neural Network Training Cycle:**  
  * **Forward Propagation:** Inputs flow through layers to compute predictions.  
  * **Error/Loss Calculation:** Compares predictions against ground-truth labels using a loss function.  
  * **Backpropagation:** Computes gradients of the loss with respect to each weight going backward.  
  * **Weight Update:** Optimizer adjusts weights and biases to minimize error.

---

## 💻 Part II. Programming Tasks & Implementation

### Task 1: Tensor Manipulations & Reshaping
* Created a random tensor of shape `(4, 6)`.
* Verified rank ($2$) and shape (`[4, 6]`).
* Reshaped into `(2, 3, 4)` and transposed dimensions to `(3, 2, 4)`.
* Applied TensorFlow **broadcasting** to perform element-wise addition between `(3, 2, 4)` and `(1, 4)` tensors seamlessly without memory duplication.

---

### Task 2: Loss Functions & Hyperparameter Tuning
* Implemented Mean Squared Error (MSE) and Categorical Cross-Entropy (CCE) loss evaluations.
* Evaluated loss sensitivity across small prediction shifts and generated a comparative bar chart (`loss_comparison.png`).

---

### Task 3: Optimizers Benchmarking (Adam vs. SGD)
* Trained two identical neural network architectures on the MNIST dataset for 5 epochs—one using **Adam** and the other using **SGD**.
* Generated validation vs. training accuracy comparison curves (`optimizer_comparison.png`). Adam converges significantly faster due to adaptive learning rates.

---

### Task 4: Neural Network Training & TensorBoard Analysis
* Configured `tf.keras.callbacks.TensorBoard` with `log_dir="logs/fit/..."`.
* Logs recorded scalar losses, accuracies, and weight distribution histograms over 5 training epochs.

#### 4.1 TensorBoard Analysis Questions:
1. **What patterns do you observe in the training and validation accuracy curves?**  
   * Both training and validation accuracy curves climb rapidly in early epochs and slow down as the model converges.
2. **How can you use TensorBoard to detect overfitting?**  
   * While training loss keeps decreasing, validation loss begins to increase. Over time, the difference between training and validation accuracy gets larger.
3. **What happens when you increase the number of epochs?**  
   * When the model reaches its learning capability, performance reaches a halt. Extended training results in overfitting, which deteriorates validation loss.
