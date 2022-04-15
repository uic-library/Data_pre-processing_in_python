---
title: "Steps in Data Pre-Processing"
teaching: 0
exercises: 0
questions:
- "What is Data Processing?"
- "How to create a Variable?"
objectives:
- "To understand variables and the rules of naming variables"
---

## What is Data Pre-Processing?

Before we start exploring our data to extract the insights out of it, we need to process our data to make it understandable. Preprocessing the raw data helps to organize, scaling, clean, simplifying it for being used to train machine learning algorithms.

The following are the steps in Data Pre-Processing:

* Missing values
* Standardization
* Normalization
* Encoding categorical features
* Discretization

## Handling Missing Values
Handling missing values is an important step, as it can affect your model. It is important to identify the missing values and know with which value they can be replaced.Depending on the missing data a decision is made regarding whether or not to keep entries with missing data.

A better strategy is to impute the missing values. Infer means to infer them from the known part of the data. The SimpleImputer class provides basic strategies for imputing missing values. Missing values can be imputed with a provided constant value, or using the statistics (mean, median, or most frequent) of each column in which the missing values are located.

~~~
import pandas as pd
import numpy as np
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import Normalizer
from sklearn.preprocessing import LabelEncoder, OneHotEncoder
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import KBinsDiscretizer
from sklearn.impute import MissingIndicator


indicator = MissingIndicator(missing_values=np.NaN)
indicator = indicator.fit_transform(df)
indicator = pd.DataFrame(indicator, columns=['horsepower'])


#replacing the missing values by their mean 

imputer = SimpleImputer(missing_values=np.nan, strategy='mean')
imputer = imputer.fit(df.iloc[:, 1:7])
df.iloc[:, 1:7] = imputer.transform(df.iloc[:, 1:7])
df

~~~
{: .language-python}

## Standardization

Standardization is a transformation that centers the data by removing the mean value of each feature and then scale it by dividing features by their standard deviation. After standardizing data the mean will be zero and the standard deviation one. For this task, we can use Standard Scaler.
~~~

sc_X = StandardScaler(with_mean=False)
X = sc_X.fit_transform(X.drop(['car name'], axis=1))
~~~
{: .language-python}

## Normalization

Normalization is the process of scaling individual samples to have a unit norm. We need to normalize data when the algorithm predicts based on the weighted relationships formed between data points.

~~~
from sklearn.preprocessing import Normalizer
nm = Normalizer()
x_sc = nm.fit_transform(X)
X=pd.DataFrame(x_sc)
~~~
{: .language-python}

## Encoding categorical features

Sklearn’s machine learning library does not support handling categorical data. Therefore, it is important to convert categorical features to a numerical representation.

Label Encoding converts the labels into the numeric form. For Example: If a column in the data set contains the values {Chicago, Urbana, Springfield}. The can be mapped to 0, 1, 2.

However, the dataset contains multiple car model names which have a string as their datatype.Therefore, we use the OneHot Encoding technique.

~~~
from sklearn.preprocessing import OneHotEncoder
onehot = OneHotEncoder(dtype=np.int, sparse=True)
nominals = pd.DataFrame(
    onehot.fit_transform(X[['car name']])\
    .toarray())
nominals
~~~
{: .language-python}

## Discretization

Data discretization refers to a method of converting a huge number of data values into smaller ones so that the evaluation and management of data become easy. There are two forms of data discretization first is supervised discretization, and the second is unsupervised discretization. Supervised discretization refers to a method in which the class data is used. Unsupervised discretization refers to a method depending upon the way which operation proceeds.

~~~
from sklearn.preprocessing import KBinsDiscretizer 
disc = KBinsDiscretizer(
n_bins=6, encode='onehot',strategy='uniform')
disc.fit_transform(X)
~~~
{: .language-python}
