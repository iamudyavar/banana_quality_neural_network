# Identifying the quality of a banana with a neural network

## Dataset
Link to dataset: https://www.kaggle.com/datasets/l3llff/banana

## Steps to run
1. Navigate to the following Google Colab project, go to "Runtime", and "Run All". Wait for the run to finish to view the train and test error.
https://colab.research.google.com/drive/17gtdpw8Qczqz_EJEUFfQMUFcSEPG6Tdk?usp=sharing
2. To run locally, download "banana_quality_neural_network.ipynb" along with "banana_quality.csv" and place them in the same directory. Install the necessary packages (pandas, numpy, sklearn) and run the code. The parameters can be tuned in the line that initalizes the `NeuralNetwork` class (at the bottom of the banana_quality_neural_network.ipynb notebook).

## Report
Assumptions:
* For the neural network, we assumed 1 hidden layer with 4 neurons. Our train/test split was 70% for training and 30% for testing.
* For the optimizer, we chose to add momentum. Our weight update equation is as follows:
<p align="center">
  <img width="242" alt="Screenshot 2024-03-21 at 4 46 23 PM"  src="https://github.com/iamudyavar/banana_quality_neural_network/assets/75750607/bfb40802-1621-429a-abad-3f26e51417a7">
</p>
* The neural network has the following parameters: activation function, activation function derivative, learning rate, number of epochs, and the momentum constant.




