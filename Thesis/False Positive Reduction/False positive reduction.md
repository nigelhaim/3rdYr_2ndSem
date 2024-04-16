
Cerebral Microbleed mimics are one of the major causes of false positives in automated detection of Cerebral Microbleeds. CMB mimics in SWI or higher field strength MRI become more problematic using methods with higher sensitivity to susceptibility. CMB mimics largely arise in T2*-weighted images to paramagnetic substances other than hemosiderin, including calcifications, iron deposits, or deoxyhemoglobin (Greenberg et al., 2009). The presence of CMB mimics along with algorithmic errors can lead to significant number of false positives (Ferlin et al., 2023). To address these mimics in the differentiation of actual CMBs and their mimics, different approaches was done based on the model's performance and algorithm in detecting the CMB candidate. A comprehensive review of Ferlin et al. (2023) stated that even with the implementation of this stage, certain approaches still have not managed to acquire satisfying quality. 


**Classifiers**

Identified CMB candidates contains features intensity, size, and other complex parameters of a single voxel.  These features with fragments of images are to be input on a classifiers. 

Chen et al. (2015) used SVM that learned representation features from the independent subspace analysis (ISA). Along with the candidate screening through intensity values and compact 3D hierarchal feature extraction on the ISA network, it resulted a high sensitivity rate of 89.44% with an average of 7.7  and 0.9% of false positives per subject and per CMB respectively (Dou et al., 2015). 

**Adjacent slices**

Analysis a sequence of a few adjacent slices based from the features of CMB became essential on the study of Ferlin et al. (2021). They proposed to apply an extra stage where it verifies the ground truth CMB and verification of false-positives as shown in the flowchart of Figure 1. Different configurations of input images are tested to provide information when analyzing the adjacent slices. If the candidate is equal as the features and parameters of the ground truth CMB, therefore the candidate is added to the True positive CMB. This verification was done through Intersection over Union (IOU) of 40%. Specifically if the bounding box of the candidate's adjacent slices contains 40% of the ground truth CMB bounding box, it is considered as a true CMB. Finally duplicates are removed (Ferlin et al., 2021).  Furthermore Ferlin et al. (2021) have also discussed that enlarging the images and providing information from the adjacent slices by input structuring had made significant improvements on the mode's ability to detect CMB. Their study resulted with high precision (89.74%), sensitivity (92.62%), and F1 score (90.84%).

![[Pasted image 20240416093223.png]]
**Figure 1.** Illustrates the post-processing stage of the model by Ferlin et al. (2021)


**2D CNN**

The proposed method of Afzal et al. (2021) proposed that after pre-processing the data through skull stripping and augmentation. This was done since they have discussed that the skull area is one of the main causes for higher false positive results. The CMB and CMB mimic images that were extracted from the SWI samples are augmented to balance the number of each class. 

From the K-means clustering stage that provided the division between microbleed and non-microbleed, the proposed approach was carried out a false-positive reduction step that is before the classification stage. This is done by removing unwanted connected components that depends on the shape and size of the microbleeds. 

Afzal et al. (2021) input the newly false-positive clusters to a transfer-learning classification model. The CNN AlexNet trained on ImageNet data samples was applied that comprises a total of eight layers. This include convolutional and fully connected layers along with the layers a re two max-pooling layers and recurrent linear unit (ReLU). ReLu speeds up the training method and stops the overfitting issue in the classification. They also used ResNet 50 to improve accuracy on SWI images. A residual network with 50 layers. The class-specific layers are transferred with the new last layers therefore the entire network was fine tuned for the SWI data samples. 

It was discussed based on the findings that the k-means clustering algorithm generated four unique clusters and selected the optimum cluster with a lower False positive. Without pre-processing Afzal et al. (2021) had changed some steps from the conventional methodology to reduce false positives. The classification stage relies on these methods. 

The study concluded that ResNet50 and Alexnet along with augmented clustered data has both 97% accuracy. The utilization of two pre-trained CNN models and a k-means clustering approach to reduce false positives became an effective method to achieve high accuracy in detecting microbleeds. 

**Feed-forward and Feed-Backward feature selection**

The goal of the proposed technique of Ghafaryasl et al. (2012) is to distinguish the CMBs from vessels on the base structural analysis in 3D data and to distinguish noisy structures in the image. Similar to the previous methods they include skull-stripping, initial candidate selection, reduction of false-positive using a two layer classification before determining the anatomical location of the CMB seen in Figure 2. Their thesis introduces a semi-automatic detection of cerebral microbleeds in MR images. 

![[Pasted image 20240416133443.png]]
**Figure 2.** The generic system model of Ghafarysal et al. (2012)
 
They stated that CMBs can be distinguished from vessels through the analysis of their structures in the 3D image. CMBs look like spherical shapes in 3D images while vessels have tubular structures. Noisy structures have plate-like patterns (Ghafarysl et al., 2012). They can also be distinguished based on size and intensity. True CMBs have dark structures with low intensity characteristics in the T2*-MR images. Any candidate without containing these parameters are considered vessels. Noisy structures have high intensity regions. These features can only be used on a multi-stage system depending on the architecture's design. 

In features extraction, this stage describes how the model distinguishes CMBs from false-positive candidates. They used as Feed-Forward features selection method. Through this method they stated that uniform distribution, triangular distribution, beta distribution and gaussian distribution are calculation techniques used in this area. The three key features are extracted on this stage. Geometric-based features contains the size and shape features gained from the binary images. Intensity-based features holds the intensity values of the candidates from the T2*-MRI and Proton Density sequences. Scale-Space representation for feature extraction is a framework that represent the image at multiple scales to find the relevant scale. Through the second order derivative matrix also known as the Hessian matrix, it is used to distinguish the difference of CMB from non-CMB structures. This is used to detect Blob structures in the image. They also used Multiscale vessel enhancement to distinguish spherical structures from tubular or plate-like structures. To detect the strongest blobs and vessel-like structures, they used automatic scale selection. 

Partial Least Square Mapping is also applied as a feature extraction. The linear regression model projected both the predicted and observable variables to a new space. The covariance matrix of the predicted variables are also considered. 

After extracting the features different classification methods were used to classify the mimics and CMBs. Support vector classifiers that involves optimizing the convex function. The hypothesis dependency on the data through the support vectors makes the model more understandable for the observer. Linear Discriminant Classifier models each class of data by a Gaussian model, Quadratic Discriminant Classifier which the classes has their, and Parzen that uses a kernel as a weighting function for estimating the class conditional densities. 

To analyze the results Ghafaryasl et al. (2012) used Free receiver Operating Characteristic (FROC). A graph that is used as the criterion for selecting the best performing feature selection method and classifier. 

Their study concluded that despite the proposed model contains some False positives, it helps the radiologist to facilitate manual segmentation. It can be used to examine and distinguish CMBs from false positives.  The sensitivity for CMB detection was 90% with, on average, 4 false-positives per subject. 



Ferlin, Maria, et al. “Exploring the Landscape of Automatic Cerebral Microbleed Detection: A Comprehensive Review of Algorithms, Current Trends, and Future Challenges.” _Expert Systems with Applications_, vol. 232, Dec. 2023, p. 120655. _ScienceDirect_, https://doi.org/10.1016/j.eswa.2023.120655.

Greenberg, Steven M., et al. “Cerebral Microbleeds: A Field Guide to Their Detection and Interpretation.” _Lancet Neurology_, vol. 8, no. 2, Feb. 2009, pp. 165–74. _PubMed Central_, https://doi.org/10.1016/S1474-4422(09)70013-4.

Qi Dou, null, Hao Chen, null, Lequan Yu, null, Lin Shi, null, Defeng Wang, null, Mok, V. C., & Pheng Ann Heng, null. (2015). Automatic cerebral microbleeds detection from MR images via Independent Subspace Analysis based hierarchical features. _Annual International Conference of the IEEE Engineering in Medicine and Biology Society. IEEE Engineering in Medicine and Biology Society. Annual International Conference_, _2015_, 7933–7936. https://doi.org/10.1109/EMBC.2015.7320232


Ghafaryasl, B., van der Lijn, F., Poels, M., Vrooman, H., Ikram, M. A., Niessen, W. J., van der Lugt, A., Vernooij, M., & de Bruijne, M. (2012). A computer aided detection system for cerebral microbleeds in brain MRI. _2012 9th IEEE International Symposium on Biomedical Imaging (ISBI)_, 138–141. https://doi.org/10.1109/ISBI.2012.6235503

Afzal, S., Khan, I., & Lee, J. (2021). A transfer learning-based approach to detect cerebral microbleeds. _Computers, Materials & Continua_, _71_(1), 1903–1923. https://doi.org/10.32604/cmc.2022.021930




| Title                                                                                                                                           | Author/s                                                                         | Abstract                                                                                                                                                                                                                                                                                         | Conclusion                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| Automatic cerebral microbleeds detection from MR images via Independent Subspace Analysis based hierarchical features                           | Dou, Q. Chen, H., Yu, L., Shi, L., Wang, D., Mok, V., Heng, P. (2015)            | Their approach detects Cerebral Microbleeds in three stages. The first stage is where the candidates are screened, then 3D hierarchal features are extracted through convolutional Independent Subspace Analysis and the false positive candidates are removed through a Support Vector Machine, | 89.44% of sensitivity was achieved on 19 subjects with 161 CMBs, 7.7 average and 0.9 false positive per subject and per CMB. |
| Exploring the landscape of automatic cerebral microbleed detection: A comprehensive review of algorithms, current trends, and future challenges | Ferlin, M., Klawikowska, Z., Grochowski, M., Grzywińka, M., Szurowska, E. (2023) | Provided a review to all published studies available up until December 2023 that focused on Automated Cerebral Microbleed Detection                                                                                                                                                              | Their findings would serve as a                                                                                              |
