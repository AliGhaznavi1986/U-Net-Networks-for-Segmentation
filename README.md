# Different U-Net - Neural Networks architecture for Semantic Segmentaion from bright field microscopic time-series images
Cell segmentation from telecentric bright-field transmitted light microscopic images using a Residual Attention U-Net:
a case study on HeLa line

The results of Cell segmentation based on living HeLa cell line images achieved by transmitted light microscope.


To download Dataset you can use :

https://jucb-my.sharepoint.com/:f:/g/personal/ghaznavi_jcu_cz/EnCjuDqA5ixFmhXUn4G2JykBri7f0cUn1yDG4hjJ8JyXpQ?e=GXRslS

Training, Testing and Validation datasets are separately avalivale in linked repository

To download Generated Models you can use :

https://jucb-my.sharepoint.com/:f:/g/personal/ghaznavi_jcu_cz/Etu-CJIqxbdPs_nmsCqRw4ABq6vru9xUyPM-4lGJSuEnVQ?e=og6Wsg


The repository contain Simple U-Net, Attention U-Net and Residual Attention U-Net Models and Epocks details.

To run the script please use Google Colab or Jupyter:


Modelling Bright Filed Dataset on U-Net Networks:

Important hyperparameters setup:


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

