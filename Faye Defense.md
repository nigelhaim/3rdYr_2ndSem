
Panelists
- Alfonzo Azucenas
- Von Guron

Robles
- good afternoon, i am the leader
- presents the thesis title
- Introduction
	- NPCs are vital components in an interactive gameplay experience
	- NPCs are demanded to be realistic and believable
- integrated Goal Oriented Action Planning


Lu
- SOP
	- will utilizing GOAP improve NPC efficiency
	- GOAP and utility AI to improve NPC accuracy
	- if GOAP and utility AI allow the player to engage more with the gameplay

Faye
- significance
	- integrate GOAP and utility AI to advance AI techniques 
	- brings significance to computer science and game development

Robles
- theoretical framework
	- utility AI 
		- deduce a goal for our system
		- for developing intelligent agents that can set actions and goals
		- looks at current world state and game statistics (e.g. hunger, thirst, etc.)
		- picks the highest scoring goal
	- shows the theoretical frameworK
	- Goal Oriented Action Planning (GOAP)
		- AI technique for developing intelligent agents that can plan and execute actions to complete an objective
		- allows the AI agents to adopt a goal-oriented approach
	- shows finite state machine (figure 1.1)
- conceptual framework
	- the study focuses on improving the npc behaviors in management simulation games
	- study will develop NPC ai agents usitng utility and GOAP
- shows conceptual framework

Fernando
- basic sketch of the system
	- at the start of the game, player will choose to play buildilngs (e.g. storage, shelter)
	- AI controlled agents, colonists, are controlled by GOAP and U-AI
	- UAI prioritizes a goal that will satisfy hunger for example and pass that to GOAP to execute that plan as efficiently as possible

Lu
- objectives
	- observe efficiency of NPCs utilizing GOAP and UAI and compare to generic path finding algorithm
	- measure the accuracy of the NPCs

Fernando
- scope
	- gocus on the management simulation game genre
	- relies on GOAP and UAI
	- the study will take place in a simulated colony environment

Faye
- Chap2
	- each alogrithm has unique strengths and weaknesses 
	- the use of GOAP in gaming reduces the need for predefined plans, allowing NPCs to create dynamic strategies based on real-events
	- randomness in NPC interactions helps emulate real human behavior
	- UAI stand out for modularity and reusability, providing a scalable solution for designing complex NPC behavior in gaming environments

Robles
- in connection to chap2
	- UAI and GOAP have not been used together

Lu
- chap3
	- hypothesis

Robles
- assumptions
- research design
	- develop game
	- respondents will play the completed game
	- respondents answer a survey
	- gameplay data sand survey data will be compiled
- research method
	- data collection
	- data analyzation

fernando
- specificaitons
	- hardware
		- might change further while the game is being developed
	- software
		- unity in C#
		- messenger, discord, google meet for communications
		- Gdocs, GSheets, GForms, GDrive, Github for collaboration
	- peopleware
		- researchers
		- thesis adviser
		- thesis coordinatior

Faye
- sampling and data gathering
	- convenience sampling
	- purposive sampling
	- stratified sampling

rob
- statistical treatment
	- shakiro wilk test
	- 1 tailed t-test if data is normalized
	- if data is not normalized; use mann-witney u test

## Post Presentation

alfonzo
- i have a problem with the term "generic AI"; because they're comparing something with no basis yet
	- what does generic AI mean

rob
- generic AI is just random stuff
- more random than none

alfonzo
- there is no backing of that information in the presentation
- there is no paper to defend you from that
- if there is a roomba, if it does not have path finding vs with path finding, of course those with path finding will surely be more effective
- its a known fact that using AI makes it more efficient
- how random is your generic AI

rob
- the randomness will always pick something that benefits it

alfonzo
- so generic AI is an ai that maximizes 

rob
- greedy algorithm essentially

alfonzo 
- get some sort of reference to compare it to
- e.g. pathfinding, finding a well documented paper makes a baseline
- need to match the novel approach with the previous approaches (baseline)
- provide a better term for generic AI
- generic AI is kind of confusing but it also needs documentation and papers to back it up (that X approach is more effective)

rob
- some game used something with generic AI or something

alfonzo
- so that will be the baseline
- recreate the game with the enhancements
- the problem that saying it, but in terms of what
	- accuracy, and player engagement
- we don't know how well a game runs based on the three things
- find an academic paper that serves as a baseline

rob
- may nahanap pero di sinama

alfonzo
- kung may papers, dagdag niyo siya
- double check the relevancy of your papers

von
- same direction with alfonzo's thoughts
- you mentioned earlier of using a questionnaire
	- it does not need to be specific to the game
- walang game engagement questionnaire

alfonzo
- may isang group na may questionnaire
- kunin nalang daw kung pwede

von
- in the 1st question in sop
	- in terms of what
	- measure if NPC improve in terms of what
- would prefer din if you can reword the SOP wherein the answer is not yes or no lang
- we encourage things to be quantitative
- when it terms of accuracy, ano ulit yun

fernando
- how close the actions taken are closest to the player's
- are you just comparing how random the proposed model is?
- why is accuracy the term
- conceptual framework
	- good but hindi nakita yung data na naeextract niyo

rob
- the data will be the player stats

von
- diba dapat the exported data is the accuracy, efficiency, etc.

rob
- those will be based on the exported player stats

alfonzo
- picturing a game, colony stats would be, the amount of..

fernando
- colony stats refer to the growth of the colony
- kunwari po, how much is the growth of the population since the population is happy
- ++ how efficient do they gather resources within a given time

von
- so if effective si NPC, maganda colony stats
- di directly si NPC babantayan
- need clarify that the "accuracy" is based on colony stats

alfonzo
- player engagement
	- medyo careful lang ako dun
	- it's a questionnaire, so kailangan ng maayos na questionnaire
	- if you choose your questionnaire
		- their questionnaire has multiple points that is addressing
	- just make sure that these are the values we're trying to check
- with the survey
	- careful lang din ako when you say casual and non-casual
	- it's an additional step to figure that out

rob
- a non-casual player would be someone who has never touched a game before
- whereas a casual is someone who played in that genre before

alfonzo
- much better to remove that and just use all of them without categorization
- just adding an extra variable

von
- why have a grouping in the first place

rob
- there's a possibility, they already know how things work

von
- find a way to back up those claims

rob
- the AI will also determine the proximity of the building
- it may not take that way as the efficient path (?)

alfonzo
- it's still not as important
- if effectiveness of the AI is the topic, the NPC should still be able to go to narnia

von
- efficiency of the AI recognizing the action of the player

alfonzo
- there is a miscommunication between the difference of efficiency and accuracy
- putting a house far away won't be efficient but that's not the efficiency we're talking about
- the AI should be quantified for its efficiency
- we're not developing a perfect game, we're seeing if including the AI will make it efficient

von
- so why 100 

rob
- basing on previous studies
- since they use 120 with separate groups each, we decide to do a similar approach in the research

alfonzo
- usually those studies have stats
- fi and when you read the paper, make sure to read those parts
- we're not sure what the population is

von
- do you know the reason why those studies chose 100
- do you think it would affect that 100 is not enough that's why their research failed
- this is why we have statistics, to calculate how many samples do we really need to generalize for a population
- good kung reference from other research
- di lang dahil ginawa nila gagawin niyo rin
	- compare the reasons too

alfonzo
- just read why they gave that number
- can you also describe to me kung gaano katagal yung experiment na gagawin niyo sa isang person
- picture me how long i would play, what's my goal as a participant, dapat ba colony stats are maximized
- how would data gathering look like to the player
- speaking of outliers, its important din to put in assumptions/scope to make the colony more manageable
- the experiment seems vague for the participants as well

lu
- game has set level of objectives to signify they have achieved a level in the game
- once they reached the final objective, they will finish the test and gather the data for the metrics
- in the SOP and objectives, there would be a set level of objectives to measure for accuracy

von
- how long should the game take to say that the data for the NPC is viable na?

rob
- the NPC will be based on the game time
- NPCs tend to take a long time
- we will shorten the game time to at most 1 hour and 30 minutes
- its still subject to change but the idea is that

alfonzo
- that needs to be well documented
- name the objectives, number of objectives, what's their purpose. 
- how would the experiment work in a simulation game
- worried din about the size of the game

rob
- there's a set level map that can be not too big and is usually very small

alfonzo
- confidently saying that, regardless, should be part of the paper
- make sure lang na everything is in the paper especially in the methodology

## after deliberation


alfonzo
- move on to the next step but with revisions about AI, the baseline AI, and the problem 
- what are the following stats to be checked
- need scientific reasoning to use such and such and how effective the new algorithm is
- need more readings,
- questionnaires, provide backup with well documentation
- kailangan rin ng reasoning behind experimentation environment and the game to be developed
	- how long someone plays, ano kailangan gawin, blablabla
	- kailangan lang talaga ng reasoning
- lalagay nalang sa suggestions yung kailangan, especially sa AI
- more or less, sir von said na ayun, kailangan ng maraming scientific backing
- you can continue as long as the misguided questions are fixed and they're more clarified
- as long as confident kayo to make the game, goods kami

