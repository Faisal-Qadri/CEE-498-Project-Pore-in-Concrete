# Methods:

Explantory data analysis was performed as any machine learning project in order to undersatnd what is behind the dataset. The acquired images are grayscale images sizing 256*196 pixels and values ranging from 0 to 255; with pixels around zero representing pores (porosity), and higher pixel values representing hydrated and unhydrated products in gray and white colors. 

Complex model has been built using Convolutional Neural Network (CNN) approach. Having the images from the training set coincided with their labels (porosity values) as the input of the model. This model will be freezed while fetching and processing a previous model performed on a very big data (images). The usual image data set “imagenet” is used as a preprocessed model to let the model train in a complex way to understand and identify images.
Due to having a very limited number of images, we had to divide porosity into categories in order to make it easier to the model to predict for a limited number of outputs (labels). This dividing was done by some of the team members as a way of variety in this project. However, in any real case study, specifing categories will be needed to make it more reasonable to predict physiochemical properties such as freezing and thawing since freezing and thawing behavior for example is changing discretely.

Image augmentation is pretty important in image processing. As we deal with pixels values and shapes, we focused on image flipping and sizing augmentation rather than color augmentation since we deal with grayscale images and pixels values.

sgsfgsfgsd