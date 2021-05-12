# Topic Modeling for Research Articles
## Topic identification of a research article by analysing its abstract.

### Introduction
This project was done as a part of Hacklive3 conducted by Analytics Vidhya.

### Problem Statement
Researchers have access to large online archives of scientific articles. As a consequence, finding relevant articles has become more and more difficult. Tagging or topic modelling provides a way to give clear token of identification to research articles which facilitates recommendation and search process. 

Given the abstracts for a set of research articles, predict the tags for each article included in the test set. 
Note that a research article can possibly have multiple tags. The research article abstracts are sourced from the following 4 topics: 

1. Computer Science

2. Mathematics

3. Physics

4. Statistics

List of possible tags are as follows:

[Tags, Analysis of PDEs, Applications, Artificial Intelligence,Astrophysics of Galaxies, Computation and Language, Computer Vision and Pattern Recognition, Cosmology and Nongalactic Astrophysics, Data Structures and Algorithms, Differential Geometry, Earth and Planetary Astrophysics, Fluid Dynamics,Information Theory, Instrumentation and Methods for Astrophysics, Machine Learning, Materials Science, Methodology, Number Theory, Optimization and Control, Representation Theory, Robotics, Social and Information Networks, Statistics Theory, Strongly Correlated Electrons, Superconductivity, Systems and Control]

### Dataset
Dataset consists of train and test set in csv format. Each training example has 31 columns. 1 is index column, 1 column contains the abstract of the paper, 4 columns contain boolean value of whether the paper belongs to a certain topic(Computer Science, Maths, Physics, Statistics) and remaining 25 columns contains boolean values representing whether the paper belongs to the corresponding target tags.

### Solution methodology
Our solution adopts a traditional mahcine learning  algorithm rather than a deep learning approach.
Data preprocessing includes removing frequently used words(which are of less significant meaning), converting the text to lower case.
The text is then passed to a Countvectorizer to extract the token of words for training.
This is done twice to two different CountVectorizers with varying n-gram and max-features parameters which will be trained differently. The algorithm used is a OneVsRestClassifier with logistic regression as the classification algorithm.
The two different outputs obtained can be blended to produce a better result.

### Tools used
1. Python
2. Jupyter notebook
3. re(regular expression library)
4. nltk(python toolkit)
5. sklearn(library)

### Result
The metric used to score the model perfomance was f1 score.
The first model and the second produced an f1_score of 0.74513 and 0.74586 respectively on the test dataset. The model went on to give an f1_score of 0.7346 on the benchmark dataset defined for the hackathon.

[Note:
1. word_freq.ipynb is used to return some of the most common words in the text which do not convey much meaning. This texts are removed as they do not contribute much to the model's performance.The top n most frequent words(as specified) are saved in the "frequently_used.txt" file.
2. People are encouraged to play with the hyperparameters such as n-gram values and common words to be removed to increase the model's performance. ]




