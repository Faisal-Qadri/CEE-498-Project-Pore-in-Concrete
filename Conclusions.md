## Conclusions

Based on the present machine learning analysis, the following conclusions could be drawn: 

* ANN was found to be capable of predicting porosity in cement paste matrix by leveraging chemistry of hydrates as well as angularity of pores. 
* The results of ANN revealed that an increase in concentration of C-S-H gel and C-H in cement would probably enhance matrix densification, consequently reducing pore volume fraction locally.
* By doing ANN, it was proved that chemistry of cement alone has the ability to predict porosity of cement with almost 80% accuracy. However, if the physical properties of pores, e.g. angularity, is coupled with cement chemistry, this accuracy would be reduced to 70%.
* CNN is determined to be a powerful technique for classification of porosities based on their volume fraction in SEM images.
* Although the number of input data was limited to 200 SEM images, decent accuracy was achieved using both ANN and CNN. Therefore, a limited number of input data (which is dictated by the difficulty and high cost of imaging) may have little impact on the robustness of both ANN and CNN.

The built models in this project are only the base for further works in the future. These models will be developed further to solve real problems in the infrastructure field. Other information in conjunction with porosity labels will be collected such as freezing and thawing resistance, scaling, thermal cracking and other durability issues. Then, based on these information, a model will be able to predict the remaining service life and the physicochemical properties based on the pore structure characteristics (porosity, tortuosity, connectivity, and pore size distribution), and the chemical compositions within the cement matrix as well. However, it is willing that model will be able to suggest early solutions to rehabilitate infrastructure and prevent further deterioration, which in turn saves money.
