
# Methods:

## Exploratory Data Analysis (EDA)
Doing exploratory data analysis (EDA) is a required task for characterizing porosity. The input data consist of only two columns, images (IDs) and their corresponding porosity were calculated using ImageJ commercial software. The exact porosities for both batches, i.e. 1 and 2, are read and shown in Table 1:

                 Table 1: importing Tabular Data
<img src ="images/fig1.JPG" width =500>


As shown in Table 1, porsoties are variable from 0 to 100 percent. In addition, the image IDs column are used to match images with their labels, i.e. porosity. It is worth noting that each Batch 1 and 2 has 100 images, which will be for porosity characterization. The first three images chosen from batch1 are shown in Fig 1:

            Figure 1: importing first three images from batch1
<img src ="images/fig2.JPG" width =700>


The input grayscale images are all having 256*196 pixels with grayscale values ranging from 0 to 255; dark pixels are having threshold values close to zero , and pixels with higher thershold values are brighter and represents cement hydrated products in gray and white colors. Image processing plays an integral role for understanding the general characterestics of capillary pore system. 



Complex model has been built using Convolutional Neural Network (CNN) approach. Having the images from the training set coincided with their labels (porosity values) as the input of the model. This model will be freezed while fetching and processing a previous model performed on a very big data (images). The usual image data set “imagenet” is used as a preprocessed model to let the model train in a complex way to understand and identify images.
Due to having a very limited number of images, we had to divide porosity into categories in order to make it easier to the model to predict for a limited number of outputs (labels). This dividing was done by some of the team members as a way of variety in this project. However, in any real case study, specifing categories will be needed to make it more reasonable to predict physiochemical properties such as freezing and thawing since freezing and thawing behavior for example is changing discretely.

Image augmentation is pretty important in image processing. As we deal with pixels values and shapes, we focused on image flipping and sizing augmentation rather than color augmentation since we deal with grayscale images and pixels values.

let's write
