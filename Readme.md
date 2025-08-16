## ML task By Backbencher studio


The stipulated task is about to sentiment analysis of imdb review dataset. Here is  the [Dataset Link](https://www.kaggle.com/datasets/mantri7/imdb-movie-reviews-dataset)

# Dataset Modification
The entire dataset is divided divided on train and test csv file. It content review of movie consumers (represented column by 0) and the sentiment label (represented by column 1). I took 1250 positive (label 1 for positive) and 1250 negative (label 0 for negative) review from both test and train csv file  randomly and concated them into one csv file which content 5000 data. For furthur randomness, I shuffle the csv one more time randomly. I also renamed column 0 and 1 as review and sentiment respectively. I reduced the dataset size for several reasons. Such as,

- Language preprocessing  process data each by each. Therefore, more data will be take much time in  the process
- Much data need larger vocabulary size. Which  can be caused overfitting.
- More deversified and lengthy data can cause difficulty in setting model's parameter.

# text pre-processing

I used Spacy for the language model. In text preprocessing teniques I  remove the html tag, only take alpha neumaric letters, and transformer all letter nito small letter. Then I tokenized the sentance with spacy, lemmatize the sentence and remove all stop word from the sentance. 

# Text Vectorization

For  classical machine learning models, I utilized the TF-IDF for text vectorization. And for RNN and transformer I used TextVectorization from Keras.


# model

We trained our tf-idf vectorized dataset on Gaussian Naive Bayes, Decision Tree and Logistic regression on 80:20 train:test split and obtained following results.

# Result for Naive Bayes

![App Screenshot](https://github.com/Prithibee13/ML-Task/blob/main/ML/Confusion/Naive_bayes%20Confusion.png)
- Naive Bayes Accuracy : 0.657
- Naive Bayes Recall : 0.6534653465346535
- Naive Bayes F21- Score : 0.6580259222333001

# Result For Decision Tree

![App Screenshot](https://github.com/Prithibee13/ML-Task/blob/main/ML/Confusion/Decision%20Tree%20confusion.png)
- Decision Tree Accuracy : 0.707
- Decision Tree Recall : 0.7267326732673267
- Decision Tree F1-Score : 0.7147030185004869

# Results for logistic regression

![App Screenshot](https://github.com/Prithibee13/ML-Task/blob/main/ML/Confusion/Naive_bayes%20Confusion.png)
- Logistic Regression Accuracy : 0.87
- Logistic Regresion Recall : 0.897029702970297
- Logistic Regression F1-score: 0.8745173745173745

# Testing one instance
Review Instance:  And here's yet another piece of evidence to claim that we should all worship the Italian giallo and acknowledge it to be the absolute most unique sub genre in horror. Emilio Miraglia's "The Red Queen Kills Seven Times" is a totally mesmerizing wholesome of original plotting, stylish production values, enchanting music, great acting talents and inventively gory murder sequences. It's a fabulous giallo (released in the golden year 1972) that belongs in the top-five of every fan of Italian cinema. The storyline doesn't just introduce your average black-gloved & sexually frustrated killer, but blends good old-fashioned revenge motives with the macabre myth of the murderous "Red Queen". At young age, their grandfather tells the constantly fighting siblings Kitty and Evelyn about an uncanny lady who, once every 100 years on April 6th, kills seven people of which her sister is the inevitable last victim. Fourteen years later, Kitty has become the successful choreographer of a prominent modeling agency (even sharing her bed with the general manager) when suddenly the killing spree begins. Sister Evelyn would be the obvious culprit, but she moved to the States recently... Or has she? Complex yet compelling and involving red herrings are thrown at you every couple of minutes and the Red Queen character is definitely the most fascinating killer in giallo-history. Her face can never be seen, but she wears a blood red cloak and produces the most ghastly laugh whenever she made a new victim. She's not exactly gentle either, as her victims are barbarically stabbed with a dagger, dragged behind cars and even impaled on fences! That latter one is truly one of the greatest (= most gruesome) acts of violence I've ever seen! What more could you possibly request? Some classy and tasteful nudity, perhaps? The gorgeous female actresses got this more than covered, among them Barbara Bouchet and a young Sybil Danning. Emilio Miraglia isn't the most famous giallo-director, as he only made this one and the equally recommended "The Night Evelyn Came Out of the Grave", but his influence and importance should NOT be forgotten.
Review Label:  1
Processed text: s piece evidence claim worship italian giallo acknowledge absolute unique sub genre horror   emilio miraglia s   red queen kill seven time   totally mesmerize wholesome original plotting   stylish production value   enchant music   great act talent inventively gory murder sequence   s fabulous giallo   release golden year        belong fan italian cinema   storyline doesn t introduce average black gloved    sexually frustrated killer   blend good old fashioned revenge motive macabre myth murderous   red queen    young age   grandfather tell constantly fight sibling kitty evelyn uncanny lady        year april   th   kill seven people sister inevitable victim   fourteen year later   kitty successful choreographer prominent modeling agency   share bed general manager   suddenly kill spree begin   sister evelyn obvious culprit   move state recently       complex compelling involve red herring throw couple minute red queen character definitely fascinating killer giallo history   face see   wear blood red cloak produce ghastly laugh new victim   s exactly gentle   victim barbarically stab dagger   drag car impale fence   truly great     gruesome   act violence ve see   possibly request   classy tasteful nudity     gorgeous female actress get cover   barbara bouchet young sybil danne   emilio miraglia isn t famous giallo director   equally recommend   night evelyn come grave    influence importance forget
Naieve Bayes Prediction:  [1]
Decision Tree Prediction:  [1]
Logistic Regression Prediction:  [1]

![App Screenshot](https://github.com/Prithibee13/ML-Task/blob/main/RNN%20and%20Transformer/Confusion%20Matrix/bilstm%20Cofusion.png)

# confusion matrix for Transformer model. 
![App Screenshot](https://github.com/Prithibee13/ML-Task/blob/main/RNN%20and%20Transformer/Confusion%20Matrix/Transformer%20confusion%20Matrix.png)