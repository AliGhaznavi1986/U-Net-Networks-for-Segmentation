# Different U-Net - Neural Networks architecture for Semantic Segmentaion from bright field microscopic time-series images
Cell segmentation from telecentric bright-field transmitted light microscopic images using a Residual Attention U-Net:
a case study on HeLa line

The data  achieved by transmitted light microscope from living Hela cells in different time-laps experiments under the condition already have been described in manuscript and divided to train, test and validation sets.

The labeled data have been prepared manually to train with the deep learning based methods

The models have been trained based on three different U-Net architecture (with the size of 512 * 512) to achieve the best segmentation result already reported in manuscript.


To download Generated Models you can use link below :

https://jucb-my.sharepoint.com/:f:/g/personal/ghaznavi_jcu_cz/Etu-CJIqxbdPs_nmsCqRw4ABq6vru9xUyPM-4lGJSuEnVQ?e=bX7A3m


The repository contain Simple U-Net, Attention U-Net and Residual Attention U-Net Models and Epocks details.


To download Dataset you can use link below :

https://jucb-my.sharepoint.com/:f:/g/personal/ghaznavi_jcu_cz/EnCjuDqA5ixFmhXUn4G2JykBri7f0cUn1yDG4hjJ8JyXpQ?e=wCjTzq

Training, Testing and Validation datasets are separately avalivale in linked repository


To run the script please use Google Colab or Jupyter:


Modelling Bright Filed Dataset on U-Net Networks:

Important hyperparameters setup:

 Image Size  = 512 * 512
 
 number of layer ; default = 5
 
 Activation function = Leaky Relu

 epoch size; default = 100

 batch size; default = 8

 Early Stop = 15

 learning rate ; default = 10e -3
 
 Step per Ecopch = 100

 dropout_rate = 0.05


metrics:

Precition, Recall, IoU, Accuracy, Dice 


Updated: 10 May 2022.

