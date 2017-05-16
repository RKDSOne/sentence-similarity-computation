# sentence-similarity-computation
This project is based on one of the ongoing kaggle competitions:   
Quora Question Pairs, Can you identify question pairs that have the same intent? (https://www.kaggle.com/c/quora-question-pairs).    
Datasets are stored in csv file, which are available from https://www.kaggle.com/c/quora-question-pairs/data. (log in required).   

The datasets include train (train.csv) and test (test.csv) part. The training part contains 404290 sets of data, each set of data contains the following features:     
•	id - the id of a training set question pair      
•	qid1, qid2 - unique ids of each question (only available in train.csv)    
•	question1, question2 - the full text of each question     
•	is_duplicate - the target variable, set to 1 if question1 and question2 have essentially the same meaning, and 0 otherwise.     
The test part contains 2345796 sets of data, each set of data contains the same features as that of the training data, except the is_duplicate feature.   

In general, this is a classification problem. In this project, 12 features of each sentence pair in the training data sets are extracted. Based on these features and labels, a supervised learning model was built to predict the probability (a number between 0 and 1) that the questions are duplicates. Typically, a probability of greater than 0.5 is regarded as duplicate, while probability of less than 0.5 is regarded as non-duplicate.  Considering time efficiency and feature importance, 10 features were finally selected for supervised learning and predicting test data sets labels. The test data labels was stored in a csv file containing a header which has the following format:   

test_id,is_duplicate   
0,0.5    
1,0.4  
2,0.9   
etc.   


I used Python 3.5.1 and the following libraries in Python:

sklearn 0.18.1  
nltk 3.2.2    
pandas 0.18.1   
numpy 1.12.1   
six 1.10.0   
scipy 0.17.1   
textblob 0.12.0   
matplotlib 1.5.1   
xgboost 0.6   
seaborn 0.7.1   



