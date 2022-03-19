# Melanoma-Diagnosis-Using-Lesion-Segmentation
In this task we worked on ISIC challenge where we segment lesions (foreground) out of dermoscopic images.

## Data-Set
We used **ISIC’s 2017** train, validation and test sets.
- The Train set consists of: 2000 images along with their ground truth masks and superpixel images(discard for this assignment).
- The mask would contain 2 values: 0 for background and 255 for foreground.
- During training we converted the mask to 0, and 1 values before feeding it to the network.
- The resized data is available at the following **[link](www.kaggle.com/dataset/536bd89301ea318c98b9c1baa7edc57b5d30ecc9e2d807f45d77e9ef7491adfb)**. 

Image             |  Segmentation Mask 
:-------------------------:|:-------------------------:
![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/trainImg.PNG)  |  ![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/trainG%20.PNG)


## Convolutional Neural Networks  
### 1. Fully Convolution Network (FCN): 
- It is implemented using a VGG-16 backbone.
- Instead of the 3 fully connected classification layers, the first two were replaced with a
 1x1 convolution with the same number of filters.
- The last layer was replaced with 1x1 convolution layer with the number of filters equals the number of classes.
-  Finally, a deconvolutional layer that upsamples the output to the original image size was added to produce the final prediction.

### 2.UNet: 
- Instead of producing the output as a sever upsampling out of the last feature map,
it desiged a decoder that doubles the feature map size until it reached the image size.
- It introduced the skip connection technique to combine the encoder and decoder
learned features to produce finer segmentation masks. 

## Results
The learning rate of the network was a hyperparameter. We trained our models in different values.

### FCN Results: 
LR = 0.01              |  LR = 0.01 
:-------------------------:|:-------------------------: 
![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/FCNBase1.jpeg)  |  ![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/FCNBase.jpeg) 

### UNet Results: 
LR = 0.01              |  LR = 0.01  |  LR = 0.001 
:-------------------------:|:-------------------------: |:-------------------------: 
![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/UNet1.jpeg)  |  ![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/UNet01.jpeg) |  ![This is an image](https://github.com/habiib1999/Melanoma-Diagnosis-Using-Lesion-Segmentation/blob/main/Results/UNet001.jpeg)


## Authors
- **[Moahmmed Aiman](https://github.com/MohammedAimanHESSin)**
- **[Osama Sherif](https://github.com/osamasherif22)**
- **[Abdulrahman Habib](https://github.com/habiib1999)**
- **[Ahmed Ashraf](https://github.com/ashraf336)**

---
_This README made with ❤️ by [Moahmmed Aiman](https://github.com/MohammedAimanHESSin) & [Osama Sherif](https://github.com/osamasherif22)_ 
