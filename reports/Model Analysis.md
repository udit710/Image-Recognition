# Analysis of Final Model

 1. Introduction
The goal of this deep learning model is to classify images into 40 categories of activities and detect whether multiple people are present. I have used a ResNet50-based architecture using transfer learning for this task.

 2. Data Description
- Dataset: The dataset consists of 4500 images categorised into 40 activity classes.
- Pre-processing: Images were resized to 224x224 pixels, and data augmentation techniques including rotation and flipping were applied.

 3. Model Architecture & Training Procedure
For the base model, I have used transfer learning with ResNet50 as the pretrained model. This is fine-tuned with an additional dense layer for regularisation. This is followed by two output layers – one for activity classification (40 classes) and one for binary person detection. I have also used custom loss functions for multi-task learning. I used a learning rate of 1e-2 initially. This did not give great results as the accuracy for the model was too low at about 7.77% and 65.69% for Class and MoreThanOnePerson respectively.

After some careful consideration and analysis (observations mentioned thoroughly in the code) I decided to perform Hyper parameter tuning by adjusting the learning rate. For this task, GridSearch seemed to be the optimal method as it allows us to check every parameter which in turn, leads to higher chance of improvement. The reason for not using other tuning methods was because the parameters were less, so to preserve simplicity, GridSearch was chosen.

On conducting hyper parameter tuning, the best learning rate was found to be 1e-4. When trained with the same, we got an accuracy of 73.75% and 85.14% for Class and MoreThanOnePerson respectively. The loss was low at 1.77. This pointed towards a slightly overfit. To mitigate overfitting, I decided to try data augmentation. On conducting augmentation, I got a slightly higher accuracy of about 75.28% and 84.58% for Class and MoreThanOnePerson respectively.

The downside here was that the model was even more overfit. I reduced the number of epochs to 10 for the fine-tuned model to prevent overfitting. While the augmented model had a lower loss, I chose the fine-tuned one because it achieved good accuracy with a reasonable loss.