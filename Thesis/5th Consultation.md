
## Kamustahan
- Software Engineering 
- Buhay pa naman 

### Progress
- Good to pursue 
- There is no model much more complicated to U-Net

#### Ventures
##### Andy
- Theres a lot of preprocessing 
- Some datasets have multiple or adjacent slices 
	- Slices of the current state of the brain 
- Cirtique 
	- Can you change the postprocessing and change it to the currence 
	- Para End-to-End 
- This really lacks research 
- Data Augmentation 
	- Could introduce artifacts
	-  How can it be fair 
	- Scaling up can really create artifacts (all pictures are made equal resolution) 
	- False positive - 118
	- Total Data - 119 
- The dataset is not consistent 
- Theres a lot of two stage processing 
	- its ok but not super ok 
	- Therese two types of object detection 
		- Propose regions of interest
		- Classification 
	- Computation expensive 

##### Kess
- Automated detection of microbleeds to severe injury 
- 4 models to compare 
	- Traditional two stage approach (Baseline)
	- Patch CNN (Classifcication)
	- Segmentation CNN 
	- UNet has the highest results 
	- Segmenation is better than classification
- Focused on severe cases 
- Fewer cases of microbleeds results to not good results 
- There is localization on what regions on the brain 
- Applied on hard sample learning 
- Used U-Net 
- All microbleeds results to True Positive or False positive 
- Ciritique 
	- Problem on clustered microbleeds to solve this a heatmap is applied 
	- But there is no count on the microbleed
	- What if the microbleeds are really valid on the non-regions 
	- Too focused on the specific regions 
- Theres a lot of opportunities for research 
- Single stage 
	- Are all single stage processing efficient? 
#### VALDO Dataset 

The VALDO datasets are only writeup more on submission only but there is a documentation of the VALDO dataset validity. All results are below the optimal results. 
- Conference side this is a good contribution 

The segmentations are too small 

We can work on both if you can find new datasets 

Anemia and Melanoma had two datasets (2016 and 2018) and compared. Its not necessarily to focus on one dataset. 

Will it become an issue? 
- Last minute dataset changing can happen

Different resolutions 
- Lossless compression and Lossley infromation 

Transfer Learning 
- Doable 
- Dont expect that it is 100% work better if there is an initial run 
- Assumption is youre going to do transfer learning anyway 
- Train it on the same data set including the splitting of data.

#### Are there other datasets? 
- There are other datasets but theres a stric requrement 
- These too much information 
- The more datasets the better
- Can you contact them? 
	- To much process 
	
- There are other dataset but the problem is there is not segmentation map 
- Synthetic is medical (Scary)


#### What is the final Research problem? 
- Package all the problems as a research problem 
- The increasing of performance should only act as a byproduct of the thesis 
- It is important is "What is the problem?"
	- Case management system 
		- In terms of adoption is it easy to adopt it in the business? 
- Your projects should 
- If your manager doesnt have the same mindset as yours it could act as a redflag 
- People who excel in work who finds problems are good assets 
- Its good to use R2U-Net but what is the problem? 
- Form the problem and think of the solutions for that 
- If the problem is two stage or the scope is too small or too much post processing. Find each attack on those problems
	- Two stage processing
	- Small scope 
		- How do you implement a larger scope 
	- Post processing 
		- Keeping the base and imbedding them on the architecture 
- How can your proposed solution address these problems? 
- Create a methdology
	- How do you plan to address these problems? 
- You can package them into one 
	- Each subproblem solved dictates to solve the main problem 
	- All of those are evidences solves the main problem 
	- Can you make one approach that strikes them out in one? 
		- If you can package them in one and larger scope then pwede niyo siya isabay as a problem 
		- Can be hard in the experimentation
		- Masters level and **might** need more time to finish 
			- Its an expectation to be delayed 
		- Undergraduate students focuses on one because of the time 
		- The more you try to think or adjust the methodology the more it could separate from other problems you want to attack 
		- What is the problem workable on your end? 
		- Have backup problems
		- In terms of the content 
			- Each suproblems you can create a paper for that 
- 1 Problem
	- 
- 2 Methodology 
	- The answer can be found on other areas of medical imaging
	- Apply your approaches 

Theres always a flaw in the paper. Theres always needed to be solved. Kahit solved na what else needs to be solved? Deep Learning approach is data intensive. Provide a good segmentation on a fewer data. Cite on the results on non-published. 