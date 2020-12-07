# Results and Discussion:

## Exploratory Data Analysis

As mentioned in the previous section, EDA is an effective approach to analyze the present dataset for identification, quantification, and characterization of pore system in cement-based matrix.
 ### Identifying Grayscale Value  Distribution 
The images from baches 1 and 2 were analyzed to recognize if there is any data could be extracted. 


18 shows how the distribution of greyscale values within the batch 1. 

<img src ="images/histogram_batch1_combined.png" width =1100> 

    Figure 18: left) histogram showing the grayscale value distribution of images in batch 1; right) the distribution of grayscale value of images in batch 1

Also, fig 19 shows how the distribution of greyscale values within the batch 2.

<img src ="images/histogram_batch2_combined.png" width =1100> 
    
    Figure 19: left) histogram showing the grayscale value distribution of images in batch 2; right) the distribution of grayscale value of images in batch 2

Interestingly, the distributions of grayscale values for both batchs 1 and 2 are alike the grayscale value distribution distribution in fig 4. This confirms that the data acquired is reasonable and is valied to be analyzed.

 ### Estimating Porosity Distribution 

Followed by doing model calibration, it is now required to estimate distribution of porosities in each batch. For this purpose, histogram of porosities at threshold = 0 is sketched in Fig 20, with different bandwidth (bins) values. Considering this figure, histograms having smaller bandwidth value, i.e. bins = 10, suggest lognormality of porosities in each batch. 

<img src ="images/fig10.JPG" width =1100> 

    Figure 20: Finding distribution of porosities of each batch 
    
However, to determine whether the chosen lognormal distribution is valid, a method called probability plot was employed to prove lognormality of the distribution. Fig 21 shows a relatively high R-squared value found from the probability plot that validates the distribution.

<img src ="images/fig11.JPG" width =700> 

    Figure 21: Probability plot test of lognormality
    
By proving the lognormality of porosities in both batch 1 and 2, it is of interest to determine whether these two distribution matches at line y=x. Accordingly, the two lognormal distributions were plotted against each other that proves a high affinity, see Fig 22. It is worth noting that any point placed prior to the lognormal peak, marked with a dashed line was eliminated from the matching procedure.  

<img src ="images/fig12.JPG" width =900> 

    Figure 22: Matching lognormal distribution of porosities for batch1 and 2

## Feature Engineering

Using EDA, different features for characterizing porosity are extracted and shown in Fig 23. However, is required to determine whether these features are capable of estimating porosity accurately.

<img src ="images/fig17.JPG" width =1400> 

    Figure 23: Extracting features (physical and chemical) from SEM images using image analysis
    
Considering Fig 24, only Calcium Silicate Hydrate (C-S-H), Portlandite (C-H), and Angularity features have strong correlation, i.e. either positive or negative, with porosity. Consequently, these features are likely to be predictive of pore volume fraction for use in Artificial Neural Network.  

<img src ="images/fig18.JPG" width =1400> 

    Figure 24: SNS heatmap of correlations between features extracted using image analysis

### Application of ANN for estimating Porosities based on Cement Chemistry: C-S-H & C-H (Model I)

In this step, extracted features represents chemical properties of cement and are highly correlated with pore volume fraction, i.e C-S-H and C-H. These features are selected to be possibly predictive of porosity. Considering Fig 25, it could be realized that the correlations between porosity and C-S-H or C-H could be both 
linear. In addition, increasing porosity would result in a reduction of both C-S-H and C-H values. 

<img src ="images/fig19.JPG" width =1100> 

    Figure 25: Porosity vs. C-S-H or C-H for both batches

To do ANN, training dataset are fed into the machine learning model. Fig 26 illustrates the features combined from batch 1 and 2, having 200 rows in total. 

<img src ="images/fig25.JPG" width =500> 

    Figure 26: Training dataset for ANN

Similarly, the testing dataset is fed into the model, which is used for validating the employed ANN. Fig 27 illustrates the selected features from batch3, which has 100 rows in total. 

<img src ="images/fig26.JPG" width =500> 

    Figure 27: Testing dataset for ANN
    
To evaluate the accuracy of ANN results, RMSE is evaluated for both testing and validation data sets, see Fig 28. As shown in this figure, the RMSE value is continuously decreased by increasing the number of epochs for both sets, while no overfitting of data is observed. 

<img src ="images/fig20.JPG" width =400> 

    Figure 28: Evaluation of RMSE vs. epochs in the first model
    
ANN also facilitates matching estimated versus true porosities of training and testing datasets, which are shown in Fig 29. This figure confirms the relative high accuracy of results, i.e. approximately 90% and 80% for testing and training datasets in spite of having a limited number, i.e. 200, of SEM images. 

<img src ="images/fig21.JPG" width =900> 

    Figure 29: Matching porosities (predicted vs. true) of training and testing datasets, first model 
 
As a result, the predicted porosity of Model I ANN is based on chemistry of cement hydrates. It was realized that increasing the level of C-S-H or C-H, which are both the main components of cement hydration products, could be an indication of sufficient cement curing, which is also known as matrix densification. The matrix densification minimizes the size of capillary pores, which explains why in Fig 25, porosity is anticorrelated with C-S-H or C-H. 

### Application of ANN for estimating porosities based a combination of physical and chemical properties: C-S-H & Angularity (Model II)

It is also of interest to determine whether the extracted features, that explains chemical (C-S-H) and physical properties (Angularity of pores) of cement matrix, are highly correlated with pore volume fraction. For this purpose, C-S-H together with angularity are chosen to be possibly predictive of porosity. Figure 30 represents existence of a strong nonlinear correlation between porosities and C-S-H or angularity. In addition, it was found that increasing porosity would enhance angularity of capillary pores. 

<img src ="images/fig22.JPG" width =1100> 

    Figure 30: Porosity vs. C-S-H or Angularity for both batch1 and 2
  
To evaluate the accuracy of ANN results, RMSE is evaluated for both testing and validation data sets, see Fig 31. As shown in this figure, the RMSE value is continuously decreased by increasing the number of epochs for both sets, while no overfitting of data is observed. 

<img src ="images/fig23.JPG" width =400> 

    Figure 31: Evaluation of RMSE vs. epochs in the second model
    
ANN also facilitates statistical matching estimated versus true porosities of training and testing datasets, which are shown in Fig 32. This figure confirms the relative high accuracy of results, i.e. approximately 70% and 60% for testing and training datasets in spite of having a limited number, i.e. 200, of SEM images. 

<img src ="images/fig24.JPG" width =900> 

    Figure 32: matching porosities for training and testing datasets, second model

Model II is also capable of relating physical as well as chemical properties of cement to its porosity, but with lower accuracy compared with Model I. The reduction in results accuracy could be attributed to the formula introduced in this paper for calculation of angularity. Nonetheless, to the authors knowledge, for the first time in the literature, angularity of pores was found to be correlated with porosity. This phenomenon shall be further explored in the future research.   

### Appllication of CNN for classifying porosity using SEM images (Model III)

Images from both batches 1 and 2 were merged into a single batch to ease working on all images. Fig 33 shows example of the categorized images. In fact, images are classified  into four different categories 0% to 10% porotity is class one, 10% to 20% is class two, 20% to 30% is class three 30% to 100% is class four

<img src ="images/categorized_images.png" width =300>

    Figure 33: a snapshot showing the categorized images from both batches 1 and 2

CNN model was build using the 200 imges from the training dataset and applied to predict the porosity 100 images in the testing dataset. Fig 34 shows the acuuracy values for both training and testing datasets. Also Fig 35 shows the loss values for both batches training and testing datasets.

<img src ="images/loss.png" width = 450>

    Figure 34: accuracy valeus for both training and testing datasets
    
<img src ="images/accuracy.png" width = 450>

    Figure 35: loss valeus for both training and testing datasets

It could be seen that both the accuracy and loss values for training and testing datasets are approching to each other. This confirms the validity of the model. However, the accuracy values are not very high, this is expected due to having a very limited number of images.
