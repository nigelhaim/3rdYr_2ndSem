
### Microbleed Segmentation

Kuijf, Hugo J. _MixMicrobleedNet: Segmentation of Cerebral Microbleeds Using nnU-Net_. arXiv:2108.01389, arXiv, 3 Aug. 2021. _arXiv.org_, https://doi.org/10.48550/arXiv.2108.01389.

- nnU-Net has a estimated Dice performance of 0.80 over all training cases. 
- False Discovery rate - 0.60
- False Negative Rate - 0.15
- Visual inspection of the results showed that most of the reported false positives could be an actual microbleed that might have been missed during visual rating. 
- No post-processing was applied 
- Where is VALDO - Vascular Lesions Detection Challenge 2021


**nnU-Net advantages**
https://www.youtube.com/watch?v=K3qRY9Q-BFo
https://www.youtube.com/watch?v=3po8qVzz5Tc
- Holistic configuration 
- Fast execution, standard deep learning hardware
- Designed for biomedical datasets (2D and 3D)
- State-of-the-art performance 

>[!Note]- nnU-Net Empirical Parameters
>![[Pasted image 20240319142339.png]]
>![[Pasted image 20240319145916.png]]

**Critique**
- No preprocessing or postprocessing needed?
- How does it determine if its an actual microbleed? (False positive)

Seghier, Mohamed L., et al. “Microbleed Detection Using Automated Segmentation (MIDAS): A New Method Applicable to Standard Clinical MR Images.” _PLoS ONE_, vol. 6, no. 3, Mar. 2011, p. e17547. _PubMed Central_, https://doi.org/10.1371/journal.pone.0017547.

- Used Microbleed Anatomical Rating Scale during data collection 
- Kappa coefficient results 
	- Patients with single CMB in lobar regions - 0.65
	- Patients with multiple CMB in lobar regions - 0.74
- Resulted in moderate agreement between Microbleed Anatomical Rating Scale and MIDAS 
- MIDAS was much more successful for detecting CMBs in lobar regions than infratentorial or deep regions
- It is hard for MIDAS to detect single CMB (62%). If the patient has multiple CMB (100%)
- Some CMB were missed by MIDAS because of 
	- lesions located within our artefact mask, predefined within MIDAS as a map of potential artefacts
	- small CMBs with low contrast from their background, probably caused by partial volume effects due to the thick slices of the clinical T2* images
- On preprocessing they used unified spatial normalization in MIDAS that involved data smoothing and re-slicing hinders detectability of CMB 
- Binary map generation that visualizes CMB localization
	- Constrained mixture of Gaussians
	- Optimization of the empirical prior
	- Unified normalization-segmentation: second iteration
- MARS (Not not resliced) while MIDAS (re-sliced)
- Only works on GRE T2* images
- https://www.neurology.org/doi/abs/10.1212/wnl.0b013e3181c34a7d

**Critique**
- nn-UNet has better performances than MIDAS
- How do you use MARS on verifying the data? 

Dadar, Mahsa, et al. “Using Transfer Learning for Automated Microbleed Segmentation.” _Frontiers in Neuroimaging_, vol. 1, Aug. 2022. _Frontiers_, https://doi.org/10.3389/fnimg.2022.940849.

- ResNet50 was trained first on an another MRI segmentation task (cerebrospinal fluid vs. background segmentation) on T1 and T2 and T2* MRI. 
- ResNet50 achieved high performance, with a patch-level sensitivity, specificity, and accuracy of 99.57, 99.16, and 99.93%, respectively.
- CSF segmentation
	- Brain tISue segmentatiON (BISON) tissue classification tool was used to segment CSF based on the T1-weighted images
- Gray and white matter segmentation
	- All T1-weighted images were also processed using FreeSurfer version 6.0.0 (recon-all-all).
- A U-Net model was also trained on complete axial slices

>[!Note]- ResNet50 problems
>The limitations of the ResNet50 model include:
>	**data imbalance, overfitting, and lower efficiency in detecting small objects**. 
>Additionally, the ResNet50 model suffers from a lack of precision.

-----


>[!Note]- Key Takeaways 
> - There is always the problem of false positive results 
> - Results drastically change based on the processing of the data 
> - Further studies on training the model on different kinds of data and machine types 
> - Double check the data by other experts 
>


>[!Info]- Datasets and challenges
>Where is VALDO - Vascular Lesions Detection Challenge 2021
>https://valdo.grand-challenge.org/#task2





