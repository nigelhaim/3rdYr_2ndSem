
# Proposed New Thesis Topic


## Coronary artery vessels Segmentation through transformers and R2U-Net Models to diagnose Atherosclerotic plaques.

### Dataset 
**ARCADE Challenge**
- Related papers and statistics (Website) - https://paperswithcode.com/dataset/arcade
- Dataset Download - https://zenodo.org/records/8386059
### Objective 
- Improve the mapping of Left Coronary artery vessels using x-ray angiography images 
- Coronary Segmentation
- Detection of atherosclerotic plaques. 

### Abstract 
- The papers only focused on the segmentation part of the challenge (Task 1), only one study conducted on the diagnosis of atherosclerotic plaques. 

### Related papers limitations and encountered problems

**StenUNet: Automatic Stenosis Detection from X-ray Coronary Angiography** [1]
- StenUNet operates on individual frames
- X-ray coronary angiograms are captured over a sequence of frames.
- Authors suggested to improve the research through the use of Recurrent Neural Network or transformers. 

**SSASS: Semi-Supervised Approach for Stenosis Segmentation** [2]
- Underscores approach on efficiency and effectiveness in addressing complex medical images
- YOLOv8 struggles on detecting objects in cluttered scenes or partially occluded. It also has difficulty on detecting small objects or lower contrast 
- Struggled with adjusting the confidence threshold that resulted to overfitting

**YOLO-Angio: An Algorithm for Coronary Anatomy Segmentation** [3]
- Has tendencies to overpredict vessel boundaries. 
	- It was solved through serial erosion of the predicted segmentation 
	- The addressed solution lacks optimization. 
- Suggested that Segmentation combined with stenosis detection to automated diagnosis.

**Multivessel Coronary Artery Segmentation and Stenosis Localisation using Ensemble Learning** [4]
- Imbalance on noise-to-image ratio
- Baseline models cannot surpass performance thresholds
- Some unsuccessful approaches 
	- Data Processing 
	- Geometric Augmentations 
	- Synthetic Data Generation
	- Loss Functions
	- Fine-Tuning 
	- Ensemble Strategies 
	- Conditional Generative Adversarial Networks

**MPSeg : Multi-Phase strategy for coronary artery Segmentation** [5]
- Lacks performance on Side Segmentation 
- Some did not performed well based on comparing the ground truth and the segmented image
- Struggles on segmenting the LCA  

| Model      | Architecture                                                                                     | Objective                                                          | Result F1 |
| ---------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ | --------- |
| StenUNet   | UNet-based model                                                                                 | X-Ray Coronary Angiography detection                               | 53.00     |
| YOLOv8m    | CNN - Path Aggregation blocks - Classification (Boxes)                                           | Cardiovascular segmentation                                        | 0.536     |
| YOLO-Angio | Featuree selection - YOLO-based segmentation - Logic based approach                              | Coronary Anatomy Segmentation                                      | 0.411     |
| MultiModel | State of the Art Segmentation models                                                             | Multivessel coronary artery segmentation and stenosis localisation | 39.39     |
| MPSeg      | Vessel Classification - YOLOv8M<br><br>UnetPlusPlus with ResNet34 encoder - LCA and RCA <br><br> | Coronary Artery Segmentation                                       | 0.61      |
### Terms 
**Atherosclerotic plaques** - Atherosclerosis thickening or hardening of the arteries. It is **caused by a buildup of plaque in the inner lining of an artery**. Plaque is made up of deposits of fatty substances, cholesterol, cellular waste products, calcium, and fibrin. As it builds up in the arteries, the artery walls become thickened and stiff.[6]


References: 

[1] _Papers with Code - StenUNet: Automatic Stenosis Detection from X-Ray Coronary Angiography_. https://paperswithcode.com/paper/stenunet-automatic-stenosis-detection-from-x. Accessed 9 Mar. 2024.

[2] Lee, In Kyu, et al. _SSASS: Semi-Supervised Approach for Stenosis Segmentation_. arXiv:2311.10281, arXiv, 16 Nov. 2023. _arXiv.org_, https://doi.org/10.48550/arXiv.2311.10281.

[3] Liu, Tom, et al. _YOLO-Angio: An Algorithm for Coronary Anatomy Segmentation_. arXiv:2310.15898, arXiv, 24 Oct. 2023. _arXiv.org_, https://doi.org/10.48550/arXiv.2310.15898.

[4] Bilal, Muhammad, et al. _Multivessel Coronary Artery Segmentation and Stenosis Localisation Using Ensemble Learning_. arXiv:2310.17954, arXiv, 27 Oct. 2023. _arXiv.org_, https://doi.org/10.48550/arXiv.2310.17954.

[5] Ku, Jonghoe, et al. _MPSeg : Multi-Phase Strategy for Coronary Artery Segmentation_. arXiv:2311.10306, arXiv, 16 Nov. 2023. _arXiv.org_, https://doi.org/10.48550/arXiv.2311.10306.

[6] _Atherosclerosis_. https://www.hopkinsmedicine.org/health/conditions-and-diseases/atherosclerosis. Accessed 9 Mar. 2024.

