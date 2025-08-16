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


# confusion matrix for Transformer model. 
![App Screenshot](https://github.com/Prithibee13/ML-Task/blob/main/RNN%20and%20Transformer/Confusion%20Matrix/Transformer%20confusion%20Matrix.png)