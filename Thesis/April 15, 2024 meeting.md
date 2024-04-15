### Kamustahan

**Daming ginagawa**
- SE
- Thesis
- Mock Defense
- Lab Exer 
- ML Project
![[Pasted image 20240415225654.png]]
### Last night 
3 SOP but nanghihinayang on the third part

How global detection improve in detecting CMBs on the axial plane
- Learning rate is slow if only axial plane is used unlike the learning rate of Sagittal and Coronial
- Triplanar plane (Axial, Coronial, Sagittal)
	- The hack 
		- Higher learning rate = Higher the curve and faster learning time
### Weird part 
- The number of adjacent slices is consistent checked on every candidate on the paper (On other studies)
	- Not all microbleed is the same size/length 
	- The slices are static 
	- The annotations are vertical therefore it is hard to detect on the axial plane


- Size of the subspace 
- The goal is the adjacent slices are different in every sample
- **The objectives should be mapped on the Statement of the Problem**

### Radiologist consultation
- Local region
- From a radiologist standpoint how sensible the hypothesis is 
- Finding a way to signal a microbleed form a radiologist standpoint 

- Rephrase the last sentence 
	- Rather than a "challenge" show them that because it was discussed earlier as a potential limitation because the global context is not detected 

### Attention
- 1 is general 
- 2 is specific 
- 2 proposals if kaya 
	- 1st proposed method Per slice is the axial plane is a localized attention to a microbleed that could also help detect other microbleed through attention on global context for each size
	- 2nd proposed method Attention can have a output embedded through localization on other slices 
	- Using the attention mechanism the the microbleed will be detected in every adjacent slice
		- Features will be obtained on each slice
		- How to solve it? 

#### 1st Task
- Chat GPT 
	- Use chat GPT to rephrase what you want on your SOP 
- Methodology 
	- How would you solve it? 

### Possible issue
- The attention mechanism depends on each slice any misinformation could ruin the model's performance
-  How do you solve it?
	- Do you want a specific slice as a basis of globality or all of the slices? 
	- The candidate will be the input and the 2nd stage will classify if the CMB is true or false positive 
	- The classification is included in the architecture 
	- What is the output?
		- How can you represent the output
		- Mask
	- The proposed region is the pixel 
	- Were only focused on the axial plane 
- **Problem wise is good solution wise is not clear**

### Hint
- There is something in the slices that can be used to solve the problem 

**Rephrase but not changing the content** 

**Radiologist consultation**
- The thought process of a radiologist in cerebral microbleeds
- If you determine a microbleed how would you show it as an output?

**Mock Defense**
- No phone
- Walang tinitignan
- Mag agawan kayo ng questions to answer