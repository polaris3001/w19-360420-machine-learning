ErrorAnalysis
=============

#### 360-420-DW - Section 03

#### Xenia Beltei and Susan Ly


Distribution of Model Accuracy
------------------------------

1. Why do we get a different accuracy each time we run the classification model?

	We get a different accuracy each time we run the classification model, because in DataSet.java, the lines 148 to 150 
refer to the class method "shuffle" from the "Collections" class which accesses different elements randomly from a 
given String. So each time we run the code, we cut the data set randomly, making us work with a different section of 
data which affects the accuracy of the overall results. 

2. How much does performance can be expected to vary on unseen data?

	Performance can be expected to vary a little bit on unseen data each time we run the classification model.
Given that the standard deviation is so low, the performance can be said to be not bad.

Mean: 0.9576224337451792

Standard Deviation: 1.7245785013738416 x 10^-4

3. What is a sensible baseline against which we should compare our model's performance?

	Random identification is a sensible baseline against which we should compare our model's performance.
For example, if the majority of the data says that the breast cancer is benign and we run the classification model
assuming that all of the data indicates that the breast cancer is benign, then we will get a maximum accurary that 
is equal to the actual number of benign breast cancer. In DataSet.java, line 200 refers to a method that indicates
the frequency of a given label. This means that if the frequency of that label, let's say benign, is 80%, then it 
is fine to conclude that we are 80% accurate when we assume that all the data is benign breast cancer.

Analysis of Different Error Types
---------------------------------

4. What is a False Positive?

	A False Positive is receivng a test result which incorrectly indicates that a particular condition is present.
In this case, a False Positive would be receiving the result that the breast cancer is malignant when it is benign.

5. What is a False Negative?

	A False Negative is receiving a test result that indicates a person does not have a particular condition when 
the person actually does have it. In this case, a False Negatice would be receiving the result that the breast cancer 
is benign when it is malignant.

6. Extend your analysis in the previous step (with the 1000 runs) to keep track of Recall and Precision as well.

	a) What makes these two measures different?

		Recall is the fraction of relevant elements received over the total number of 
	relevant elements. In other words, it is the fraction of true positives over the total 
	number of positives which is a sum of the false negatives and true positives. 

	Mean Recall: 0.94437502610804028

		Precision is the fraction of relevant elements received over the selected elements. 
	In other words, it is the fraction of true positives over the number of predicted positives
	which is a sum of the true positives and false positives.

	Mean Precision: 0.9458143902103265
	
		Recall and Precision are different measures, because they calculate different portions of the data.
	It is important to note that in general, the ratio of these two measures are usually similar, because
	the total number of positives is approximately equal to the number of predicted posisitves.
	
	b) What are sensible baseline for each of these measures?
	The sensible baseline for the precision would be 1. The close the number is to 1 the more precise it is because if the 
	ratio of the baseline and the precision gives a number close to 1, it will mean that it's well predicted. In 
	the case of the recall, the baseline is also 1 because the recall and the precision have similar ratios.
		

7. How do the above results change with the hyperparameter k?

	The hyperparameter k indicates the number of closest neighbors that are used to determine the class of an element. 
The bigger the k is, the harder it is to figure out the class of the element, as the program will have to consider 
much more neighbors' classes before predicting a label. This means that the boundaries between the classes will be 
less evident.
Also it is important to note, that the k should be odd to avoid tied votes.
	
