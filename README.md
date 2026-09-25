# Algorithms-for-Intelligent-Systems-and-Robotics-
A collection of Algorithms for Intelligent Systems &amp; Robotics lab experiments, featuring Python implementations of AI search, optimization, path planning, filtering, and robotics algorithms.

The main purpose of maintaining this repository is to keep my lab implementations organized and to understand how these algorithms work practically using Python.

---

## 📌 Experiments Included

### 1. Hill Climbing Search

**Aim:**  
To implement the Hill Climbing Search algorithm and understand its use in optimization problems.

**What I implemented:**
- Basic Hill Climbing algorithm
- State-space exploration
- Evaluation of neighbouring states
- Selection of better states
- Search for an optimal solution

**About the Experiment:**  
Hill Climbing is a local search algorithm that starts from an initial solution and continuously moves towards a better neighbouring solution. The process continues until no better neighbouring state can be found.

This experiment helped me understand how heuristic information can be used to improve a solution without exploring the complete search space.

**Concepts Used:**  
`Heuristic Search` `Local Search` `Optimization` `State Space`

---

### 2. Breadth-First Search (BFS) and Depth-First Search (DFS)

**Aim:**  
To implement and understand the working of Breadth-First Search and Depth-First Search algorithms.

**What I implemented:**
- Graph representation
- Breadth-First Search
- Depth-First Search
- Node traversal
- Tracking visited nodes
- Comparison of BFS and DFS traversal

### Breadth-First Search

BFS explores the graph level by level. It first visits all the neighbouring nodes before moving to the next level.

A **queue** is used to maintain the order in which nodes are explored.

### Depth-First Search

DFS explores one path as deeply as possible before returning and exploring another path.

It can be implemented using a **stack or recursion**.

This experiment helped me understand how the choice of a searching strategy changes the order in which a graph is explored.

**Concepts Used:**  
`Graph Search` `BFS` `DFS` `Queue` `Stack` `Graph Traversal`

---

### 3. Reinforcement Learning

**Aim:**  
To understand the basic working of Reinforcement Learning and how an agent learns through interaction with an environment.

**About the Experiment:**  
In Reinforcement Learning, an agent interacts with an environment by performing different actions.

After performing an action, the agent receives a reward or penalty. Based on this feedback, it gradually learns which actions are more useful for achieving its goal.

The basic interaction can be represented as:

```text
Current State
     ↓
   Agent
     ↓
   Action
     ↓
 Environment
     ↓
   Reward
     ↓
Learning / Updated Decision
```

This experiment helped me understand the basic relationship between an agent, environment, state, action and reward.

**Concepts Used:**  
`Agent` `Environment` `State` `Action` `Reward` `Policy` `Exploration` `Exploitation`

---

## Experiment 6: Simple Neural Network Concept using Python

**Aim:**  
To implement a simple Artificial Neural Network from scratch using Python and NumPy and understand how a neural network learns nonlinear relationships.

### What I implemented

- Sigmoid activation function
- ReLU activation function
- Activation function derivatives
- Single neuron implementation
- AND, OR and XOR logic gates
- Neural network with a hidden layer
- Forward propagation
- Backpropagation
- Gradient descent
- XOR classification
- Dying ReLU analysis
- Effect of hidden-layer width
- Spiral dataset classification
- Comparison with Scikit-learn MLPClassifier

### About the Experiment

I first implemented a single neuron and tested it on AND, OR and XOR logic gates.

The single neuron was able to learn AND and OR correctly, but it could not solve XOR because XOR is not linearly separable.

A hidden layer with ReLU activation was then added to the network. With the hidden layer, the network was able to learn nonlinear decision boundaries and successfully solve XOR.

The basic network structure used was:

```text
Input Layer
     ↓
Hidden Layer
   (ReLU)
     ↓
Output Layer
  (Sigmoid)
     ↓
Prediction
```

### Dying ReLU

I also studied the **dying ReLU problem**.

For negative inputs, the output and derivative of ReLU become zero. If a neuron remains in this region for all training samples, it stops receiving useful gradient updates and can become inactive.

The experiment was repeated using different random initializations to observe how this affects training.

### Effect of Hidden Layer Width

Different numbers of hidden neurons were also tested.

The experiment showed that increasing the number of hidden neurons made the network more reliable because the network had enough remaining capacity even when some ReLU neurons became inactive.

### Spiral Dataset

The neural network was further tested on a spiral dataset to study a more difficult nonlinear classification problem.

A single neuron performed poorly because it could only create a linear decision boundary. The network with a ReLU hidden layer was able to create a much more complex decision boundary and classify the spiral data successfully.

Finally, the implementation was compared with Scikit-learn's `MLPClassifier`.

**Concepts Used:**  
`Artificial Neural Network` `ReLU` `Sigmoid` `Forward Propagation` `Backpropagation` `Gradient Descent` `XOR` `Dying ReLU` `MLP`

---

## Experiment 7: Comparison of Learning Strategies for an MLP Classifier

**Aim:**  
To compare different learning strategies used for training a Multi-Layer Perceptron classifier.

### Dataset Used

The **Wine Dataset** available in Scikit-learn was used for this experiment.

The dataset contains:
- 178 samples
- 13 input features
- 3 target classes

The data was divided into training and testing sets and feature scaling was performed using `StandardScaler`.

### Learning Strategies Compared

I compared the effect of several MLP parameters, including:

#### 1. Solver
Different optimization algorithms were tested:

- Adam
- SGD
- SGD with Momentum
- SGD with Nesterov Momentum
- SGD with Inverse Scaling
- SGD with Adaptive Learning Rate
- L-BFGS

#### 2. Learning Rate

Different learning rates were tested to observe how the step size affects the training process.

A very small learning rate resulted in slow learning, while larger learning rates allowed the model to converge faster.

#### 3. Activation Function

The following activation functions were compared:

- ReLU
- Tanh
- Logistic
- Identity

#### 4. Network Architecture

Different hidden-layer structures were tested to understand the effect of network size and depth.

Examples included:

```text
(5,)
(10,)
(20,)
(20, 20)
(40, 20, 10)
```

#### 5. Batch Size

Different batch sizes were tested to study their effect on training time and model performance.

#### 6. Regularization

Different values of the `alpha` parameter were tested to study L2 regularization and its effect on overfitting.

### Model Evaluation

The models were compared using:

- Training Accuracy
- Testing Accuracy
- Number of Iterations
- Training Time
- Loss Curves
- Confusion Matrix
- Precision
- Recall
- F1-Score

### Cross-Validation

Since the Wine Dataset is relatively small, a single train-test split can give misleading results.

Therefore, **5-fold cross-validation** was also performed to obtain a more reliable comparison between different learning strategies.

This was an important observation from this experiment because a model that performed very well on one train-test split did not necessarily have the same relative performance during cross-validation.

**Concepts Used:**  
`MLPClassifier` `Adam` `SGD` `L-BFGS` `Learning Rate` `Momentum` `Activation Functions` `Regularization` `Cross-Validation`

---

## Experiment 8: Kalman Filtering using Python

**Aim:**  
To implement the Kalman Filter in Python and understand how it can be used to estimate the state of a system when sensor measurements contain noise.

### About the Experiment

The Kalman Filter combines information from:

1. A mathematical model of the system
2. Noisy sensor measurements

to produce an improved estimate of the actual state.

The basic Kalman Filter cycle can be represented as:

```text
Previous State
      ↓
  Prediction
      ↓
Predicted State
      ↓
Measurement → Update
      ↓
Corrected State
      ↓
Next Prediction
```

Two main applications were studied in this experiment.

### Part 1: Temperature Sensor

A noisy temperature sensor was simulated.

The temperature initially remains constant, then increases after a heater is switched on.

A one-dimensional Kalman Filter was implemented to estimate the actual temperature from the noisy sensor measurements.

Different values of **process noise Q** were tested.

This demonstrated an important trade-off:

```text
Small Q → Smoother estimate but slower response

Large Q → Faster response but more sensitivity to noise
```

The performance was measured using **Root Mean Square Error (RMSE)**.

---

### Part 2: Robot Motion Tracking

The second part implements the matrix form of the Kalman Filter for tracking a robot moving along a square path.

The state of the robot contains:

```text
[x position, x velocity, y position, y velocity]
```

The sensor provides noisy position measurements while the Kalman Filter estimates both the position and velocity of the robot.

The robot follows straight paths and makes sudden turns at the corners.

This was useful for observing what happens when the motion model does not perfectly match the real motion of the robot.

Different process-noise values were tested to compare:

- Overall tracking error
- Error near corners
- Error on straight paths
- Responsiveness of the filter

---

### Sensor Failure

The experiment also studies a temporary sensor failure.

During this period, the Kalman Filter does not receive new measurements and has to depend only on its prediction model.

When the robot changes direction during the sensor blackout, the prediction error increases because the filter does not know that the robot has turned.

Once sensor measurements become available again, the filter gradually corrects its state estimate.

This part helped demonstrate both the usefulness and limitations of prediction-based state estimation in robotics.

**Concepts Used:**  
`Kalman Filter` `State Estimation` `Prediction` `Update` `Kalman Gain` `Covariance` `Process Noise` `Measurement Noise` `RMSE` `Robot Tracking`

---

# Technologies and Libraries Used

The experiments were mainly implemented using:

- **Python**
- **NumPy**
- **Matplotlib**
- **Scikit-learn**
- **Jupyter Notebook / Google Colab**

---

# Installation

To run the experiments locally, Python should be installed along with the required libraries.

```bash
pip install numpy matplotlib scikit-learn pandas
```

The notebooks can then be opened using Jupyter Notebook, JupyterLab or any other environment that supports `.ipynb` files.

---

# What I Learned

Through these experiments, I was able to understand both basic and advanced concepts used in intelligent systems and robotics.

Some of the major concepts I worked with include:

- Searching and graph traversal using BFS and DFS
- Heuristic optimization using Hill Climbing
- Basic Reinforcement Learning concepts
- Building a neural network from scratch
- Forward propagation and backpropagation
- ReLU and the dying ReLU problem
- Training and evaluating MLP classifiers
- Effect of learning rate, solver and network architecture
- Model evaluation using cross-validation
- State estimation using Kalman Filtering
- Handling noisy sensor measurements
- Tracking robot position and velocity

These experiments helped me connect the theoretical concepts of Artificial Intelligence and Robotics with their practical Python implementations.

---

# Repository Purpose

This repository is maintained as part of my **Algorithms for Intelligent Systems and Robotics Lab** coursework.

It contains my implementations and observations from the lab experiments and serves as a record of the concepts and algorithms studied during the course.

---

## Author

**Sakshi Bhatt**  
B.Tech  
UPES