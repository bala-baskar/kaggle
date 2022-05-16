When we build a Random Forest algorithm, without making data do train - test split, by default, the algorithm splits the data with approx 65 - 35 split ratio. The reason behind this is that algorithm uses the **bootstrap sampling** method. In simple terms, bootstrap is the random sampling with replacement. 

**What is random sampling with replacement?**

Let's say we have **n** rows in the dataset and we choose to make **n** trials. In each trial, we randomly select a data point and keep it for model training. Now, we put the selected data point back to the dataset. For the second trial, we may choose a new data point or the same old one, since the trial is independent of previous trial outcomes and completely random.


So, as described, the algorithm randomly draws a data point from the dataset and uses it for training (**train data**), and after the defined number of trials (based on total data pts), the algorithm uses sample data for model training. Due to random sampling with replacement, there will be data points left out by the algorithm (**test data, also known as OOB in RF**). And, on average this train-test ratio will be **63.2% - 36.8%** (precisely).

**So, why on average bootstrap sampling method contains 63.2% of the sample?**

Let n be the number of data points in our dataset (n rows)

The probability of choosing a data point is $${1 \over n}$$
The probability of not choosing that data point is  $$(1  - {1 \over n})$$
For n trials, the probability of not choosing the data point is $${(1  - {1 \over n})^n}$$

(We multiply the probability of each event, as it is independent (not influenced by the previous outcome)

When n gets larger and larger, then the probability of not choosing the sample will become:

$$\lim\limits_{n \to \infty} {(1  - {1 \over n})^n} = {1 \over e} = 0.368$$

Thus, the probability of not choosing the sample is 36.8%, then the probability of choosing the sample is  (100- 36.8)% = 63.2%

This implies that for a given dataset with n rows, on average, **63.2% of rows are used for model training** while **36.8% of rows are used as test data (Out-of-Bag sample)**. We can also refer OOB score in the scikit - sklean function while building the RF model, to see what is the accuracy of the model on unknown data.