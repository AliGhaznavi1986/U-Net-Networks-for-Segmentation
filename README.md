# U-Net-Networks-for-Segmentaion
Cell segmentation from telecentric bright-field transmitted light microscopic images using a Residual Attention U-Net:
a case study on HeLa line

The results of Cell segmentation based on living HeLa cell line images achieved by transmitted light microscope.
Check the Wiki page for Documentation.

Check the Project tab for tracking tasks.

To download database and Source code/datasets you can use :

git clone https://github.com/saberioon/WORLDSOILS.git
datasets are available in : data folder

To setup environment, first install poetry then using following code in your terminal:

poetry install
To activate your virtual environment use this :

poetry shell
merging_data.py:

merging two csv files based on their ID

python src/merging_data.py clhs_lucas15.csv S2a_resampled_lucas15.csv
fnn.py:

Modelling LUCAS or BSSL data using FNN

python src/fnn.py -i /path/to/input_file -o /path/to/output_folder -l 3 -e 400 -b 20 
-h: help

-l : number of hidden layer ; default = 3

-e : epoch size; default = 400

-b : batch size; default = 20

-d : droup out ; default = 0.2

-r : learning rate ; default = 0.01

-k : kernel initializer ; default = he_normal

LUCAS15_analysis.py:

Modelling LUCAS or BSSL data using FNN

python src/LUCAS15_analysis.py -i /path/to/input_file -o /path/to/output_folder
to see other keys use this :

python src/LUCAS15_analysis.py -h
metrics.py:

calculating R-square, RPD, MSE, RMSE

outlier_finder.py:

Finding outliers using Mahalanobis distance + Principal Component Analysis

Updated: 26 July 2021.

