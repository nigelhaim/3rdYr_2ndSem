Ferlin, M., Klawikowska, Z., Grochowski, M., Grzywińska, M., & Szurowska, E. (2023). Exploring the landscape of automatic cerebral 
	microbleed detection: A comprehensive review of algorithms, current trends, and future challenges. _Expert Systems with Applications_, _232_, 120655. https://doi.org/10.1016/j.eswa.2023.120655

### Pre processing 

**Bias Field Correction**
- is the operation that reduces negative influence of the bias field, which is an undesired artifact in most MRI images, especially old ones. 
- It can also be called intensity inhomogeneity correction. 
**Skull stripping**
- to obtain binary masks of the brain tissue from MR magnitude images and applied them to SWI and phase images.
- is an operation of removing the skull and background from the image, leaving only the brain.
**Normalization**
- is a typical operation of rescaling the pixel values into range (0, 1) or (−1, 1). This enables bias reduction in the next stages of system synthesis.
**Standardization**
- is an equally common operation as normalization and involves subtraction of mean value of pixels and division by the standard deviation of them
**Padding**
- is an artificial size change by the addition of a black frame to obtain a desired image size without applying resize
**Image cut** 
- is a common operation performed to simplify the de- tection task. It involves image partitioning into smaller components and feeding them into the classifier. It might be performed using the sliding neighborhood processing (SNP) technique to produce smaller fragments of the original image.
**Inversion**
- s the operation that consists of swapping intensity values in relation to the center of the intensity interval 
- Selective tissue supression possible 
- Twice the sensitivity to T1 Images
- Added contrast to T1 and T2 Images 

### Approaches in training the models 
- In the domain of CMB detection, various approaches were used, such as artificial neural network which consist of a sum of inputs multiplied by weights assigned in the training process,
- back-propagation neural networks (BPNNs) that is ANNs extension with the information about the error,
- sparse auto-encoder (SAE) which is a neural network consisting of an encoder and decoder with the additional sparsity penalty algorithm
- Occasionally, the detection task was replaced by classifying small fragments of an image using either CNN or ResNet50
- **CNN**
	- consists of a number of feed-forward convolutional layers, where the features are extracted by performing a convolution between input data and convolutional filters.
	- Consecutive convolution layers are interspersed by pooling layers that extract the most important features.
- An interesting approach is a replacement of a fully-connected layer by Extreme Learning Machine (Huang et al., 2006), which is much more efficient 
- In the context of pre-trained general-purpose neural networks, various commonly-known architectures have been utilized, including AlexNet, ResNet50, Faster-RCNN, VGG, U-Net, YOLOv2, DenseNet 201 or SSD with the modification of feature enhancement.
- 3D CNN has potential in medical imaging but do not exceed preformance on 2D CNN 

### Candidate Verification 
- To mitigate the issue of false positives 
- Manual Radiologist verification 
	- BOMBS 
	- MARS 
- Then, the features of CMBs together with the previously prepared fragments of images were passed to the classifier. A lot of classifiers were tested, including Support Vector Machine (SVM), linear criterion classifier (LDC), quadratic discriminant classifier (QDC) and Random Forrest Classifier (RFC)
- Moreover, there were also other methods to define CMB features to eliminate false positives, for instance, 2D CNN, 3D ISA network, 3D Radon Transform or feed-forward feature selection (FFFS). In some cases, thresholds of geometric features were set, and on this ground, the classification was performed.
- Another strategy at this stage was to use a previously generated CSF mask to distinguish a real CMB from vessels, and a WM mask to include the information about the location of potential microbleed
- . In addition, there was an algorithm used to investigate the overlap between predictions from adjacent slices. It enabled not only the removal of false-positive predictions that were in fact a ground truth, although labeled in the adjacent slice but also helped find a real CMB that was detected in the adjacent slice in spite of the previous false-negative prediction
- 