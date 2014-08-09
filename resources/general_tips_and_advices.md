Sebastian Raschka  
Last updated 09/08/2014

# General tips and advices

<br>

### Sections

- [A typical pattern classification workflow](#a-typical-pattern-classification-workflow)
- [Resampling of training and test datasets](#resampling-of-training-and-test-datasets)
<br>
<br>

### A typical pattern classification workflow

[[back to top](#sections)]

<br>
<hr> 
(1) question -> (2) input data -> (3) features -> (4) algorithm -> (5) parameters -> (6) evaluation 
 <hr>
<br>

- The question should be concrete and specific: "Can I specify flower species based on the dimensions of the leaves?".

- Usually: the more input data is collected the better.

- Try to consult a domain expert for selecting "good" features.

- The choice of a learning and prediction algorithm is typically less important than good feature selection: 
	- Hand, David J. 2006. “Classifier Technology and the Illusion of Progress.” Statistical Science 21 (1): 1–14. doi:10.1214/088342306000000060. 
[http://projecteuclid.org/euclid.ss/1149600839](http://projecteuclid.org/euclid.ss/1149600839)

- It is expected that the generalization error (error on the test data set, or any other new dataset that was not used for training/fitting the model) is larger than the resubstitution error (= the error on the training dataset). However a large difference between the two error rates is a strong indicator for overfitting.

<br>
<br>

### Resampling of training and test datasets

[[back to top](#sections)]

- A typical, suggested ratio is to split an input dataset into 60% training and 40% test dataset.
- Both the test and training datasets should be randomly sampled.
- A test dataset should only be used **exactly once**, otherwise (if an algorithm is trained on the training dataset, and the test set is used to evaluate the predictor  multiple times) the test dataset "becomes" a training dataset and can cause "overfitting".
- If a test dataset is to be used to evaluate the predictor multiple times, create a separate validation dataset beforehand (the validation dataset should also only be used once).
- If the input dataset is split into three datasets, the typically suggested ratio is 60% training, 20% test, and 20% validation dataset.
- The choice whether a separate validation dataset should be used depends on the size of the dataset: A validation dataset is typically only recommended for "reasonably" large datasets
- It is generally recommended to use cross-validation: the training set is split into subsets of training and test datasets so that the original test dataset is kept to evaluate the predictor only once at the very end.
- Choose a cross-validation method (random sampling, k-fold, or leave-one-out) appropriate to your data: continuous or categorical data, large or small sample sizes.
- A typical size for **k** in k-fold cross-validation is 10 since a larger number of folds increases the variance of the error estimates and the computational time as well; very small numbers of folds can cause very biased error estimates on the other hand.
<br>
<br>

### in progress ...
[[back to top](#sections)]