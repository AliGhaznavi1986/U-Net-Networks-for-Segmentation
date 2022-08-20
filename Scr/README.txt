
This Telecentric bright-field_README.txt file was generated on 2022-08-13 by Ali Ghaznavi


GENERAL INFORMATION

1. Cell segmentation from telecentric bright-field transmitted light microscopy images using a Residual Attention U-Net: A case study on HeLa line


2. Author Information
	First-author 
		Name: MSc. Ali Ghaznavi 
		Institution: Institute of Complex Systems, University of South Bohemia in České Budějovice, Zámek 136, 373 33, Nové Hrady, Czech Republic
		Email: ghaznavi@frov.jcu.cz

	Corresponding author 
		Name: Dr. Renata Rychtáriková
		Institution: Institute of Complex Systems, University of South Bohemia in České Budějovice, Zámek 136, 373 33, Nové Hrady, Czech Republic
		Email: rrychtarikova@frov.jcu.cz

	Co-author 
		Name: Dr. Mohammadmehdi Saberioon
		Institution: Helmholtz Centre Potsdam, GFZ German Research Centre for Geosciences, Section 1.4 Remote Sensing and Geoinformatics, Telegrafenberg, Potsdam 14473, Germany
		Email: saberioon@gfz-potsdam.de

	Co-author 
		Name: Prof. Dalibor Štys
		Institution: Institute of Complex Systems, University of South Bohemia in České Budějovice, Zámek 136, 373 33, Nové Hrady, Czech Republic
		Email: stys@frov.jcu.cz




3. Date of data collection: 2021

4. Geographic location of data collection: Nové Hrady, Czech Republic

5. Funding sources that supported the collection of the data: Ministry of Education, Youth and Sports of the Czech Republic – project CENAKVA (LM2018099), European Regional Development Fund in the frame of the project ImageHeadstart (ATCZ215) in the Interreg V-A Austria–Czech Republic programme, and GAJU 017/2016/Z.

6. Recommended citation for this dataset: Ghaznavi A., Rychtáriková R., Saberioon M., Štys D. Telecentric bright-field transmitted light microscopic dataset (2022), 10.5061/dryad.80gb5mksp, Dryad, Dataset.


DATA & FILE OVERVIEW

1- Description of HeLa dataset
	Human Negroid cervical epithelioid carcinoma line HeLa was chosen as a testing cell line for microscopy image segmentation task. The reason for choosing is that HeLa is the oldest, immortal, and most used model cell line ever. HeLa is cultivated in almost all tissue and cell laboratories worldwide and utilized in many fields of medical research, such as research on carcinoma or testing the material biocompatibility.
	Human HeLa cell line (European Collection of Cell Cultures, Cat. No. 93021013) was cultivated to low optical density overnight at 37°C, 5% CO2, and 90% relative humidity. The nutrient solution consisted of Dulbecco’s modified Eagle medium (87.7%) with high glucose (1 g L−1), fetal bovine serum (10%), antibiotics and antimycotics (1%), L-glutamine (1%), and gentamicin (0.3%; all purchased from Biowest, Nuaille, France). The HeLa cells were maintained in a Petri dish with a cover glass bottom and lid at temperature of 37°C.

2- Description of bright-field microscope
	Time-lapse image series of living human HeLa cells on the glass Petri dish were captured using a high-resolved bright-field light microscope (designed by the Institute of Complex System Nové Hrady, CZ; built by Optax, Prague, CZ and ImageCode, Brloh, CZ in 2021).
	The microscope has a simple construction of the optical path. The light from two light-emitting diods CL-41 (Optika Microscopes, Ponteranica, Italy) passes through a sample to reach a telecentric measurement objective TO4.5/43.4-48-F-WN (Vision & Control GmbH, Shul, Germany) and an Arducam AR1820HS 1/2.3-inch 10-bit RGB camera with a chip of 4912 × 3684 pixel resolution.
	The images were captured as a primary (raw) signal with theoretical pixel size (size of the object projected onto the camera pixel) of 113 nm. The software sinchronizes the capture of the primary signal with the camera exposure (of 2.75 ms in this case).
	All these experiments were performed in time-lapse to observe cells’ behaviour over time.

3- Data preparation steps
	3-1 Calibration of all time-lapse experiments images to avoid image background inhomogeneities and noise (more information in section 2-2 of DOI:10.1016/j.compbiomed.2022.105805).
	3-2 Conversion of the raw image representations to 8-bit colour (rgb) images of resolution (number of pixels) quarter of the original raw images by applying quadruplets of Bayer mask pixels (more information in section 2-2 of DOI:10.1016/j.compbiomed.2022.105805).
	3-3 Applying means denoising method to minimize the background noise in the constructed RGB images at preserving the texture details.
	3-4 Cropping the image series to the 1024 × 1024 pixel size.
	The steps described 3-1 -- 3-4 gave us 500 images from different time-lapse experiments on HeLa cells.
	3-5 Manual labelling the cells in the images in MATLAB (MathWorks Inc., Natick, Massachusetts, USA) as Ground-Truth (GT) single class masks with the dimension of 1024 × 1024.
	3-6 Usage of 500 labelled images as training (80%), testing (20%), and evaluation (20% of the training set) sets for the U-Net networks.


4- METHODOLOGICAL INFORMATION
The U-Net is a semantic segmentation method proposed on the FCN architecture. The FCN consists of a typical encoder–decoder convolutional network. This architecture includes several feature channels to combine shallow and deep features.
The first architecture we applied to our dataset was a simple U-Net. We reached the Mean-IoU score of 0.9505 for our dataset.
In the second step, we added a soft attention mechanism into the U-Net architecture to highlight the relevant image parts containing cells and improve our segmentation result. The Mean-IoU score for our datasets reached to 0.9524.
In the final step, we added a residual mechanism into the Attention U-Net architecture to overcome the gradient vanishing problem. We improved the segmentation result slightly to Mean-IoU score of 0.9530.
(More information in section 2-3 of DOI:10.1016/j.compbiomed.2022.105805.)

5- Training Models
	5-1 The computation was implemented in Python 3.7. The framework for deep learning was Keras, and the backend was Tensorflow.
	5-2 The whole method, including the Deep Learning framework, was transferred and executed on the Google Colab Pro account with P100 and T4 GPU, 24 Gb of RAM, and 2 vCPU.
	5-3 The primary dataset (of 500 images) was divided into a set of 400 images and a testing set of 100 images. A part of the fist set (320 images, 80%) was used for the model training. The second part of the first set (80 images, 20%) was used for model validation.
	5-4 Since the network architectures work with a specific size of the input images, all datasets were resized to the 512 × 512 pixel size.


DATA-SPECIFIC INFORMATION FOR: Folder spilit_x_image_train
	The train folder contains 320 images selected randomly among all datasets to train the models based on our Train set.

DATA-SPECIFIC INFORMATION FOR: Folder spilit_y_mask_train
	The train folder contains 320 masks created manually as the Ground-Truth set (described in section 3-5) to train the models based on our Train set.


DATA-SPECIFIC INFORMATION FOR: Folder spilit_x_image_validate
	The val folder contains 80 images selected randomly among all datasets to train and validate the models using our Train set and Validation set.


DATA-SPECIFIC INFORMATION FOR: Folder spilit_y_mask_validate
	The val folder contains 80 masks created manually as the Ground-Truth set (described in section 3-5) to train and validate the models using our Train set and Validation Set.

DATA-SPECIFIC INFORMATION FOR: Folder spilit_x_image_test
	The test folder contains 100 images selected randomly among all datasets to test the models' performance after the training process and evaluate the models' performance using appropriate metrics.

DATA-SPECIFIC INFORMATION FOR: Folder spilit_y_mask_test
	The test folder contains 100 masks created manually as the Ground-Truth set (described in section 3-5) to test the models' performance after the training process and evaluate the models' performance with the Test set using appropriate metrics.


6- Evaluation metrics (More information section 2-5 DOI:10.1016/j.compbiomed.2022.105805)
	Overall pixel accuracy (Acc): represents a per cent of image pixels belonging to the correctly segmented cells
	Precision (Pre): is a proportion of the cell pixels in the segmentation results that match the GT
	The Recall (Recl): represents the proportion of cell pixels in the GT correctly identified through the segmentation process
	F1-score or Dice similarity coefficient (m-Dice): states how the predicted segmented region matches the GT in location and level of details and considers each class’s false alarm and missed value
	Jaccard similarity index or Intersection over Union (m-IoU): is a correlation among the prediction and GT, and represents the overlap and union area ratio for the predicted and GT segmentation.

7- Result (More information in section 3 of DOI:10.1016/j.compbiomed.2022.105805)
	Simple U-Net: Acc = 0.9574  --  m-IoU = 0.9505  --  m-Dice = 0.9744
	Attention U-Net: Acc = 0.9594  -- m-IoU = 0.9524  --  m-Dice = 0.9755
	Residual Attention U-Net: Acc = 0.9600  --  m-IoU = 0.9530  --  m-Dice = 0.9758


