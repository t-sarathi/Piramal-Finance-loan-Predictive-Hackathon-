Piramal Finance caters to the diverse lending needs of the people of Bharat with a portfolio of products ranging from Secured loans to Unsecured loans. Acquisition models are used to judge the credit worthiness of a customer before giving out loan. Post giving out a loan, various internal metrics are used to track the performance of the loan to take necessary steps whenever required.


Task
You are given a set of loans and various parameters on it. Your objective is to train a binary classification model which outputs the probability of a loan going bad.


Dataset description
The train dataset is provided with ground truth for model development. The test dataset will be used for evaluation, and you need to make submission for these. Each of the train and test datasets are further divided into three parts following the same format as
following file

‘xyz_1.csv’ (where ‘xyz’ can be ‘train’ or ‘test’) contain the primary data with both the identifier columns, ‘loan_id and ‘id’, and ‘label’ in case of train data.
The files ‘xyz_2_1.csv’ and ‘xyz_2_2.csv’ contains additional secondary data with ‘id’ as identifier.
The ‘train_1.csv’ contains the ‘label’ column which takes value 1 if there was a default in the loan. These two datasets contain same columns but the values belong from two different time periods. For example, if development time period is of September 2023, the data in ‘xyz_2_1.csv’ and ‘xyz_2_2.csv’ will be of August 2023 and April 2023 respectively.

SNo	File Name	Description	Columns
1	train_1.csv	Primary data to be used for modelling. This contains the loan performance over a period of time.	loan_id, label, id, prod, col 1…..col n
2	train_2_1.csv	Secondary data which contains bureau data for time period 1	id, add 1….add n
3	train_2_2.csv	Secondary data which contains bureau data for time period 2	id, add 1….add n
4	test_1.csv	Primary data to make predictions (analogous to train_1.csv)	loan_id, id, prod, col 1…..col n
5	test_2_1.csv	Secondary data for test (analogous to train_2_1.csv)	id, add 1….add n
6	test_2_2.csv	Secondary data for test (analogous to train_2_2.csv)	id, add 1….add n
7	sample_submission.csv	Sample file to illustrate final submission format	loan_id, prob
The columns provided in the dataset are as follows:

Column name	Description
loan_id	Represents primary key (loan ID) in the train and test dataset to be used for final prediction
id	Represents the secondary key (customer ID) to be used to combine additional bureau data
prod	Represents the product categorisation (masked)
col_1 to col_164	Represents the features in train and test data
add_1 to add_677	Represents the additional features in bureau data
label	Represents the ground truth in the train data
prob	Represents the predicted probability for final submission

Evaluation

score = 100*metrics.roc_auc_score(actual, predicted)
