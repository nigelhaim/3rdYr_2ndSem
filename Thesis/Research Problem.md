
## Detection of Cerebral Microbleeds in MR Images Using a Single-Stage Triplanar Ensemble Detection Network (TPE-Det)

### Points
**General Overview**
- Eliminating the need for the two-stage approach
- Leveraged 3D information by assembling 2D networks on three different planes 

**Data information**
- Dataset 1 - 0.5 x 0.5 x 2.0 mm$^3$
- Dataset 2 - 0.5 x 0.5 x 3.0 mm$^3$

**Data Preprocessing**
- Brain Extraction Tool used to obtain binary masks of the brain tissue from MR magnitude images. 
- Volumetric datum of Dataset 2 was interpolated so it has the same slice thickness as Dataset 1.
	- Cropped from the size of 512 x 448 x 72 → 360 x 360 x 72 
	- Discarding the empty background fom the top, bottom, right and lift sides.
	- **Resized** to 360 x 360 x 360 to ensure the images to be square 
- The contrast of the SWI images was stretched by mapping the pixel intensity values to new wider range such that the image’s histogram was linearly scaled, and the values were evenly distributed from maximum to minimum (eg 255 to 0 on an 8-Bit image).

**Proposeed Detection Network**
- Each detection network of the TPE-Det is based on EfficientDet.
- EfficientDet can simultaneously detect the location of multiple CMBs, providing coordinates of bounding boxes with confidence scores as output.
- Independently trained on the three axis images 

**Limitations**
- Each detection model cannot help being biased toward its dataset's specific parameters. 
- It is expected that an entirely different resolution from DS1 would substantially degrade the detection performance of TPE-Det, which was trained on DS1 only.

### Personal Insights 

Yung pinaka main problm talaga dito is na manipulate nila yung Dataset 2 na gawing malapit sa Dataset 1. Resizing and binago yung contrast. Pwed maglead sa artifacts yung resizing. Yung pagmanipulatee naman sa contrast pwede siya maglead into grainy images (depending sa strength ng pagbago) tapos pwede rin magintroduct ng mimic microbleeds lalo na sa mga darker pixels.  Yung EfficientDet isa siyang variation ng U-Net na gumagamit ng fewer parameters pero better results ginamit lang yung box detection. Na mention sa paper na nagmamatter yung deph and other parameters ng isang microbleed. Doon papasok yung idea ng Segmentation. In terms rin sa limitation ng study, is biased yung training sa Dataset 1 kaya daming false positives sa Dataset 2, pwede natin gawin is transfer learning.

## Toward Automated Detection of Microbleeds with Anatomical Scale Localization: A Complete Clinical Diagnosis Support Using Deep Learning


**Introduction**
- propose a single-stage 3D deep learning detection model for automatic CMBs detection.
- develop an unprecedented location identification task that informs the anatomical location of CMBs
- investigate the clinical feasibility of the proposed framework by evaluating the generalization capability on different unseen clinical data

**Data Preprocessing**
- applied the brain extraction tool (BET) for brain skull stripping
	- reduce the number of false positives that could be caused by the skull
- all MR images of each subject were normalized using min-max normalization
- applied slice interpolation to increase the number of slices in the z-direction to 224 slices in the case of the CMB detection task
- data cropping is essential for 3D network training
	- cropping the whole MR image into 128128128 voxels for the detection task and 646416 voxels for the anatomical localization task

**Proposed Network**
- incorporates the U-Net and RPN of Faster R-CNN
- For the location identification task, we utilized U-Net to segment the brain

**CMB Detection**
- CMB mimics are considered the main challenge for previously developed methods since they cause the generation of many false positives
- incorporates the Feature Fusion Module (FFM) and Hard Sample Prototype Learning (HSPL).

**Feature Fusion Module (FFM)**

