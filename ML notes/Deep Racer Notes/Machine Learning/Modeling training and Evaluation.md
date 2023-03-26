previous - [[The four aspects of Working with data]]
next - [[Model Evaluation]]


Iteratively update model parameters to minimise some loss function.

1. Splitting Dataset - test and train ( 20 - 80 is good ratio)
2. Set the hyper parameters
3. Train the model on train set - update the hyper parameters and re-train if necessary.
4. Compute the loss function on the results
5. Update the model parameters in a direction that reduces loss.
6. Test the model on test set


Various models 

- **Linear Models
- **Tree-based models ( XGBoost )
- **Deep learning models (FFNN , CNN , RNN/LSTM , Transformer )
	-   **FFNN**: The most straightforward way of structuring a neural network, the Feed Forward Neural Network (FFNN) structures neurons in a series of layers, with each neuron in a layer containing _weights_ to all neurons in the previous layer.
	-   **CNN**: Convolutional Neural Networks (CNN) represent nested filters over grid-organised data. They are by far the most commonly used type of model when processing images.
	-   **RNN/LSTM**: Recurrent Neural Networks (RNN) and the related Long Short-Term Memory (LSTM) model types are structured to effectively represent for loops in traditional computing, collecting state while iterating over some object. They can be used for processing sequences of data.
	-   **Transformer**: A more modern replacement for RNN/LSTMs, the transformer architecture enables training over larger datasets involving sequences of data.
