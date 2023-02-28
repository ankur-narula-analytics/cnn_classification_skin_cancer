# Skin Cancer Type Detection
> Build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.


## Table of Contents
* [Setup](#setup-information)
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## Setup
- Download the notebook (.ipynb) file, upload the zip data shared on portal to google drive, change the respective path in top cells and everything should run smoothly
- Preferably use google colab so that nothing extra needs to be installed

## General Information
- This is multi class classification problem (9 classes), consisting images as the input data source. Therefore, we have build a custom CNN model. Also, as instructed transfer learning has not been used. However, that can be used as well to speed up the process
- Input data is a zip file, which is needed to be unzipped and then used for training the model
- Out technical goal is to define best finalised model architecture in minimal iterations and the conclusions behind each successful/ unsuccessful attempts. Business goal is to predict the right type of cancer based on images so that appropriate action plan can be followed to cure it before time with early accurate predcitions
- The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
- Vanilla model of type sequential using 4 convolutional & pooling layers, a flatten layer and dense layer at the end : We can see overfitting as per train (81) and validation accuracy (52) as well as loss. Next steps to try in order to reduce overfitting are : reduce complexity of network and add dropout, then try adding batch normalization
- Vanilla Model removing last layer of Conv2D & Pool2D and adding dropout : We can see overfitting has reduced from previous iteration but there is still significant difference between train and validation accuracy.
- Vanilla Model removing last layer of Conv2D & Pool2D and adding batch normalization : We can see Batch Normalization doesn't help reduce overfitting. But as next step to further reduce Overfitting with the initial model + dropout, we can apply augmentation for images
- Vanilla Model removing last layer of Conv2D & Pool2D and adding batch normalization + DATA AUGMENTATION (generalised) : We can see overfitting has reduced by a lot extent and this shows data augmentation worked out really well and improve the overall model. Next step to further improve the model accuracy is to check if there is any class imbalance and treat it
- Vanilla Model and adding dropouts + DATA AUGMENTATION + CLASS IMBALANCE VALIDATION & TREATMENT : With the final iteraton we have managed to eliminate overfitting and the overall accuracy has also increased considerably, thus reducing underfitting as well. From all the iterations the final successful model came after having 3 convolution and pooling later along with flatten and dense, later adding dropouts, image augmentation in general, and image augmentation to reduce class imbalance separately. One last iteration testing removing dropouts to increase accuracy as the expectation is that data augmentation itself is taking care of accuracy
- Vanilla Model + DATA AUGMENTATION + CLASS IMBALANCE VALIDATION & TREATMENT : This shows that surely removing dropout has helped increase the accuracy still keeping overfitting in check. We have a good model ready with these iterations with generalised architecture. To further improve from here we can increase the number of layers of Convolution and Pooling, add adding more images and increase epochs with early stopping as precaution. However in terms of modelling this architecture seems like the best one to go forward with.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- numpy
- pandas
- os
- pathlib
- matplotlib.pyplot
- PIL
- tensorflow
- warnings 
- augmentator
- glob
- google.colab
- Labelencoder
- Counter

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project was inspired by...
- References if any...
- This project was based on [this tutorial](https://www.example.com).


## Contact
Created by [@ankur-narula-analytics] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
