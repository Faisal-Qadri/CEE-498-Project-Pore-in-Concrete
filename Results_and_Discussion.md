# Results and Discussion:

## Exploratory Data Analysis

As mentioned in the previous section, EDA is an effective approach to analyze the present dataset for identification, quantification, and characterization of pore system in cement-based matrix.

 ### Estimating Porosity Distribution 

Followed by doing model calibration, it is now required to estimate distribution of porosities in each batch. For this purpose, histogram of porosities at threshold = 0 is sketched in Fig 10, with different bandwidth (bins) values. Considering this figure, histograms having smaller bandwidth value, i.e. bins = 10, suggest lognormality of porosities in each batch. 

<img src ="images/fig10.JPG" width =1100> 

    Figure 10: Finding distribution of porosities of each batch 
    
However, to determine whether the chosen lognormal distribution is valid, a method called probability plot was employed to prove lognormality of the distribution. Fig 11 shows a relatively high R-squared value found from the probability plot that validates the distribution.

<img src ="images/fig11.JPG" width =700> 

    Figure 11: Probability plot test of lognormality
    
By proving the lognormality of porosities in both batch 1 and 2, it is of interest to determine whether these two distribution matches at line y=x. Accordingly, the two lognormal distributions were plotted against each other that proves a high affinity, see Fig 12. It is worth noting that any point placed prior to the lognormal peak, marked with a dashed line was eliminated from the matching procedure.  

<img src ="images/fig12.JPG" width =900> 

    Figure 12: Matching lognormal distribution of porosities for batch1 and 2

## Feature Engineering

Using EDA, different features for characterizing porosity are extracted and shown in Fig 13. However, is required to determine whether these features are capable of estimating porosity accurately.

<img src ="images/fig17.JPG" width =1400> 

    Figure 13: Extracting features (physical and chemical) from SEM images using image analysis
    
Considering Fig 14, only Calcium Silicate Hydrate (C-S-H), Portlandite (C-H), and Angularity features have strong correlation, i.e. either positive or negative, with porosity. Consequently, these features are likely to be predictive of pore volume fraction for use in Artificial Neural Network.  

<img src ="images/fig18.JPG" width =1400> 

    Figure 14: SNS heatmap of correlations between features extracted using image analysis

### Application of ANN for estimating Porosities based on Cement Chemistry: C-S-H & C-H (Model I)

In this step, extracted features represents chemical properties of cement and are highly correlated with pore volume fraction, i.e C-S-H and C-H. These features are selected to be possibly predictive of porosity. Considering Fig 15, it could be realized that the correlations between porosity and C-S-H or C-H could be both 
linear. In addition, increasing porosity would result in a reduction of both C-S-H and C-H values. 

<img src ="images/fig19.JPG" width =1100> 

    Figure 15: Porosity vs. C-S-H or C-H for both batches

To do ANN, training dataset are fed into the machine learning model. Fig 16 illustrates the features combined from batch 1 and 2, having 200 rows in total. 

<img src ="images/fig25.JPG" width =500> 

    Figure 16: Training dataset for ANN

Similarly, the testing dataset is fed into the model, which is used for validating the employed ANN. Fig 17 illustrates the selected features from batch3, which has 100 rows in total. 

<img src ="images/fig26.JPG" width =500> 

    Figure 17: Testing dataset for ANN
    
To evaluate the accuracy of ANN results, RMSE is evaluated for both testing and validation data sets, see Fig 18. As shown in this figure, the RMSE value is continuously decreased by increasing the number of epochs for both sets, while no overfitting of data is observed. 

<img src ="images/fig20.JPG" width =400> 

    Figure 18: Evaluation of RMSE vs. epochs in the first model
    
ANN also facilitates matching estimated versus true porosities of training and testing datasets, which are shown in Fig 19. This figure confirms the relative high accuracy of results, i.e. approximately 90% and 80% for testing and training datasets in spite of having a limited number, i.e. 200, of SEM images. 

<img src ="images/fig21.JPG" width =900> 

    Figure 19: Matching porosities (predicted vs. true) of training and testing datasets, first model 
 
As a result, the predicted porosity of Model I ANN is based on chemistry of cement hydrates. It was realized that increasing the level of C-S-H or C-H, which are both the main components of cement hydration products, could be an indication of sufficient cement curing, which is also known as matrix densification. The matrix densification minimizes the size of capillary pores, which explains why in Fig 15, porosity is anticorrelated with C-S-H or C-H. 

### Application of ANN for estimating porosities based a combination of physical and chemical properties: C-S-H & Angularity (Model II)

It is also of interest to determine whether the extracted features, that explains chemical (C-S-H) and physical properties (Angularity of pores) of cement matrix, are highly correlated with pore volume fraction. For this purpose, C-S-H together with angularity are chosen to be possibly predictive of porosity. Figure 20 represents existence of a strong nonlinear correlation between porosities and C-S-H or angularity. In addition, it was found that increasing porosity would enhance angularity of capillary pores. 

<img src ="images/fig22.JPG" width =1100> 

    Figure 20: Porosity vs. C-S-H or Angularity for both batch1 and 2
  
To evaluate the accuracy of ANN results, RMSE is evaluated for both testing and validation data sets, see Fig 21. As shown in this figure, the RMSE value is continuously decreased by increasing the number of epochs for both sets, while no overfitting of data is observed. 

<img src ="images/fig23.JPG" width =400> 

    Figure 21: Evaluation of RMSE vs. epochs in the second model
    
ANN also facilitates statistical matching estimated versus true porosities of training and testing datasets, which are shown in Fig 22. This figure confirms the relative high accuracy of results, i.e. approximately 70% and 60% for testing and training datasets in spite of having a limited number, i.e. 200, of SEM images. 

<img src ="images/fig24.JPG" width =900> 

    Figure 22: matching porosities for training and testing datasets, second model

Model II is also capable of relating physical as well as chemical properties of cement to its porosity, but with lower accuracy compared with Model I. The reduction in results accuracy could be attributed to the formula introduced in this paper for calculation of angularity. Nonetheless, to the authors knowledge, for the first time in the literature, angularity of pores was found to be correlated with porosity. This phenomenon shall be further explored in the future research.    

### Appllication of CNN for classifying porosity using SEM images (Model III)

As a way of variety, each student tried to deviate a little from the main work. The main work is to build an algorithm that will be able to identify porosity for images from the testing data set. Start writing about porosity, we saw from the explanatory data analysis that the porosity for each batch is normally distributed. Also, from the second plot, it is shown the frequency of porosity within each batch, and the average values of porosity for batch 1 is 18.52% and for batch 2 is 12.17% which are reasonable. The reason behind this explanatory data analysis is to see how porosity distributed among all images in each batch and identify if there is any image that could have unreasonable values. We also figured out that 

![training and testing loss](/loss.PNG)

![training and testing accuracy](/accuracy.PNG)

