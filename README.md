# CNN-model-DoggyApp
Welcome! 

It's a core component of the **DoggyApp** project, where I developed the convolution neural network (CNN) for classification of dog breeds from images.
The CNN model uses transfer learning base on pre-trained architecture MobileNetV3-Large in the problem of multi-class image classification, making it efficient for deployment. Pre-trained model has excellent accuracy with small number of params – 5.5M.

## Data Analysis
The dataset is called **["70 Dog Breeds-Image Data Set"](https://www.kaggle.com/datasets/gpiosenka/70-dog-breedsimage-data-set)** and contains 70 categories of unique dog breeds from Kaggle. This collection comprises 9346 pictures in .jpg format, which are split into:

- Training: 85%
- Validation: 7.5%
- Test: 7.5%

All images are resized to **224×224 pixels** and have **3 RGB channels**.

This dataset has imbalanced classes, so data augmentation was done. The project used a variety of image transformation techniques, including randomly selecting a delta value to adjust brightness, randomly flipping the image both vertically and horizontally, setting lower and upper limits for the contrast ratio to produce random changes in contrast.

## Model details
The customized model structure consists of the following layers:
 - **Input layer:** `(224×224×3)`
- **Data augmentation layer**
- **Base model:** Pre-trained `MobileNetV3-Large`, with its top layers frozen
- **Fully connected layers**:
  - `Dense(512)`, ReLU activation
  - `Dropout(0.3)`
  - `Dense(256)`, ReLU activation
  - `Dropout(0.3)`
- **Output layer**:
  - `Dense(70)`, Softmax activation

`categorical cross-entropy` loss function was chosen for this model due to the presence of 70 class labels in the dataset. This selection is suitable for addressing the multiple class classification problems, where a unitary code labels the data. 

## Results

The developed model was tested and demonstrated the **final accuracy is 96%**. Resulting metrics for some classes on the test sample.
|    Class            | Precision | Recall |  F1-score |
| :---                |    :---:  |  :---: |    :---:  |
| American Hairless   | 0.90      | 0.90   | 0.90      |
| Basset              | 0.91      | 1      | 0.95      |
| Dingo               | 0.82      | 0.90   | 0.86      |
| Doberman            | 1         | 0.90   | 0.95      |
| Rhodesian Ridgeback | 1         | 0.90   | 0.95      |

Below is an example of model predictions on 12 random images. The correct predictions  are shown in **green**, incorrect ones in **red**.
![Prediction sample](https://github.com/user-attachments/assets/83594d24-616d-4e95-8924-546737f69b37)

# Thank you for your attention💕
