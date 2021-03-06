# Distracted_Driver-_Detection
Model that detects distracted driver while driving

![MKT](https://img.shields.io/badge/version-v0.1-blue.svg)
![MKT](https://img.shields.io/badge/language-Python-green.svg)
![MKT](https://img.shields.io/badge/platform-GoogleColab-orange.svg)


- The objective of this task is to classify each driver's behavior. 

- The dataset used is from the Kraggle competition:            https://www.kaggle.com/c/state-farm-distracted-driver-detection.
  - I have used only 600 images per class i.e 6000 images in train.
- c0: safe driving
- c1: texting - right
- c2: talking on the phone - right
- c3: texting - left
- c4: talking on the phone - left
- c5: operating the radio
- c6: drinking
- c7: reaching behind
- c8: hair and makeup
- c9: talking to passenger

![alt text](https://github.com/shyamprasad369/Distracted_Driver-_Detection/blob/master/data.png)


## Data Processing:
- All the images in train and test are of size 480*600.
- Resizing the images to 240*240.
- Changing all images into gray scale from RGB.
- Storing the updated images according to classes in training_data.

## Creating Model:
Implemented Convolutional Neural Network(CNN) architecture in keras.
- Model has 3 CNN layers and 2 Dense layer
- Each layer is having 2 Conv2D layers and 1 BatchNormalization.
- Using loss='categorical_crossentropy' 
  - In the specific case of Multi-Class classification the labels are one-hot encoded. If we use this loss, we will train a CNN to    output a probability over the classes for each image.
  
## Model performance:
- Increase in epochs increased accuracy and loss has been decreased.
- Without adding BatchNormalization got train accuracy as 14% and with it gave me 96%

## Testing the model:
- Made the same data processing for test data.
- Predicting the output using the model.

## Save the Model & Weights:

Saving the model and the weights for transfer learning or model execution later

model.save_weights('./driverdistraction_lr_weights.h5', overwrite=True)
model.save('./driverdistraction.h5')






















