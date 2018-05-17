# Intel AI Academy Webinar (5.17.18)

## Intel AI Academy
- Intel hosted resources and training for AI
- Student Ambassador Program: devmesh.intel.com

## Intro to AI
- AI: A set of programs that have cognitive functions
- ML: A branch of AI where we don't explicitly program a model, but feed data that allows the program to learn on its own.
- DL: (Deep Learning), set of models that determine themselves what the best representation of data is. We can use it if we won't be able to known which features to use on our own.
- AI has existed since the 1950s: https://cl.ly/1X1c2S3y2l3b
	- AI Winters occurred when the yield of AI didn't seem to pay off as folks had hoped

### Deep Learning Breakthrough
- 2012: DL model beats previous benchmark on ImageNet competition
- 2013: DL is used to understand conceptual meaning of words
- 2014: Computer Visions algorithms can understand/describe photos
- 2015: Tensorflow developed
- 2016: AlphaGo beats Go master

### Modern AI
- Playing a large role in CV (self driving cars, healthcare) and NLP (translations)
- Only 58% of businesses are researching AI, 12% currently using. 

### Why is this Era of AI different?
- Bigger Datasets
- Faster Computers
- Neural Networks
- All of these lead to more innovations in a variety of fields
- Also, a lot of open sourcing is currently going on

## Applications
Some examples include:
- High risk inspection of solar farms by drones. Because the farms are far away (and other factors), we can use drones to detect broken panels, etc.
- Silicon package defect detection. This model checks for issues in silicon chips/modules
- Home buying assistant: Given visual characteristics of a home, suggests other homes
- Credit card anomoly detection

## Data Science Workflow
- Diagram of the flow, generally https://cl.ly/390a172w0G46
- The skillset includes data munging, statistics, software engineering, domain expertise, modeling, storytelling and communication

## Machine Learning
- Supervised and Unsupervised Learning
- Supervised methods include regression and classification
- Unsupervised methods include clustering and recommendation systems

### Supervised Overview
- Training (data plus model -> trained model)
- Inference (trained model plus features -> prediction)

### Considering Models
- Training Time 
- speed for making predictions
- amoutn of data needed
- type of data
- problem complexity
- abilty to solve complex problems

## Data Sources
- Human generated, like with social media
- IoT and machine generated data (through sensors for eg)
- Public websites
- Legacy documents, as in the insurance and medical industries
-

### Data Types
- Numerical (continuous or discrete), categorical data, ordinal, text, image, audio (last three are more where DL is hitting)

### Data Shape
- More features you have, more samples required
- If you don't have enough features for useful information, need to find features, not more samples
- If you have too many features but not enough samples, might overfit

### How to determine enough samples
- Learning curves or statistical heuristics (like having 10x as many samples as DoF might help)

### Increasing number of features
- Feature engineering (design new features)
- Polynomial features

### Decreasing number of features
- You might have to reduce features, like through dimensionality reduction

### Data Preprocessing
- might have to restructure data for your model, especially if it's super raw
- There could be missing data values: do you put in the mean? should you keep the sample?

### Labeling Data
- Data can be hand labeled, but can be expensive and time consuming

### Challenges
- Anything can lead to overly optimistic results
- There can be a bias in the data or an unbalanced group of classes, which can lead to a lot of issues


