# Introduction

## Hossein's version 

Durability of concrete structures against gradual ingress of deleterious liquids is mainly controlled by porosity and pore structure of cement paste matrix1. There are multiple factors that affect general properties of capillary pore structure in concrete, which include curing regimes, cementitious materials contents, and water-to-cementitious materials ratios1,2. Therefore, it is necessary to precisely measure and characterize pore structure in concrete to determine the optimum concrete curing conditions and mix proportions. Over the past few decades, mercury intrusion porosimeter (MIP) test, has been used to measure porosity and pore size distribution in cement-based composites. In this method, using relatively high pressure, mercury is injected into the pore spaces of the matrix to determine porosity and its structure. MIP test, with an ability to measure pore sizes in the range of 0.006–500 µm, is typically performed on a small oven-dried cement-composite specimen and mercury is gradually applied on the desired surface1. However, it has been reported that, cement matrix surface tension as well as mercury contact angle with cement pore wall affects the accuracy of MIP
measurements3.

To address the uncertainty of MIP results, image analysis method is recently developed to directly measure paste matrix porosity. In this technique, backscattered scanning electron microscopy (SEM) images of polished impregnated epoxy concrete surface is captured and analyzed using ImageJ commercial software1. To go further, ImageJ software quantifies the total area of pores using a grayscale thresholded image. However, as shown in Fig. 1, this commercial software solely provides total porosity of the matrix and lacks the ability to characterize porosity1

In addition, comparing the total porosity of paste matrices measured by MIP method with that of ImageJ method revealed that porosity is underestimated in the former technique (see Fig. 2). In fact, in contrary to MIP, Image analysis is capable of measuring both connected and disconnected capillary pores, and hence gives a more realistic picture of paste matrix porosity1.





## Faisal's version
Concrete durability is intimately linked with cement paste microstructure, specifically; porosity within the cement paste. Pore structure is mainly divided into two main categories: capillary and gel pores and they range from few millimeters into few nano-meters having 70-90% of total porosity in the nano scale. Using machine learning/image processing is useful to identify several physiochemial properties that matter concrete durability. 

There are two broad ways to measure porosity in concrete: Mercury Introsion Porosimetery (MIP), and using imaging techniques focusing on micro and nano X-ray Computed Tomography (XCT). Usually, MIP enables us to detect porosity up to nano scale, but with XCT is pretty difficult to reach that accuracy. However, the former technique needs speciemn preparation and it is hard to conduct, while the latter technique is easy to conduct since it does not need and specimen preparation, but costs a lot of money.

Collecting images with porosity detected by MIP is the first step to provide a usful dataset for future work. However, porosity for images collected by other means such as XCT or scanning electron microscoy will be predicted using machine learning approach which saves time, effort, and money. Secondly, with more information collected such as freezing and thawing resistance, scaling, thermal cracking and other durability issues will be predicted based on the microstructure of any cement paste or even concrete. Moreover, pore structure such as connectivity and tortuosity can be predicted using machine learning/Image processing approach. 

In this project, due to the limited information in the data sets, porosity-related images were only collected and the project was conducted just to predict the porosity for images from a testing dataset. The training set has 200 images with their corresponding porosity values, and the testing set has only 100 images.

dasdasfas
