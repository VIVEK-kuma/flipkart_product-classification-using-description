# flipkart_product-classification-using-description
classification of product using NLP and description of product 



here the dataset used is a csv file containing product description of various product here after applying NLP on the text description to preprocess the text data we train our model then predict on the new data
dataset can be downloaded from     https://drive.google.com/file/d/1Rzozfho5ak88mClwSksdNAzraZ8ZRHUl/view?usp=sharing


Text preprocessing:In this block we are preprocessing text

First we imported porterstemmer module which is used for stemming text data.
I have done preprocessing mainly on 2 columns 'product_category_tree' and 'description'.
I have ignored the deleted rows(553 and 17299)
first in 'product_category_tree' I removed all the elements except alphabets and spaces then i convert it all in lowercase elements and then split it and join using space and appended in the list corpus.
Secondly in 'description' column I removed all the elements except alphabets and spaces then i convert it all in lowercase elements after that I have deleted all the stopwords present in the description and done the stemming using porterstemmer module then split it and join it using space and appended in the list crpus
This is the basic operation for any NLP project
I have used set during stemming to improve runtime.

In this block I have created a separate dataframe of preprocessed text to improve readability of code.

I have figure out that main category of the data lies in the begining of product_category column elements so I have cut a strip of first word and treat it as a class itself.




Data Labelling

In this block I used count vectorizer on 'description' column because ountVectorizer is used to convert a collection of text documents to a vector of term/token counts.
I used LabelEncoder on 'product_category' column because it can normalize variables and labelencoder also convert non numerical to numerical variables.
I used train_test_split to split the data into training set and test set I used 75% data for training purpose to avoid overfitting.

Multinomial Naive bayes Classifier:
It is a really good model when we have to classify text data into multiple categories.

This block and the block below this is used for model validation, in this block we calculated accuracy and classification report of the model and check underfitting.
In the block below this block we checked overfitting by observing difference in model accuracies when prediction is done in test set and training set(if difference is high then there is overfitting and if diffrence is low there is no overfitting).
These methods tells us how good our model is.

checking Accuracy

The Block below is used to calculate accuracy and to check underfitting
the Block below this block is used to check overfitting by observing difference in model accuracies when prediction is done in test set and training set(if difference is high then there is overfitting and if diffrence is low there is no overfitting).

Hence we see that there is also no overfitting in logistic regression model but this model do not converge to local optima so I prefered Multinomial Naive bayes algorithm I have used other algorithms(Randomforest,xgboost,etc) also but the RAM crashed during fitting phase so i end up with these two models and also these two model give fair results.

Hence we see that there is also no overfitting in logistic regression model but this model do not converge to local optima so I prefered Multinomial Naive bayes algorithm I have used other algorithms(Randomforest,xgboost,etc) also but the RAM crashed during fitting phase so i end up with these two models and also these two model give fair results.
