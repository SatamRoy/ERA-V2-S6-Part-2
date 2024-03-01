# ERA-V2-S6-Part-2
# ERA-V2-S6 - CNN Model Explanation

The architecture of the neural network (NN) model is as follows:

1. **Convolutional Layers**:
    - Convolutional layers (`Conv2d`) are used for feature extraction in image data.
    - The first convolutional layer (`conv1`) takes a single-channel input (such as grayscale images) and produces **32 output channels**.
    - The second convolutional layer (`conv2`) also has **32 output channels**.
    - The third convolutional layer (`conv3`) produces **20 output channels**.

2. **Activation Function**:
    - After each convolutional layer, the **ReLU activation function** is applied. It introduces non-linearity to the model.

3. **Normalization**:
    - **Batch normalization** (`BatchNorm2d`) stabilizes training by normalizing the input to each layer.
    - It helps improve convergence and generalization.

4. **Pooling Layers**:
    - **Max pooling** (`MaxPool2d`) reduces the spatial dimensions of the feature maps.
    - It selects the maximum value from a local region (e.g., 2x2) and downsamples the feature map.

5. **Dropout**:
    - **Dropout** (`dropout1`) randomly sets a fraction of input units to zero during training.
    - It prevents overfitting by encouraging the network to learn robust features.

6. **Global Average Pooling**:
    - The `global_avg_pool` operation computes the average value of each feature map.
    - It reduces the spatial dimensions to a single value per channel.

7. **Final Output**:
    - The last convolutional layer (`conv4`) produces **10 output channels**.
    - The output is reshaped (`x.view(-1, 10)`) to match the desired output size.
    - Finally, the `log_softmax` function is applied to obtain the log probabilities of different classes.

