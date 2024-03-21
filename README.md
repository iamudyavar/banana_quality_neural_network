# Classifying the quality of a banana with a neural network

## Dataset
- Link to dataset: https://www.kaggle.com/datasets/l3llff/banana
- Problem statement: classify the quality (Good or Bad) of a banana based on its features.

## Steps to run
1. Navigate to the following Google Colab project, go to "Runtime", and "Run All". Wait for the run to finish to view the train and test error.
https://colab.research.google.com/drive/17gtdpw8Qczqz_EJEUFfQMUFcSEPG6Tdk?usp=sharing
2. To run locally, download "banana_quality_neural_network.ipynb" along with "banana_quality.csv" and place them in the same directory. Install the necessary packages (pandas, numpy, sklearn) and run the code. The hyperparameters can be tuned in the line initializing the `NeuralNetwork` class (at the bottom of "banana_quality_neural_network.ipynb").

## Report

### Assumptions
- We assumed 1 hidden layer with 4 neurons.
- Our train/test split was 70% for training and 30% for testing.
- We chose the following hyperparameters: activation function, learning rate, number of epochs, and momentum constant.
- For the optimizer, we chose to add momentum. Our weight update equation with momentum is as follows:
<p align="center">
  <img width="242" alt="Screenshot 2024-03-21 at 4 46 23 PM"  src="https://github.com/iamudyavar/banana_quality_neural_network/assets/75750607/bfb40802-1621-429a-abad-3f26e51417a7">
</p>

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

From tuning the model parameters, we found an optimal combination of hyperparameters. The Tanh activation function was the strongest, followed by Sigmoid and ReLu. Since our target value was non-negative (0 or 1), tanh performed well due to its larger range while ReLu performed poorly due to it acting as an identity function. For learning rate, a lower value yielded a higher accuracy score for both training and testing. This was because a large learning rate caused the model to cross over the optimal solution due to its larger step size. As for the number of epochs, a smaller value was detrimental to the model's accuracy. Larger epoch numbers generally improved the accuracy since it allowed the network to make more passes and converge weights around an optimal value. Finally, a momentum constant closer to 1 improved the model accuracy, because the network avoided oscillation by considering the previous weight values more heavily.





