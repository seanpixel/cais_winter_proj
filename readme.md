Sean Ahn (seohoahn@usc.edu)

# Task
Classifying 29 different ASL hand patterns using a training data set containing 87,000 images which are 200 x 200 pixels.

# Dataset
Kaggle ASL hand patterns dataset available at (https://www.kaggle.com/datasets/grassknoted/asl-alphabet)

The dataset was divided into Train, Validation, and Test using at 8, 1, 1 ratio. For each file, the images were put into a folder named after the character which the hand pattern represented.

For image preprocessing, I kept it simple and only used random horizontal flipping on the training data to make the model more robust. Then, I transformed the images into tensors and normalized them using the standard values.

# Model Development and Training

The bulk of the model is the Resnet-18 model pretrained to detect features. I replaced the last fully connected layer with a linear layer with 29 outputs, each output corresponding to one character. For the loss function, I used Categorical Cross Entropy as it is one of the standard loss functions when categorizing images. I also used the Adam optimizer, which is another standard practice for image classification. Since I used the Adam optimizer, I did not have to worry too much about the learning rate but I kept it at 0.001, another standard and common value.

# Model Evaluation/Results

Metric chosen: Percent accuracy
Results on given metric: 99.26% Accuracy on Test Dataset

# Conclusion
I believe that the dataset, model architecture, and chosen metrics all suitably fit the task at hand of classifying different hand patterns. Firstly, the dataset from Kaggle was diverse and well-labeled. It contained a wide range of ASL hand signatures. Next, I believe that it was a suitable choice to use the Resnet-18 pretrained feature extractor as the model is widely used to do similar tasks: identify patterns and features of images to be used for classification. Lastly, I used a simple metric of accuracy percentage, which is well suited for a binary correct/incorrect testing procedure. I believe that all of these choices led to the model's success and its accuracy of 99.26%

The model's social implication/contribution is quite apparent: through the use of this model, sign language can be transcribed with near perfect accuracy to language, meaning that not everyone has to know sign language to be able to understand people who are unable to speak through the use of this model. An example of a place where the model can be used is at a conference where the speaker is only able to communicate through sign language. Since the members of the audience will most likely not all know sign language, the model can be used to change ASL to language.

My next steps of this project would be to go the other way around: I would find a way to transform speech into sign language. I believe that this reversed model has more use cases as people who use ASL are mostly deaf and cannot hear. 