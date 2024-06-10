https://www.v7labs.com/blog/neural-networks-activation-functions#:~:text=An%20Activation%20Function%20decides%20whether,prediction%20using%20simpler%20mathematical%20operations.

Go through the article you will get to know about activations functions

WHy the activation functions are required ?

### Detailed Explanation and Notes on Non-linear Activation Functions in Neural Networks

#### Introduction to Activation Functions
Activation functions are a crucial part of neural networks. They determine whether a neuron should be activated or not by applying a transformation to the input received by the neuron. The activation function introduces non-linearity into the network, allowing it to learn complex patterns.

#### Linear Activation Function (Identity Function)
- **Definition**: A linear activation function is one where the output is directly proportional to the input. Mathematically, it can be expressed as \( g(z) = z \).
- **Properties**: It simply outputs the input value without any modification. Hence, it is also known as the identity activation function.

#### Why Non-linear Activation Functions are Needed
1. **Inability to Learn Complex Patterns**:
   - If a linear activation function is used throughout the network, the entire network acts as a linear model, regardless of the number of layers.
   - This means that the network is just computing a linear transformation of the input, which is insufficient for capturing complex patterns in the data.

2. **Mathematical Explanation**:
   - Consider a neural network with two layers where:
     - \( a^{(1)} = z^{(1)} = W^{(1)}x + b \)
     - \( a^{(2)} = z^{(2)} = W^{(2)}a^{(1)} + b \)
   - Substituting \( a^{(1)} \) in the equation for \( a^{(2)} \):
     \[
     a^{(2)} = W^{(2)}(W^{(1)}x + b) + b
     \]
   - Simplifying, we get:
     \[
     a^{(2)} = W' x + b'
     \]
     where \( W' = W^{(2)}W^{(1)} \) and \( b' = W^{(2)}b + b \).
   - This shows that the composition of linear functions is itself linear.

3. **Depth of the Network**:
   - In deep networks (networks with many layers), using linear activation functions means that no matter how deep the network is, the final output is still a linear function of the input.
   - Hence, having multiple layers becomes redundant if only linear activation functions are used.

#### Non-linear Activation Functions
To enable neural networks to learn and represent complex functions, non-linear activation functions are used. Common non-linear activation functions include:
- **ReLU (Rectified Linear Unit)**:
  \[
  \text{ReLU}(z) = \max(0, z)
  \]
  - Introduces non-linearity by setting negative values to zero.
- **Sigmoid Function**:
  \[
  \sigma(z) = \frac{1}{1 + e^{-z}}
  \]
  - Outputs values between 0 and 1, useful for binary classification.
- **Tanh (Hyperbolic Tangent)**:
  \[
  \tanh(z) = \frac{2}{1 + e^{-2z}} - 1
  \]
  - Outputs values between -1 and 1, providing zero-centered outputs.
- **Leaky ReLU**:
  \[
  \text{Leaky ReLU}(z) = \begin{cases} 
  z & \text{if } z > 0 \\
  \alpha z & \text{if } z \leq 0 
  \end{cases}
  \]
  - Allows a small, non-zero gradient when the unit is not active.

#### Special Cases for Linear Activation Functions
- **Output Layer in Regression Problems**:
  - In regression tasks where the target value \( y \) is a real number, it can be acceptable to use a linear activation function in the output layer.
  - For example, predicting housing prices can involve outputs that range from very low to very high values, where a linear output can be appropriate.

- **Using Non-negative Outputs**:
  - Even in regression problems, if the output is constrained to be non-negative (e.g., prices), using an activation function like ReLU in the output layer can ensure the predictions are non-negative.

#### Summary
- **Non-linear Activation Functions**: Essential for neural networks to learn and represent complex relationships in data.
- **Linear Activation Functions**: Appropriate in the output layer for certain types of regression problems but not suitable for hidden layers in general as they limit the model to learning only linear relationships.
- **Impact on Network Depth**: Without non-linear activation functions, adding more layers does not increase the complexity of the model's ability to represent data patterns.

This understanding is crucial as it forms the foundation for effectively designing and training neural networks to solve real-world problems by leveraging their capacity to learn non-linear representations.


Sure, let's break down the explanation into "what", "how", and "why" questions:

### What Questions:
1. **What is a linear activation function?**
   - A linear activation function outputs the input value directly without any modification. It's represented as \( g(z) = z \).

2. **What are non-linear activation functions?**
   - Non-linear activation functions introduce non-linearity into the network, allowing it to learn and represent complex patterns in data. Examples include ReLU, sigmoid, tanh, and Leaky ReLU.

3. **What is the purpose of activation functions in neural networks?**
   - Activation functions determine whether a neuron should be activated or not based on the input it receives. They introduce non-linearity, which enables the network to learn complex relationships in the data.

### How Questions:
1. **How do linear activation functions affect the network's behavior?**
   - Linear activation functions result in the network acting as a linear model regardless of the number of layers, limiting its capacity to learn complex patterns.

2. **How do non-linear activation functions address the limitations of linear functions?**
   - Non-linear activation functions allow the network to compute non-linear transformations of the input, enabling it to learn and represent complex functions.

3. **How do activation functions impact the gradient flow during backpropagation?**
   - Activation functions affect the gradients' flow through the network during backpropagation. Non-linear activation functions help mitigate issues like vanishing and exploding gradients by maintaining effective gradient flow.

### Why Questions:
1. **Why are non-linear activation functions necessary in neural networks?**
   - Non-linear activation functions are necessary because they enable neural networks to learn and represent complex relationships in data, which linear functions cannot capture.

2. **Why does using only linear activation functions make the network behave like a linear model?**
   - Using only linear activation functions results in the network computing linear transformations of the input, regardless of its depth. This limits the network's ability to learn complex patterns, making it behave like a linear model.

3. **Why is it essential to choose appropriate activation functions for different tasks?**
   - Choosing appropriate activation functions impacts the network's ability to learn and generalize from the data. Understanding the task requirements and the properties of activation functions helps in designing effective neural network architectures.
