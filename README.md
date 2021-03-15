# Artificial Neural Networks and Deep Learning

<p align="center">
    <img src="https://i.imgur.com/mPb3Qbd.gif" width="180" alt="Politecnico di Milano"/>
</p>

## Overview
In this repository you can find the Jupyter Notebooks used to take part at the competitions created for the Artifical Neural Networks and Deep Learning exam at Politecnico di Milano. The covered topics are the following:

* Image Classification
* Semantic Segmentation
* Visual Query Answering

Remember that the notebooks have not the goal to be runned as they are here, but they were runned for the competitions and partially re-runned for producing this repository. If you want to run them, download the datasets and modify the code in order to set the right paths. Finally, note that all the notebooks use tensorflow 2.0 and keras to create predictive models.


## Image Classification
[![Kaggle](https://img.shields.io/badge/open-kaggle-blue)](https://www.kaggle.com/c/ann-and-dl-image-classification)
[![Dataset](https://img.shields.io/badge/download-dataset-orange)](https://www.kaggle.com/c/17346/download-all)

The goal of this challenge is to build the best model to solve an image classification problem. The proposed dataset contains images of several objects belonging to 20 different classes and consists in 1554 training examples. Additional 500 images are provided to compute the final predictions to submit to Kaggle. 

<p align="center">
    <img src="https://i.imgur.com/rMPM6wf.png" width="650" alt="classification"/>
</p>

In order to achieve our best performance of 98.2% accuracy, we first extracted a validation set from the training data. Then all the training images were resized to a fixed dimension and augmented in order to tackle the problem of having few samples for each class. The final model exploits transfer learning using a InceptionResNet v2 with pretrained weights from Imagenet. To improve the accuracy, we unfroze the last layers to apply fine tuning. 


## Semantic Segmentation
[![Kaggle](https://img.shields.io/badge/open-kaggle-blue)](https://www.kaggle.com/c/ann-and-dl-image-segmentation)
[![Dataset](https://img.shields.io/badge/download-dataset-orange)](https://www.kaggle.com/c/17695/download-all)

The goal of this challenge is to build the best model to solve a segmentation problem. The proposed dataset contains 7647 aerial images of different areas. Given a 256x256 image, the model should learn how to segment buildings at pixel level, thus predicting for each pixel if it belongs to a building or not. Additional 1234 images are provided to compute the final predictions to submit to Kaggle. 

<p align="center">
    <img src="https://i.imgur.com/g4JmKl7.png" width="500" alt="segmentation"/>
</p>

In order to achieve our best performance of 0.61 intersection over union, we first extracted a validation set from the training data. As in the previous challenge, we applied data augmentation and we exploited transfer learning. More specifically, in the UNet shaped model we used VGG for the downsampling part and the pix2pix network for the upsampling part.  

## Visual Query Answering 
[![Kaggle](https://img.shields.io/badge/open-kaggle-blue)](https://www.kaggle.com/c/ann-and-dl-vqa)
[![Dataset](https://img.shields.io/badge/download-dataset-orange)](https://www.kaggle.com/c/17987/download-all)

The goal of this challenge is to build the best model to solve a visual query answering problem. The proposed dataset contains 69642 synthetic scenes composed by several objects and corresponding 259492 questions about the existence of something in the scene (e.g. "Is there a yellow thing?") or about counting (e.g. "How many big objects are there?"). Given a 320x480 image and a question, the goal is to answer correctly. Additional 2754 images and 3000 questions are provided to compute the final predictions to submit to Kaggle. 

<p align="center">
    <img src="https://i.imgur.com/9fNa4oc.png" width="350" alt="visual query answering"/>
</p>

In order to achieve our best performance of 34.2% categorization accuracy, we first built a data generator to solve the problem of fitting the images in memory. Then we read the questions from the json file and tokenized them. The final model consists in the collaboration between a convolutional neural network based on VGG and a bidirectional GRU recurrent network, concatenated thanks to a final dense part.

## Team
- Samuele Meta [[Github](https://github.com/SamueleMeta)] [[Email](mailto:samuele.meta@mail.polimi.it)]
- Stiven Metaj [[Github](https://github.com/StivenMetaj)] [[Email](mailto:stiven.metaj@mail.polimi.it)]
