﻿# Predicting Class for a Simulated Single Nucleotide Polymorphism Data Set

In this course project we encourage you to develop your own set of methods for learning and classifying. 

This is a simulated dataset of single nucleotide polymorphism (SNP) genotype data containing **29623 SNPs (total features)**. Amongst all SNPs are 15 causal ones which means they and neighboring ones discriminate between case and controls while remainder are noise.

In the training are 4000 cases and 4000 controls. My task was to predict the labels of 2000 test individuals whose true labels are known only to the instructor and TA. 

### Links to Datasets
 - [Datasets](https://github.com/Gonnuru/Simulated_Single_Nucleotide_Polymorphism/blob/master/testdata.rar)
 - [labels](https://github.com/Gonnuru/Simulated_Single_Nucleotide_Polymorphism/blob/master/train_labels.txt) 


### ML Techniques Utilized
I have used cross-validation to evaluate the accuracy of my method and for parameter estimation. I wasn’t supposed to use numpy or scipy except for numpy arrays as given below. I was also allowed to use the following:
-	support vector machine
-	logistic regression, 
-	naive bayes, 
-	linear regression
-	dimensionality reduction modules 

but not the feature selection ones. These classes are available by importing the respective module. 

For example to use svm we do

*from sklearn import svm*

I could make system calls to external C programs for classification such as:
-	svmlight 
-	liblinear
-	fest
-	bmrm.

### Challenges Faced

**Memory issues:**
One challenge with this project is the size of the data and loading it into RAM. Floats and numbers take up more than 4 bytes in Python because everything is really an object (a struct in C) that contain other 
information besides the value of the number. To reduce the space I have used the array class of Python.

**Type** 
*from array import array*

In the beginning of my program. Suppose we have a list of n float called l. This will take more space than 4l bytes. To make it space efficient create a new array called l2 = array('f', l). The new array l2 can be 
treated pretty much like a normal list except that it will take 4l bytes (as is done in C or C++). One may also use numpy arrays for efficient storage.

In my program I could take as input:
-	[training dataset]()
-	[trueclass label](https://github.com/Gonnuru/Simulated_Single_Nucleotide_Polymorphism/blob/master/train_labels.txt) file for training points
-	[test dataset](https://github.com/Gonnuru/Simulated_Single_Nucleotide_Polymorphism/blob/master/testdata.rar) 

### Output
I have achieved an [output](https://github.com/Gonnuru/Simulated_Single_Nucleotide_Polymorphism/blob/master/Output.txt) with an accuracy of 65%








