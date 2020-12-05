# Results:


## Exploratory Data Analysis
Extracting features from images that assist us predict porosity is an integral task. 


 ### Estimating Porosity Distribution 

Followed by doing model caliberation, it is now required to estimate distribution of porosities in each batch. For this purpose, histogram of porosites at threshold = 0 is sketched in Fig 10 for both batches using different bandwidth (bins) values. Considering this figure, histograms having smaller bins value, i.e. bins = 10, suggest lognormality of porosities in each batch. 

<img src ="images/fig10.JPG" width =1100> 

    Figure 10: finding distribution of porosities in each batch 
    
However, it is required to determine whether the chosen lognormal distribution is valid. For this reason, a method called probability plot was employed to prove lognormality of distribution. Fig 11 shows a relatively high R-squared value found from the probability plot and validates the distribution.

<img src ="images/fig11.JPG" width =700> 

    Figure 11: porbability plot test of the chosen lognormal distribution

As a way of variety, each student tried to deviate a little from the main work. The main work is to build an algorithm that will be able to identify porosity for images from the testing data set. Start writing about porosity, we saw from the explanatory data analysis that the porosity for each batch is normally distributed. Also, from the second plot, it is shown the frequency of porosity within each batch, and the average values of porosity for batch 1 is 18.52% and for batch 2 is 12.17% which are reasonable. The reason behind this explanatory data analysis is to see how porosity distributed among all images in each batch and identify if there is any image that could have unreasonable values. We also figured out that 

![training and testing loss](/loss.PNG)

![training and testing accuracy](/accuracy.PNG)

