




# Related Work

Topics:

- Locomotion
  - Motion Sickness
  - Teleportation
  - Immersion
  - Problems with space
- Gestures
  - ASL
  - Ergonomics
  - 
- Locomotion with Gestures


# Motion Sickness

The phenomenon known today as motion sickness predates modern technology by millennia and even Hippocrates wrote about it. The word "nausea", the main symptom of motion sickness is also derived from the Greek word for ship "naus". \cite{Golding} It is a very unpleasant feeling and was even used as a legal punishment in the 19th Century \cite{Reason}. The source of motion sickness is well understood because there is a lot research from military agencies since they had to transport a lot of soldiers by ship and needed them to be healthy when they reached their destination \cite{Johnson}. After the invention of the first flight simulator, the term simulator sickness was coined. Simulator sickness is a form of motion sickness that can occur when training pilots in simulator \cite{Johnson}. With the rise of head mounted displays and VR technology, motion sickness got another subcategory: virtual reality sickness, also known as cybersickness. It is distinct from simulator sickness in that the symptoms are not as much related to the Oculomotor system (for example eyestrain, blurred vision, etc) but rather disorienting. The severity was found to be about 3 times greater than simulator sickness. This might be because the VR systems are more immersive than a flight simulator that relies on traditional displays \cite{Stanney}. 
Because cybersickness and simulator sickness are different, there needs to be a separate evaluation method for the two phenomena. According to Stone et al. this is because the weighted scale of the simulator sickness questionnaire does not translate well to the VR environment. This is improved with a new weighting scale proposed by Stone et al. but a new questionnaire specifically created for cybersickness generates the best results. However the simulator sickness questionnaire is often used in reached anyway. This only has the benefit that the results are easy to compare but there are significant tradeoffs in regards to accuracy.  \cite{Stone}

## Cybersickness
As discussed before, cybersickness is a form of motion sickness. It can result in a range of symptoms including nausea, vomiting, disorientation, headaches and eye strain \cite{LaViola}. This is a serious problem and needs to be taken into account when developing VR systems. 

% TODO: indent direct quote
The actual cause of cybersickness is not known and the underlying physiological responses uncertain. The three most prominent theories for the cause of cybersickness are poison theory, postural instability theory and sensory conflict theory \cite{Davis}. 

- Poison theory: survival mechanism that induces vomiting and nausea to remove poison from the body if the brain detects sensory input like hallucinations.
- Postural instability theory: a loss of postural control causes sickness
- Sensory conflict theory: symptoms are created if there is a conflict between the vestibular and visual senses. For example if a user is not moving but their avatar in VR is.

Unfortunately all three theories have low predictive power and fail to explain some key aspects of cybersickness \cite{Davis}. 

To compare systems and study how a system influences participants,  




# Locomotion in VR
The ability to move the players avatar in the virtual environment is called locomotion. It is required for many applications or games that take place on a larger scale. Without locomotion techniques VR would be very inaccessible. A user would need a giant tracking space, which is not possible in most homes and also the technology to track the users headset would have to work over that amount of space. Locomotion is also needed even if you could walk everywhere in your space, since it can also be a convenience or accessibility feature in combination with a seated experience. Getting the locomotion mechanics just right, will also improve other interactions and user satisfaction in general. Moving to a different virtual altitude would also not be possible without some technique that can simulate the player walking up stairs. Otherwise every user would have to have stairs in their tracked space. The implementations of locomotion techniques can be very divers and so there is a wide range of categorizations schemes. 

Luca et al. collected 109 different locomotion techniques from academic sources, social media and popular VR games. The result is a public database of methods that can be filtered and compared. Some of the methods are in a preliminary state and not fully implemented or evaluated but in general the database is a great resource \cite{Luca}. There are only 8 results for hand-tracking are some of them are falsely categorized. 

## Locomotion using controllers








## Immersion









## Locomotion using hand-tracking

When filtering the locomotion database from Luca et al. for techniques that are categorized to use hand-tracking only 8 results are presented. The results that are relevant for this paper are:

- Hand Close: a gesture for continuos movement. Seams to have problems with cybersickness (25\% of study participants had to abort the 90 minute test). \cite{Huang}

- Finger Run: two-handed gesture for continuos movement, the only resource is a video on a game development account that mostly posts prototyping ideas. % TODO cite video

- Walking stick: a gesture instantiates a walking stick, that can be used to move the user in relation to the sticks touch point on the ground. This is only a preliminary database entry though and this is not a great solution for big distances or different altitudes. 

The categorizations seam to have some issues and so going through all 109 techniques, a small list of more gestures can be found:



Technologies that might work using gestures:
- World in miniature
- TV screen
- Cloudstep
- Dash Pointing

Problems:
- limited tracking space for hands: Controllers can still detect button presses and orientation changes if they are out of the tracking region, like behind the body. The hand-tracking system has no idea what the users hands are doing if they are out of view or obscuring each other.
- limited accuracy: Hand-tracking is much less accurate with current technology. This might improve in the future though.
- Hand-to-hand interaction is confusing the hand-tracking system
- 





# Gestures

## Gesture Detection
The most accessible hand-tracking hardware for virtual reality today is the Oculus Quest 2 VR headset. It has hand-tracking build in, which can be accessed using the Oculus SDK in Unity. The exact technology the Oculus Quest device uses is not known. However it can be speculated that Oculus is using a variation of the research done by Han et al. The Oculus Quest only has monochrome cameras and only a very limited amount of processing power, which correlates with the limitations addressed by Han et al. \cite{Han}. Like the Oculus Quest, the unnamed headset in the paper has 4 cameras. They are positioned on the headsets corners, all facing in slightly different directions to cover a 120° area in front and below the headset. The areas the individual cameras can see overlap in some places so that in the most important areas the hands are visible for at least 2 up to 4 cameras. 
The tracking system works by first detecting the hands in the camera streams using a CNN architecture optimized for efficiency named DetNet. The network can simultaneously localize and classify the hands which combines two steps into one. Next, a network called KeyNet takes the the cropped camera images and outputs 21 coordinates that match key points of a human hand. The network architecture is optimized to reduce jitter and consistency when moving between overlapping camera areas. This is done using extrapolated points as an additional network input. The output is suitable for basic interactions and certainty impressive for real time processing on mobile hardware but there are definite limitations. Since Hand-to-hand occlusions and interactions were not part of the training set, the output has problems with complicated poses. 


## Future Technology
Current technology has some major limitations when tracking hands. Hand-to-hand interactions, self-contact and occlusion come to mind. Smith et al. created a system that takes in high resolution data from 124 cameras capturing uniformly lit hands. The images are turned into a mesh so detailed its basically indistinguishable from the original hands. The pose of two hands and even the texture is captured without any artifacts. This process is very complex and it takes minutes to render per frame so it will take some optimization until detailed hand models like this could be included in a VR environment. However, this is the direction that technology will go, even if it will take some time. That means that even if hand-to-hand interaction is not able to be reliably tracked currently, it could be in the future. 


## Ergonomics



























