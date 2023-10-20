# FakeVoiceModels

## Python Version = 3.9.18

Update:
Dataset = train, development and evaluation data (Train data is for training, development data is for evaluation for each epoch, and evaluation data is equivalent to testing data)
- mfcc
- data agumentation (could chanage hyperparameters)
- feature normalization
- CNN with drop out rate of 0.7 (use this for now)
- batch normalization
- learning rate scheduler (could change = linear, exponential or time based)
- threshold = 0.7
- epoch = 30
- batch size = 32

Goal:
- stablize the evaluation performance (fluctations in validation accuracy are acceptable in early epochs but later on, they should stablize)
- accuracy is important but model stability is more important than accuracy number itself.
- model should generalize, not overfit

Task: 
For tuning hyperparameters, experiment with
- different learning rate scheduler (priorities)
- data agumentation strateiges (priorities)

- regularization techniques
- model architecture
- early stopping

Note:
- learning rate scheduler gives more flexibility as we go through each epoch, time-based and exponential tend to perform better than linear or fixed rate because
it adjusts the rate as we go down each epoch
- methods of data agumentation can also influence model performance. Strong parameters in data agumentation can introduce noise and may lead to overfitting

- for now stick with 0.7 drop out rate (0.5 - 0.8 is a standard range) and L2 regularization (since it's a standard)
- for now, do not change the model architecture

Record the results somewhere (I have experiments.txt file)

__________
Old experiments: Dataset = train data
- mfcc
- data agumentation
- feature normalization
- CNN with drop out rate of 0.8
- batch normalization
- learning rate scheduler with patience = 5
- threshold = 0.7
- epoch = 20
- batch size = 32

Test Loss: 0.18166127800941467
Test Accuracy: 0.9712371826171875

About dataset:
- The 2019 edition focuses on countermeasures for all three major attack types, mainly from TTS, VC and replay spoofing attacks.
- While the training and development sets contain spoofing attacks generated with the same algorithms/conditions (designated as known attacks), the evaluation set also contains attacks generated with different algorithms/conditions (designated as unknown attacks). Reliable spoofing detection performance therefore calls for systems that generalise well to previously-unseen spoofing attacks.


__________

## NEW ENSEMBLE MODEL

Article used for training ensemble model : https://medium.com/@alexppppp/how-to-train-an-ensemble-of-convolutional-neural-networks-for-image-classification-8fc69b087d3 

Dataset used for training - AsvSpoof 2019

num_epochs = 20
learning_rate = 0.001
batch_size = 32