	
The theoretical framework incorporates the outline of different theories  and concepts of previous studies to automate microbleed detection. This section provides an overview on studies of different concepts that served as the foundation of our proposed methodology. Figure 1 illustrates the techniques and methods used on their studies as part of their architecture in detecting microbleeds. It overviews Localization, Classification, Attention Mechanism, and Global attention. 

![[Blank diagram (2).png]]

*Figure 1. Theoretical Framework of the Study*
	
## Localized Regions

Localization is the detection of a specific region of Interest (ROI) in an image. Interpretation tasks are dependent on this stage there fore it is a critical prerequisite to all object detection task (Alaskar et al., 2022). It is also used on other studies such as brain tumors conducted by Li et al. (2021). 
 
Kim et al. (2023) stated that localization is not only limited on determining CMBs but also reduces False positive results through the use of anatomical information. Another study of Chen et al. (2015) proposed a method where one of the three steps is the localization of CMB candidates with high sensitivity. They analyzed these scans following a production of a binary image through setting a statistical method. Each candidate's center is the centroid of a 3D growing connected component.

Other studies conducted by Yan et al. (2023) that applied Contrastive learning frameworks that were integrated in the localized region. This is done to enhance self-supervised models for segmentation with limited annotations. 
## Attention mechacnism

Inspired by how a human vision works, attention mechanism works through dynamically focuses on a subset of the given visual field. This long-time developing mechanism, it had become a new hope for advanced models. A survey conducted by Xie et al. (2023) stated that the application of attention mechanisms have gained a steady annual growth from 2017 to 2023. This is because of hierarchical feature learning capabilities. It serves as a plug-in sublayer into the convolution block. This plug-in can be applied on the bottleneck. 

**Spatial attention** 
Through assigning importance scores to different spatial regions in the feature map, spatial attention helps identify important regions in an image.  On the study of Oktay et al. (2018), to obtain the gating coefficient to build spatial attention weight map, the attention gates utilize additive attention between the input. This was followed by a gate signal collected at a course scale. It is widely used and adapted in medical image segmentation (Duran et al. 2022). Spatial attentions are also specifically modified to solve problems like blurred boundaries, Zhang et al. (2019) created edge attention and (Li et al. 2020d) utilized the shape as a prior knowledge in guiding shape attention. 

**Temporal attention**
Proposes the global-local representation. When the data has a temporal dimension, it is usually seen as a dynamic timeframe selection mechanism. Videos can be a great example (Li et al., 2019). Instead of self-attention with a local and global branches in capturing complex temporal relationships, adopting an adaptive kernel is used to propose the temporal adaptive module (TAM) by Liu et al. (2021d). It can be applied in multi-frame clinical images or videos.


A good example of combined Spatial attention and Temporal attention is the study of Woo et al. (2018). They proposed CBAM that calculates channel and spatial attention in which the channel attention module utilizes two parallel branches via max-pool, and avg-pool operations while a convolution layer with a larger kernel is applied in spatial attention module to generate the attention map. 

The multi-head self attention and feedforward layers are the two main sub-layers of the basic Transformer layer (Vaswani et al. (2017)). Through the application of scaled dot-product attention to model interactions between all elements of a sequence, Self attention can be described by equation (1). Along with multi-head attention mechanism which where the complex relationships beetween entities are captured. This is done through the attention layers focus on different subspace representations. 

![[Pasted image 20240419095540.png]]

$Equation II$  With the given input vector and the head number $h$, it is transformed into three separate groups of vectors. Each vector contnains h vectors. This describes the Self attention mechanism. 

On the other hand feedforward layers is a two-layer feedforward neural network to the attended input. With a ReLU activation function in between two linear transformations. The model has the ability to learn more complex representations and allows the model to transform the attended input into a different space. 

**Vision Transformer (ViT)**

Dosovitsky et al. (2020) applied Vision transformer that introduces transformer encoder on the classification of images through computer vision. The transformer models is applied on a sequence of fixed-size of image patches that are flattened as vectors. Each of them are linearly embedded, along with position embeddings. The sequence of vectors are fed into the input of the transformer encoder. It learns through embedding where the output of the Transformer encoder is a representation in classification performance. One of the standard approach on vision transformer is through adding an extra learnable "classification token" to the sequence is used. Vision transformers had demonstrated effectiveness in Transformer architecture for computer vision tasks. 

**DEtection TRansformer (DETR)**

The proposed methodology of DETR of Carion et al. (2020) for object detection is a transformer based model that treats detection as a direct set prediction problem. It predicts all objects simultaneously through an encoder-decoder architecture based on the Transformer. Another variation of DETR of Zhu et al. (2020) proposes the mitigation of high computational cost for the original DETR. 

**SEgmentation TRansfomer (SETR)**
Mitigating the Transformer to image segmentation tasks. The three employment for pixel-wise classification are naive up-sampling, progressive up-sampling, and multi-level feature aggregation (Zhen et al. 2021).

**Swin Transformer**
As a plug-in module or the basic blocks of the model, it is usually introduced into the U-Net architecture. It is efficient to capture global image features. It also preserves fine-grained spatial information. It achieved good results on several benchmark datasets and demonstrates its effectiveness on vision tasks through its hierarchical design. 


## Global Attention

Global attention captures overarching patterns and structures of the image's global information. It allows the model to consider the fusion of local details and global context. Li et al (2024) introduced Global and Local Attention Mechanism that provides an in-depth method for input images. 

**GALDET**

Li et al. (2024) introduced GALDET a new module that enhances performance and flexibility in remote sensing target detection models. It focuses on enhancing feature extraction capability through utilizing the CGAL module that enables the model to be more effective in detecting and parse fine-grained information by small targets. 


**TPE-Det**

The proposed model of Lee et al. (2022) is an ent-to-end CMB detection network that utilizes 3D information. Three EfficientDet D3 are trained in three MRI planes of the brain. IT detects CMBs through finding the consistent coordinates of all three planes where the CMB is present. 


## Classification

Leaonard (2019) stated that classification of features in images is an important reserach direction in computer vision. Through gradient descent methods, CNN can learn image features and classifies detected objects. 

**CMB-Hunt**

Suwalska et al. (2022) proposed a Deep Neural network where it classifies True CMB and Mimics through susceptibility-weighted imaging data (SWI) and radiomic-type numerical features. The network consists of the Region of interest input layer and the Numeric features input layer. 

**IoMT framework**

Utilized the U-Net architecture where if down samples to produce activation maps or a set of image features. Compromised of convolution layers the decoder helped up-sampling the images to generate segmented results. The classifies each pixel as either CMB or non-CMB class. It also could give patch-level methods that suffer from imbalance data an advantage (Ali et al., 2019).

## Pre-processing 

Raw data is usually not ready for correct inferences. Pre-processing is a methodology that converts raw, messy or noisy data to a well organized manner before applying high level machine learning algorithms or any advanced methods for data analysis (Khalid et al., 2020).

**Skull Stripping**

Brain extraction or Skull stripping is the process of removing the skull and the background from the MRI image. Smith (2002) created a method named Brain Extraction Tool (BET) that applies a set of locally adaptive model forces to fit the brain's surface. As seen on Figure 1, stated that it is clear from the figure that the skull contains many false positives (Afzal et al., 2022).


![[Pasted image 20240422183719.png]]
**Figure 2. A graphical representation of (Afzal et al., 2022) of skull-part removal from the cerebrum**

**Normalization**

Medical images tend to be corrupted by noise and artifacts. It is a the operation of pixel value rescaling into the range of (0,1) or (-1,1) (Ferlin et al., 2023). Despite of numerous studies have been applied and being effective in this process, this technique can be tedious, and often changes a lot of content in the image (Kociolek et al., 2020)


Alaskar, H., Hussain, A., Almaslukh, B., Vaiyapuri, T., Sbai, Z., & Dubey, A. K. (2022). Deep learning approaches for automatic localization in medical images. _Computational Intelligence and Neuroscience_, _2022_, 6347307. https://doi.org/10.1155/2022/6347307

Chen, H., Yu, L., Dou, Q., Shi, L., Mok, V. C. T., & Heng, P. A. (2015). Automatic detection of cerebral microbleeds via deep learning based 3D feature representation. _2015 IEEE 12th International Symposium on Biomedical Imaging (ISBI)_, 764–767. https://doi.org/10.1109/ISBI.2015.7163984

Chesebro, A. G., Amarante, E., Lao, P. J., Meier, I. B., Mayeux, R., & Brickman, A. M. (2021). Automated detection of cerebral microbleeds on T2*-weighted MRI. _Scientific Reports_, _11_(1), 4004. https://doi.org/10.1038/s41598-021-83607-0

Kim, J.-H., Noh, Y., Lee, H., Lee, S., Kim, W.-R., Kang, K. M., Kim, E. Y., Al-masni, M. A., & Kim, D.-H. (2023). _Toward automated detection of microbleeds with anatomical scale localization: A complete clinical diagnosis support using deep learning_ (arXiv:2306.13020). arXiv. https://doi.org/10.48550/arXiv.2306.13020

Yan, X., Naushad, J., You, C., Tang, H., Sun, S., Han, K., Ma, H., Duncan, J., & Xie, X. (2023). _Localized region contrast for enhancing self-supervised learning in medical image segmentation_ (arXiv:2304.03406). arXiv. https://doi.org/10.48550/arXiv.2304.03406

Soydaner, D. (2022). Attention mechanism in neural networks: Where it comes and where it goes. _Neural Computing and Applications_, _34_(16), 13371–13385. https://doi.org/10.1007/s00521-022-07366-3

Lee, H., Kim, J., Lee, S., Jung, K., Kim, W., Noh, Y., Kim, E. Y., Kang, K. M., Sohn, C., Lee, D. Y., Al‐masni, M. A., & Kim, D. (2023). Detection of Cerebral Microbleeds in MR Images Using a Single‐Stage Triplanar Ensemble Detection Network (Tpe‐det). _Journal of Magnetic Resonance Imaging_, _58_(1), 272–283. https://doi.org/10.1002/jmri.28487

Suwalska, A., Wang, Y., Yuan, Z., Jiang, Y., Zhu, D., Chen, J., Cui, M., Chen, X., Suo, C., & Polanska, J. (2022). CMB-HUNT: Automatic detection of cerebral microbleeds using a deep neural network. _Computers in Biology and Medicine_, _151_, 106233. https://doi.org/10.1016/j.compbiomed.2022.106233

Leonard, J. K. (2019). Image classification and object detection algorithm based on convolutional neural network. _Science Insights_, _31_(1), 85–100. https://doi.org/10.15354/si.19.re117

Ali, Z., Naz, S., Yasmin, S., Bukhari, M., & Kim, M. (2023). Deep learning-assisted IoMT framework for cerebral microbleed detection. _Heliyon_, _9_(12), e22879. https://doi.org/10.1016/j.heliyon.2023.e22879


_Data preprocessing—An overview | sciencedirect topics_. (n.d.). Retrieved April 22, 2024, from https://www.sciencedirect.com/topics/engineering/data-preprocessing


Kociołek, M., Strzelecki, M., & Obuchowicz, R. (2020). Does image normalization and intensity resolution impact texture classification? _Computerized Medical Imaging and Graphics_, _81_, 101716. https://doi.org/10.1016/j.compmedimag.2020.101716