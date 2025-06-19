# CNN-model-DoggyApp
Welcome! 

It's a part of **DoggyApp** project, where I developed the convolution neural network (CNN) for classification dog breeds by image.
In process of creating СNN models use transfer learning base on pre-trained architecture MobileNetV3-Large in the problem of multi-class image classification. Pre-trained model has excelent accuracy with small number of params – 5.5M.

Let's move on to the details!

## Data Analysis
The dataset is called **"70 Dog Breeds-Image Data Set"** and contains 70 categories of unique dog breeds from Kaggle. This collection comprises 9346 pictures in .jpg format, which are categorized into training, validation, and test sets at the dataset level in the percentage ratio of 85%:7.5%:7.5%. All images are resized to a uniform dimension of 224×224 pixels and consist of three channels: red, green, blue. 

This dataset has imbalanced classes, so data augmentation was done. The project used a variety of image transformation techniques, including randomly selecting a delta value to adjust brightness, randomly flipping the image both vertically and horizontally, setting lower and upper limits for the contrast ratio to produce random changes in contrast.

## Model details
The customized model structure consists of:
 - **Input layer** that defines the input image's dimensions. The input images are then processed by resizing and scaling them.
 - **Data augmentation techniques** are applied to effectively expand the dataset. To generate various variations of images.
 - **Base model layers**
 - **Fully connected layers**: one with dimensions of 512×1 and another with dimensions of 256×1. Both layers apply the Rectified Linear Unit (ReLU) activation function.
 - **Dropout layers** are added between the classification layers to prevent the issue of overfitting. At each epoch, a random selection process with a probability of 0.3 selects neurons for training.
 - **Fully connected layer with 70 neurons** and a softmax activation function at its output to classify images into 70 unique class labels. 

The categorical cross-entropy loss function was chosen for this model due to the presence of 70 class labels in the dataset. This selection is suitable for addressing the multiple class classification problems, where a unitary code labels the data. Categorical cross-entropy is a method that operates on the model's output values, which indicate the likelihood of the input data belonging to various classes.


## Model's metrics

The developed model was tested and demonstrated the final accuracy is **96%**. Resulting metrics for some classes on the test sample.
|    Class            | Precision | Recall |  F1-score |
| :---                |    :---:  |  :---: |    :---:  |
| American Hairless   | 0.90      | 0.90   | 0.90      |
| Basset              | 0.91      | 1      | 0.95      |
| Dingo               | 0.82      | 0.90   | 0.86      |
| Doberman            | 1         | 0.90   | 0.95      |
| Rhodesian Ridgeback | 1         | 0.90   | 0.95      |


The example of determining the breed of a dog on a sample of 12 random images. The correct prediction of the breed is marked in green, the wrong one in red.
![image](https://github.com/user-attachments/assets/83594d24-616d-4e95-8924-546737f69b37)



# Thank you for your attention💕
