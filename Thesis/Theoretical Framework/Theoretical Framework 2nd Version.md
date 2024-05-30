**Interpolation**

The theoretical framework incorporates the outline of different theories and concepts of previous studies to automate microbleed detection. This section provides an overview of studies of different concepts that served as the foundation of our proposed methodology. Figure 1.3.1 illustrates the techniques and methods used in their studies as part of their architecture for detecting microbleeds. It overviews Localization, Classification, Attention Mechanism, and Global Attention.

**![](https://lh7-us.googleusercontent.com/BYoTq7or7ih1PHMEZqVg7WHIkasrxoS_Bg5sQYumXgX4ftebzevqdiPWr32_JsnLTeq7gnX9-5c7Xx0qsQfsXZ076sdigmaf1gWyu_MShJUijM_wYg4cJ0HqOUZAVxpZv2wU6Hs9PkOPPCU8yz9kiQQ)**



Figure 1.3.1 Theoretical Framework Diagram

### Localization

Localization detects a specific region of interest (ROI) in an image. Interpretation tasks depend on this stage; therefore, it is a critical prerequisite for all object detection tasks (Alaskar et al., 2022). It is also used in studies of brain tumors, such as the study by Li et al. (2021). 

Kim et al. (2023) stated that localization is not only limited to determining CMBs but also reduces false positive results through anatomical information. Another study by Chen et al. (2015) proposed a method where one of the three steps is the localization of CMB candidates with high sensitivity. They analyzed these scans following the production of a binary image through a statistical method. Each candidate's center is the centroid of a 3D growing connected component.

**Region Proposal Network**

Introduced by Ren et al. (2016) Region Proposal Networks (RPN) shares full-image convolutional features with the detection network, it enables region proposal with free of cost on memory. It is a convolutional network that predicts object bounds and objects scores at each position simultaneously. Their proposal shares convolutional layers with a small marginal cost for computing time. 

Kim et al., (2023) integrated RPN and Fast R-CNN into a single network that shares their convolutional features with attention mechanisms. RPN is responsible for instructing the unified network what location to look. They concluded that RPN is an efficient and accurate that shares convolutional features. It improves region proposal quality and the overall accuracy of their model. 

Other studies conducted by Yan et al. (2023) that applied Contrastive learning frameworks that were integrated in the localized region. This is done to enhance self-supervised models for segmentation with limited annotations. 
### Attention Mechanism

Inspired by how a human vision works, the attention mechanism works by dynamically focusing on a subset of the given visual field. This long-time developing mechanism has become a new hope for advanced models. A survey by Xie et al. (2023) stated that the application of attention mechanisms has gained a steady annual growth from 2017 to 2023. This is because of hierarchical feature learning capabilities. It serves as a plug-in sublayer into the convolution block.

**Vision Transformer (ViT)**

Dosovitsky et al. (2020) applied Vision transformer that introduces transformer encoder on the classification of images through computer vision. The transformer model is applied on a sequence of fixed-size image patches that are flattened as vectors. Each of them are linearly embedded, along with position embeddings. The sequence of vectors are fed into the input of the transformer encoder. It learns through embedding where the output of the Transformer encoder is a representation in classification performance. One of the standard approaches on vision transformers is through adding an extra learnable "classification token" to the sequence. Vision transformers had demonstrated effectiveness in Transformer architecture for computer vision tasks. 

**Global Context**
Extracting the global understanding of an image is the aim of capturing long-range dependency. It provides a good benefit to different recognition tasks on media type classification, object detection and segmentation. (Cao et al., 2019). Introduced by Cao et al. (2019) named the global context provides the benefits of the effective modeling on long-range dependency along with the simplified non-local block with effective modeling with lightweight computation.

It is used by Bouget et al., (2021) on the segmentation of Meningioma on T1-Weighted images. They discussed that global context along with spatial relationships helps models to discriminate between contrast-enhanced meningiomas and bright anatomical structures in the brain. Their study concluded that leveraging the use of global context from a 3D MRI volume provided the best performance even with a limited memory in the GPU. 
### Classification
 

Leonard (2019) stated that classifying image features is an important research direction in computer vision. CNN can learn image features and classify detected objects through gradient descent methods.

### Preprocessing
Raw data is usually not ready for correct inferences. Pre-processing is a methodology that converts raw, messy or noisy data to a well organized manner before applying high level machine learning algorithms or any advanced methods for data analysis (Khalid et al., 2020).

**Skull Stripping**
Brain extraction or Skull stripping is the process of removing the skull and the background from the MRI image. Smith (2002) created a method named Brain Extraction Tool (BET) that applies a set of locally adaptive model forces to fit the brain's surface. As seen on Figure 1.3.2, it is clear from the figure that the skull contains many false positives (Afzal et al., 2022).

![](https://lh7-us.googleusercontent.com/iTsp45L6Bkb89uXw9MsEA0d5Xl7RSgwJIvK8DSaGaFNVmZDXaUPufNZ6uMWzmBlykBNvGDuP_2i1XVC4JpMX6VRsJJmOoLOh0qswPcX2XVKvLM7kdXt4MTqsYRFk9jxmiaPoXTzbgZeS3UXrK4kkFgI)

Figure 1.3.2 Skull-part removal from the cerebrum

  

**Normalization**
Medical images tend to be corrupted by noise and artifacts. It is the operation of pixel value rescaling into the range of (0,1) or (-1,1) (Ferlin et al., 2023). Despite of numerous studies have been applied and being effective in this process, this technique can be tedious, and often changes a lot of content in the image (Kociolek et al., 2020)

**Interpolation**

To further improve segmentation one of the default operations in preprocessing of medical images is interpolation. The intensity-based registration method is one of the important registration methods (Mahmoudzadeh & Kashou, 2013). It also improves the resolution of images.  Mahmoudzadeh & Kashou (2013) concludes that it could play a critical role in the improvement and deterioration of the quality. Assessing the technique is crucial to avoid interpolation error. 


Bouget, David, et al. “Fast Meningioma Segmentation in T1-Weighted Magnetic Resonance Imaging Volumes Using a Lightweight 3D Deep Learning Architecture.” _Journal of Medical Imaging_, vol. 8, no. 2, Mar. 2021, p. 024002. _PubMed Central_, https://doi.org/10.1117/1.JMI.8.2.024002.

Cao, Yue, et al. _GCNet: Non-Local Networks Meet Squeeze-Excitation Networks and Beyond_. 1, arXiv:1904.11492, arXiv, 25 Apr. 2019. _arXiv.org_, https://doi.org/10.48550/arXiv.1904.11492.


Ren, Shaoqing, et al. _Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks_. arXiv:1506.01497, arXiv, 6 Jan. 2016. _arXiv.org_, https://doi.org/10.48550/arXiv.1506.01497.

Mahmoudzadeh, A. P., & Kashou, N. H. (2013). Evaluation of interpolation effects on upsampling and accuracy of cost functions-based optimized automatic image registration. _International Journal of Biomedical Imaging_, _2013_, 395915. https://doi.org/10.1155/2013/395915