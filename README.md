# Classifying the quality of a banana with a neural network

## Dataset
- Link to dataset: https://www.kaggle.com/datasets/l3llff/banana
- Our goal is to classify the quality of a banana (Good or Bad) based on its features.

## Steps to run
1. Navigate to the following Google Colab project, go to "Runtime", and "Run All". Wait for the run to finish to view the train and test error.
https://colab.research.google.com/drive/17gtdpw8Qczqz_EJEUFfQMUFcSEPG6Tdk?usp=sharing
2. To run locally, download "banana_quality_neural_network.ipynb" along with "banana_quality.csv" and place them in the same directory. Install the necessary packages (pandas, numpy, sklearn) and run the code. The parameters can be tuned in the line that initalizes the `NeuralNetwork` class (at the bottom of banana_quality_neural_network.ipynb).

## Report

### Assumptions
- For the neural network, we assumed 1 hidden layer with 4 neurons. Our train/test split was 70% for training and 30% for testing.
- For the optimizer, we chose to add momentum. Our optimized weight update equation is as follows:
<p align="center">
  <img width="242" alt="Screenshot 2024-03-21 at 4 46 23 PM"  src="https://github.com/iamudyavar/banana_quality_neural_network/assets/75750607/bfb40802-1621-429a-abad-3f26e51417a7">
</p>

- The hyperparameters are activation function, activation function derivative, learning rate, number of epochs, and the momentum constant.

### Findings
| Activation Function | Learning Rate | Epochs | Momentum Constant | Training Accuracy | Test Accuracy |
| ------------------- | ------------- | ------ | ----------------- | ----------------- | ------------- |
| Sigmoid             | 0.03          | 100    | 0.9               | 0.8266            | 0.8258        |
| Sigmoid             | 0.3           | 100    | 0.9               | 0.7738            | 0.7824        |
| Sigmoid             | 0.03          | 50     | 0.9               | 0.8244            | 0.8196        |
| Sigmoid             | 0.03          | 10     | 0.9               | 0.8252            | 0.8206        |
| Sigmoid             | 0.03          | 100    | 0.3               | 0.8212            | 0.8138        |
| Tanh                | 0.03          | 100    | 0.9               | 0.8622            | 0.8588        |
| Tanh                | 0.3           | 100    | 0.9               | 0.5048            | 0.4862        |
| Tanh                | 0.03          | 50     | 0.9               | 0.852             | 0.8496        |
| Tanh                | 0.03          | 10     | 0.9               | 0.8258            | 0.8284        |
| Tanh                | 0.03          | 100    | 0.3               | 0.5019            | 0.4929        |
| ReLu                | 0.03          | 100    | 0.9               | 0.5366            | 0.5432        |
| ReLu                | 0.3           | 100    | 0.9               | 0.5006            | 0.4964        |
| ReLu                | 0.03          | 50     | 0.9               | 0.5428            | 0.5366        |
| ReLu                | 0.03          | 10     | 0.9               | 0.4968            | 0.5048        |
| ReLu                | 0.03          | 100    | 0.3               | 0.5832            | 0.5782        |

From tuning the model parameters, we found an optimal combination of hyperparameters. In general, a lower learning rate yielded a higher accuracy score for both training and testing. This is likely because a large learning rate causes the model to take larger steps and cross over the optimal solution. As for the number of epochs, a smaller value was detrimental to the model's accuracy. Larger epoch numbers improved the accuracy since it allowed the network to make more passes and converge weights around an optimal value.





