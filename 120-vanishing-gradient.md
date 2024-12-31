**vanishing gradient** vanishing gradient problem in deep learning occurs when the gradients used to update the weights of a neural network during backpropagation become extremely small. 
This makes it difficult for the network to learn, as the weights of the earlier layers receive minimal updates
- reduce model complexity
- Use ReLU
- Xavier/Glorot initialization: Initializes weights in a way that preserves variance during forward and backward propagation.
- Batch Normalization
- Limits the magnitude of gradients during backpropagation to prevent them from exploding
- Residual Connections (Skip Connections): Create shortcuts that allow gradients to flow directly through multiple layers, bypassing potential vanishing gradients
