Training NNs: Best practices
- Back propagation is the NN's weight update algorithm

Failure cases:
1) Vanishing gradients
    - gradients for the lower layers (closer to input) can become very small
    - in deep NNs, computing can involve taking the product of many small terms
    - when gradients vanish toward 0, these layers train very slowly or not at all
    - Preventions:
        *ReLU activation function
2) Exploding gradients
    - if the weights in the network are very large, the gradients involve products of many large terms
    - these gradients may get too large to converge
    - Prevention:
        * batch normalization
        * lower learning rate
3) Dead ReLU units
    - if the weighted sum for a ReLU unit falls below 0, the unit can get stuck
    - outputs 0 activation
    - contributes nothing to the network
    - gradients can no longer flow through during backpropagation
    - weighted sum may no tever change enough to get back above 0
    - Preventions:
        * lower learning rate

Dropout regularization
    - randomly drop unit activations in a network for a single gradient step
    - the more drops the stronger the regularization
    
    0 = no dropout regularization
    1 = drop everything (model learns nothing)
    values between 0 and 1 = more useful
        
