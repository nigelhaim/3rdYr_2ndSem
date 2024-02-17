

| Domain | Research Topic | Related Literatures | Pros of the Field | Cons of the Field | Datasets | Models and algorithms used | Notes |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Tumor/Cancer | Breast Tumour Segmentation | Attention-Enriched Deep Learning Model for Breast Tumor Segmentation in Ultrasound Images [1] | <br> | It is considered Mammogram is better in detecting breast abnormalities within the breast tissue. Ultrasound is used as a complimentary tool. | https://scholar.cu.edu.eg/?q=afahmy/pages/dataset<br><br> | - Salient Map<br>- U-Net<br>- U-Net-SA<br>- U-Net-SA-C |  |
|  | Lung Cancer Segmentation | Lung Tumor Image Segmentation from Computer Tomography Images Using MobileNetV2 and Transfer Learning [2]<br><br>LCDctCNN: Lung Cancer Diagnosis of CT scan Images Using CNN Based Model [11] | we observed that CNN outperformed other models and has been shown to be promising compared to traditional methods. It achieved an accuracy of 92%, AUC of 98.21%, recall of 91.72%, and loss of 0.328 |  |  | -MobileNetV2<br>- Transfer Learning |  |
|  |  |  |  |  |  |  |  |
| Dengue |  |  |  |  |  |  |  |
|  | Dengue Blood Smear segmentation | Machine Learning-Based Detection of Dengue from Blood Smear Images Utilizing Platelet and Lymphocyte Characteristics [3] | Usage of Peripheral Blood Smear (PBS) Images<br><br> |  | https://www.kaggle.com/datasets/iarunava/cell-images-for-detecting-malaria | blob detection algorithm | PBS are the Gold Standard for diagnosing various pathological conditions.<br> |
|  |  | Deep learning approach for detection of Dengue fever from the microscopic images of blood smear [4] | Accuracy - 91.30%,<br>Sensitivity - 84.62%<br>Specificity - 100%<br>Precision - 100%<br>F1 score - 91.67% |  |  | Google Net |  |
|  |  | Analyzing Blood Cells in Seconds With Deep Learning [5]<br><br>Say hello to athelas one [6] | Determines the concentration of different white blood cells. It is able to identify neutrophils, lymphocytes, platelets, and even measure hemoglobin — data points that comprise the traditional CBC (complete blood count).<br><br>There is no specific function for detecting dengue | NVIDIA had attempted to make a device with a homemade blood analytics machine |  | Athelas |  |
|  |  | Intelligent algorithm for detection of dengue using mobilenetv2‐based deep features with lymphocyte nucleus [7] |  | Unaccessible |  | mobilenetv2-based deep features |  |
|  |  |  |  |  |  |  |  |
| Spine | Spine Image Segmentation | Spine-GAN: Semantic segmentation of multiple spinal structures[8] | Spine-GAN achieves high pixel accuracy of 96.2%<br>Dice coefficient of 87.1%<br>Sensitivity of 89.1%<br>Specificity of 86.0% |  |  | propose a [Recurrent](https://www.sciencedirect.com/topics/engineering/recurrent "Learn more about Recurrent from ScienceDirect's AI-generated Topic Pages") [Generative Adversarial Network](https://www.sciencedirect.com/topics/computer-science/generative-adversarial-networks "Learn more about Generative Adversarial Network from ScienceDirect's AI-generated Topic Pages") called Spine-GAN |  |
|  |  | Spinal magnetic resonance image segmentation based on U-net [9] | a cross-validation method was used to propose the use of CNN for precise segmentation of spinal MRI images, which achieved good results with an average segmentation accuracy of over 88%. |  |  | U-Net <br>U-Net ++ |  |
|  |  | Automatic lumbar spinal MRI image segmentation with a multi-scale attention network [10] | The method was tested on real spine MRI data and evaluated through similarity metrics such as dice similarity coefficient and average surface distance. The results of these similarity metrics were 92.52% and 2.71 mm respectively. These results prove the effectiveness of our method. |  | https://github.com/anjany/verse?tab=readme-ov-file | MANet with U-Net |  |
|  |  | Spine Image Segmentation Based on U-Net and Atrous spatial pyramid pooling [12] | ![[Pasted image 20240217203056.png]] |  |  | U-Net<br>SE-UNet<br>Own Method |  |
|  |  |  |  |  |  |  |  |



### References


[1] Vakanski, A., Xian, M., & Freer, P. E. (2020). Attention-enriched deep learning model for breast tumor segmentation in ultrasound images. _Ultrasound in Medicine & Biology_, _46_(10), 2819–2833. https://doi.org/10.1016/j.ultrasmedbio.2020.06.015

[2] Riaz, Z., Khan, B., Abdullah, S., Khan, S., & Islam, M. S. (2023). Lung tumor image segmentation from computer tomography images using mobilenetv2 and transfer learning. _Bioengineering_, _10_(8), 981. https://doi.org/10.3390/bioengineering10080981

[3] Mayrose, Hilda, et al. “Machine Learning-Based Detection of Dengue from Blood Smear Images Utilizing Platelet and Lymphocyte Characteristics.” _Diagnostics_, vol. 13, no. 2, Jan. 2023, p. 220. _www.mdpi.com_, https://doi.org/10.3390/diagnostics13020220.

[4] Mayrose, Hilda, et al. “Machine Learning-Based Detection of Dengue from Blood Smear Images Utilizing Platelet and Lymphocyte Characteristics.” _Diagnostics_, vol. 13, no. 2, Jan. 2023, p. 220. _www.mdpi.com_, https://doi.org/10.3390/diagnostics13020220.

[5] _Analyzing blood cells in seconds with deep learning_. (n.d.). Retrieved February 16, 2024, from https://www.youtube.com/watch?v=0J_XspPlJSY

[6] _Say hello to athelas one_. (n.d.). Retrieved February 16, 2024, from https://www.athelas.com/insights/introducing-athelas-one

[7] Mayrose, H., Sampathila, N., Bairy, G. M., Belurkar, S., Saravu, K., Basu, A., & Khan, S. (2023). Intelligent algorithm for detection of dengue using mobilenetv2‐based deep features with lymphocyte nucleus. _Expert Systems_, _40_(4), e12904. https://doi.org/10.1111/exsy.12904

[8] Han, Z., Wei, B., Mercado, A., Leung, S., & Li, S. (2018). Spine-GAN: Semantic segmentation of multiple spinal structures. _Medical Image Analysis_, _50_, 23–35. https://doi.org/10.1016/j.media.2018.08.005

[9] Wang, Z., Xiao, P., & Tan, H. (2023). Spinal magnetic resonance image segmentation based on U-net. _Journal of Radiation Research and Applied Sciences_, _16_(3), 100627. https://doi.org/10.1016/j.jrras.2023.100627

[10] Li, H., Luo, H., Huan, W., Shi, Z., Yan, C., Wang, L., Mu, Y., & Liu, Y. (2021). Automatic lumbar spinal MRI image segmentation with a multi-scale attention network. _Neural Computing & Applications_, _33_(18), 11589–11602. https://doi.org/10.1007/s00521-021-05856-4

[11] Mamun, M., Mahmud, M. I., Meherin, M., & Abdelgawad, A. (2023). _Lcdctcnn: Lung cancer diagnosis of ct scan images using cnn based model_ (arXiv:2304.04814). arXiv. https://doi.org/10.48550/arXiv.2304.04814

[12] _Radware bot manager captcha_. (n.d.). Retrieved February 17, 2024, from https://hcvalidate.perfdrive.com/fb803c746e9148689b3984a31fccd902//?ssa=4ce77ba4-5607-454a-9b37-155ecb8ea149&ssb=44080201259&ssc=https%3A%2F%2Fiopscience.iop.org%2Farticle%2F10.1088%2F1742-6596%2F2209%2F1%2F012020%2Fmeta&ssi=f2a63d1e-8427-40b5-902f-9211817fdbe5&ssk=support@shieldsquare.com&ssm=70251996758189295104115375916469&ssn=9113b7f309a4fc0073a00a46cc35c06bebec1db5fe5b-79c2-49f2-9611ed&sso=8a2be587-696553b2798aefe91fd80bab69a7342d5ff525b4f86d2f55&ssp=41782066941708166712170811436608016&ssq=52532697308051384899873080895786990097943&ssr=NTQuMTQ2LjU0Ljgw&sst=Mozilla/5.0%20(Macintosh;%20Intel%20Mac%20OS%20X%2010_15_7)%20AppleWebKit/537.36%20(KHTML,%20like%20Gecko)%20Chrome/120.0.0.0%20Safari/537.36&ssu=&ssv=&ssw=&ssx=W10=
## Links

### Datasets 
- https://www.v7labs.com/blog/healthcare-datasets-for-computer-vision#h4
- https://data.world/datasets/cancer

## Medical Image Segmentation Ideas:

**Specific Tasks:**

- **Tumor segmentation:** Develop a robust method to automatically segment different types of tumors (e.g., brain, lung, liver) from various modalities (MRI, CT, PET). Explore challenges like low-contrast boundaries, varying shapes, and presence of artifacts.
- **Organ segmentation:** Improve the accuracy of segmenting crucial organs like heart, lungs, kidneys, and bones for tasks like surgical planning, radiotherapy dose calculation, and functional analysis.
- **Lesion segmentation:** Segment specific lesions on various tissues, such as skin cancer on dermoscopy images, white matter lesions in the brain, or inflammatory lesions in the lungs. Focus on handling overlapping structures and subtle intensity variations.
- **Cell segmentation:** Develop algorithms for accurate segmentation of individual cells in microscopy images for tasks like cell counting, lineage tracking, and drug screening. Address challenges like overlapping cells, complex shapes, and varying illumination.
- **Blood vessel segmentation:** Segment blood vessels from retinal fundus images or coronary angiograms to assess vascular health, diagnose diseases like diabetic retinopathy, and plan interventions. Overcome challenges like branching structures, variable thickness, and noise.

**Methodological Approaches:**

- **Deep learning with novel architectures:** Develop specialized architectures suited for medical image segmentation, like U-Net variants, attention-based models, or recurrent networks for 3D data.
- **Incorporating prior knowledge:** Integrate anatomical atlases, shape priors, or domain-specific rules into the segmentation process to guide the model towards accurate results.
- **Multi-modal segmentation:** Combine information from different imaging modalities (e.g., MRI and PET) to improve segmentation accuracy and capture complementary information.
- **Unsupervised and weakly supervised learning:** Reduce reliance on large amounts of labeled data by exploring self-supervised learning techniques or leveraging weakly labeled data with active learning or uncertainty sampling.
- **Explainable segmentation:** Develop methods that not only accurately segment images but also provide insights into the segmentation decisions, aiding diagnosis and treatment planning.

**Additional Considerations:**

- **Focus on a specific clinical application:** Align your research with a real-world problem and collaborate with medical professionals to ensure clinical relevance and impact.
- **Evaluate on publicly available datasets:** Utilize standard datasets like MICCAI or BraTS to benchmark your method and compare it to existing approaches.
- **Consider computational efficiency and real-time processing:** If developing for clinical applications, optimize your method for efficient inference on available hardware.
## Medical Image Segmentation Topics Focused on the Philippines:


**Addressing Local Health Challenges:**

- **Developing AI-powered segmentation tools for diseases prevalent in the Philippines:** Focus on diseases like tuberculosis (chest X-ray segmentation), dengue fever (liver ultrasound segmentation), or schistosomiasis (blood smear image segmentation).
- **Segmenting medical images from resource-limited settings:** Adapt or develop segmentation models that work accurately even with low-quality images or limited computing power, common in resource-constrained regions.
- **Segmentation of medical images for under-diagnosed or under-treated conditions:** Focus on conditions with limited resources for diagnosis, like neglected tropical diseases or specific cancers prevalent in the Philippines.