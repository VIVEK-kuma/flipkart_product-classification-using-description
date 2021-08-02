# flipkart_product-classification-using-description
classification of product using NLP and description of product 



here the dataset used is a csv file containing product description of various product here after applying NLP on the text description to preprocess the text data we train our model then predict on the new data


Text preprocessing:In this block we are preprocessing text

First we imported porterstemmer module which is used for stemming text data.
I have done preprocessing mainly on 2 columns 'product_category_tree' and 'description'.
I have ignored the deleted rows(553 and 17299)
first in 'product_category_tree' I removed all the elements except alphabets and spaces then i convert it all in lowercase elements and then split it and join using space and appended in the list corpus.
Secondly in 'description' column I removed all the elements except alphabets and spaces then i convert it all in lowercase elements after that I have deleted all the stopwords present in the description and done the stemming using porterstemmer module then split it and join it using space and appended in the list crpus
This is the basic operation for any NLP project
I have used set during stemming to improve runtime.

