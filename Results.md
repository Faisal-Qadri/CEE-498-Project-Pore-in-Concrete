# Results:


## Exploratory Data Analysis

 ### Estimating Porosity Distribution 

Followed by doing model caliberation, it is now required to estimate distribution of porosities in each batch. For this purpose, histogram of porosites at threshold = 0 is sketched in Fig 10 for both batches using different bandwidth (bins) values. Considering this figure, histograms having smaller bins value, i.e. bins = 10, suggest lognormality of porosities in each batch. 

<img src ="images/fig10.JPG" width =1100> 

    Figure 10: finding distribution of porosities in each batch 
    
However, to determine whether the chosen lognormal distribution is valid, a method called probability plot was employed to prove lognormality of the distribution. Fig 11 shows a relatively high R-squared value found from the probability plot and validates the distribution.

<img src ="images/fig11.JPG" width =700> 

    Figure 11: porbability plot test of lognormality
    
By proving the lognormality of porosityies in both batch 1 and 2, it is of interest to determine whether these two distribution matches at line y=x. Accordingly, the two lognormal distributions were plotted against on another, and shows a high affinity of, see Fig 12. It is worth noting that any point placed prior to the lognormal peak, specified with a dashed-line was eleminared from the matching procedure.  

<img src ="images/fig12.JPG" width =700> 

    Figure 12: matching lognormal distribution of porosities of batch1 and 2

## Feature Engineering

Using EDA, different features for characterizing porosity are extracted and shown in Fig 13. However, is a required task to determine whether these features are capable of estimating porosity 

<img src ="images/fig17.JPG" width =900> 

    Figure 13: extracting features (physical and chemical) from SEM images
    
Considering Fig 14, only Calcium Silicate Hydrate (C-S-H), Portlandite (C-H), and Angularity features have strong correlation, i.e. either positive or negative, with porosity. Consequently, these feature are likely to be predictive of pore volume fraction for use in Neural Network.  

<img src ="images/fig18.JPG" width =900> 

    Figure 14: SNS Heatmap of correlations between features extracted from image analysis

### Appllication of ANN for estimating porosity based on C-S-H & C-H

In this step, extracted features corresponding to chemical properties of cement and highly correlred to pore volume fraction, i.e C-S-H and C-H, are selected to be predicitve of porosity. Considering Fig 15, it could be realized that the corrlation between porosity and C-S-H or C-H is not linear. Also, increasing porosity would result in a reduction in both C-S-H and C-H values. 

<img src ="images/fig19.JPG" width =1100> 

    Figure 15: Porosity vs. C-S-H or C-H for both batch1 and 2

To do ANN, training dataset has to be fed into the model. Fig 16 illusterates the features combined from batch 1 and 2, having 200 rows in total. 

<img src ="images/fig25.JPG" width =600> 

    Figure 16: Training dataset used for ANN

Similarly, the testing dataset is fed into the model, which is used for validating the employed ANN. Fig 17 illusterates selected features from batch3, which has 100 rows in total. 

<img src ="images/fig26.JPG" width =600> 

    Figure 17: Testing dataset used for ANN
    
To evaluate the accuracy of ANN results, RMSE is evaulated for both testing and validation data sets, see Fig 18. As shown in this figure, the RMSE value is decreasing by increasing the number of epochs for both sets, while no overfitting of data is observed. 

<img src ="images/fig20.JPG" width =600> 

    Figure 18: Evaluation of RMSE vs. epochs 
    

    

### Appllication of ANN for estimating porosity based on C-S-H & Angularity

To do ANN, training dataset has to be fed in the model. Fig 18 illustrates the features combined from batch 1 and 2, having 200 rows in total. 

<img src ="images/fig20.JPG" width =400> 

    Figure 17: Porosity vs. C-S-H or C-H for both batch 1 and 2
    
In the next step, the porosities for the training and testing batches are estimated and compared with the exact, i.e. true, porosities. Fig 19 shows matched porosites, i.e. estimated vs. exact, found by ANN. 

<img src ="images/fig21.JPG" width =900> 

    Figure 17: matching porosities for training asd testing datasets.
    
### Appllication of CNN for classifying porosity using SEM images


As a way of variety, each student tried to deviate a little from the main work. The main work is to build an algorithm that will be able to identify porosity for images from the testing data set. Start writing about porosity, we saw from the explanatory data analysis that the porosity for each batch is normally distributed. Also, from the second plot, it is shown the frequency of porosity within each batch, and the average values of porosity for batch 1 is 18.52% and for batch 2 is 12.17% which are reasonable. The reason behind this explanatory data analysis is to see how porosity distributed among all images in each batch and identify if there is any image that could have unreasonable values. We also figured out that 

![training and testing loss](/loss.PNG)

![training and testing accuracy](/accuracy.PNG)

