Anatomy
- set of nodes (analogous to neurons) organized in layers
- set of weights representing the connections between layers
- set of biases for each node
- activation function transforming output of each node in a layer

Hidden layers

Activation functions
- piping hidden layer nodes through a non-linear function
- common functions:
    * sigomid F(x) = 1 / (1+e^-x)
    * rectified linear unit (ReLU) F(x) = max(0, x)
        - often works a littler better than a smooth function like sigmoid
        - easier to compute

Pros and cons
- neural networks aren't always better than feature crosses
- neural networks offer a flexible alternative that works well in many cases

