U-Net-Networks-for- Semantic Segmentaion bright field microscopic time-series images
Cell segmentation from telecentric bright-field transmitted light microscopic images using a Residual Attention U-Net: a case study on HeLa line

The results of Cell segmentation based on living HeLa cell line images achieved by transmitted light microscope. Check the Wiki page for Documentation.

Check the Project tab for tracking tasks.

To download database you can use :

https://jucb-my.sharepoint.com/:f:/r/personal/ghaznavi_jcu_cz/Documents/Data/Dataset?csf=1&web=1&e=IqWkGcdatasets

Training, Testing and Validation datasets are separately avalivale in linked repository

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

calculating Precition, Recall, IoU, Accuracy, Dice

Updated: 10 May 2022.
