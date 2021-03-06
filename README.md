# Create and Optimize an Algorithmic Trading Bot

*Module 14 Challenge Assignment *

---

## Overview of the Analysis
---
  In order to remain competitive with other top financial advising firms, we aim to create an easily adaptable algorithmic trading bot. We will enhance the existing trading signals with machine learning algorithms that can adapt to new data.

  First we implement an algorithmic trading strategy that uses machine learning to automate the trade decisions. Next we adjust the input parameters to optimize the trading algorithm. Finally, we train a new machine learning model and compare its performance to that of the baseline model.


## Results
---

* Original Model - SVC classifier model from SKLearn's support vector machine (SVM) learning method, first 3 months of data used as training dataset, SMA: short window = 4, long window = 100:
  * The model's accuracy was assessed to be 55%
  * The model's precision was assessed to be 43% for (-1) and 56% for (1).
  * The model's recall was assessed to be 4% for (-1) and 96% for (1).

![cr_3months](/Images/cr_3months.jpg)    
![plot_3months](/Images/plot_3months.jpg)

### Adjust the size of the training dataset

* Alternative Model 1 - Same as original, except first 1 month of data used as training dataset:
  * The model's accuracy was assessed to be 55%
  * The model's precision was assessed to be 37% for (-1) and 56% for (1).
  * The model's recall was assessed to be 3% for (-1) and 96% for (1).

![cr_1month](/Images/cr_1month.jpg)    
![plot_1month](/Images/plot_1month.jpg)


* Alternative Model 2 - Same as original, except first 6 months of data used as training dataset:
  * The model's accuracy was assessed to be 56%
  * The model's precision was assessed to be 44% for (-1) and 56% for (1).
  * The model's recall was assessed to be 2% for (-1) and 98% for (1).

![cr_6months](/Images/cr_6months.jpg)    
![plot_6months](/Images/plot_6months.jpg)

* Alternative Model 3 - Same as original, except first 18 months of data used as training dataset:
  * The model's accuracy was assessed to be 56%
  * The model's precision was assessed to be 75% for (-1) and 56% for (1).
  * The model's recall was assessed to be 0% for (-1) and 100% for (1).

![cr_18months](/Images/cr_18months.jpg)    
![plot_18months](/Images/plot_18months.jpg)
    
### Question: What impact resulted from increasing or decreasing the training window?

  Accuracy and precision increased by increasing the training window. Recall increased for the (1) values, but decreased for the (-1) values.
  
### Adjust the SMA windows
  
* Alternative Model 4 - Same as original, except SMA windows changed to short window = 4, long window = 50:
  * The model's accuracy was assessed to be 54%
  * The model's precision was assessed to be 42% for (-1) and 56% for (1).
  * The model's recall was assessed to be 13% for (-1) and 86% for (1).

* Alternative Model 5 - Same as original, except SMA windows changed to short window = 25, long window = 100:
  * The model's accuracy was assessed to be 56%
  * The model's precision was assessed to be 44% for (-1) and 56% for (1).
  * The model's recall was assessed to be 4% for (-1) and 96% for (1).

* Alternative Model 6 - Same as original, except SMA windows changed to short window = 50, long window = 100:
  * The model's accuracy was assessed to be 54%
  * The model's precision was assessed to be 45% for (-1) and 56% for (1).
  * The model's recall was assessed to be 17% for (-1) and 83% for (1).

* Alternative Model 7 - Same as original, except SMA windows changed to short window = 15, long window = 75:
  * The model's accuracy was assessed to be 56%
  * The model's precision was assessed to be 45% for (-1) and 56% for (1).
  * The model's recall was assessed to be 6% for (-1) and 94% for (1).

### Question: What impact resulted from increasing or decreasing either or both of the SMA windows?

  Accuracy was pretty much unchanged by increasing or decreasing the SMA windows. Precision was also largely unchanged. Recall was a little more balanced between the two categories when the long window was decreased to 50 while leaving the short window unchanged (13% for (-1) and 86% for (1)), or increased the short window to 50 while leaving the long window unchanged (17% for (-1) and 83% for (1)).
  
![cr_long_short_window](/Images/cr_long_short_window.jpg)    
![plot_long_short_window](/Images/plot_long_short_window.jpg)  


* Alternative Model 8 - Logistic Regression linear model from SKLearn's linear model learning method, first 3 months of data used as training dataset, SMA: short window = 4, long window = 100:
  * The model's accuracy was assessed to be 52%
  * The model's precision was assessed to be 44% for (-1) and 56% for (1).
  * The model's recall was assessed to be 33% for (-1) and 66% for (1).

![cr_lr](/Images/cr_lr.jpg)    
![plot_lr](/Images/plot_lr.jpg)

### Questions: Did this new model perform better or worse than the provided baseline model? Did this new model perform better or worse than your tuned trading algorithm?

  The accuracy of this model (52%) was lower than the original model (55%) or the tuned model (56%). Precision was right in between the other two models at 44% for (-1) and 56% for (1), versus the original model being 43% for (-1) and the tuned model being 45% for (-1). Precision for the previous two models for (1) was 56% as it is with this logisitc regression model. Recall for this model was 33% for (-1) and 66% for (1) compared to the original and tuned models whose recall was and 6% for (-1) and 94% for (1) for both models.

## Summary
---
Given the lack of improvement in accuracy precision, and recall, I would not recommend that any of the alternative models be used. The original model itself is also not very accurate. I would reccommend that more alterations be made until improvement is found, or that an entirely different type of model be used for these predictions given the potential loss of capital were these models to be used in practice. 

### Original Model:
![plot_3months](/Images/plot_3months.jpg)

### Tuned Model:
![plot_long_short_window](/Images/plot_long_short_window.jpg)  

### Logistic Regression Model:
![plot_lr](/Images/plot_lr.jpg)

---

## Technologies

The application is written in Python using Pandas
The following packages are used:

Pandas - to write and run the program [Pandas documentation](https://pandas.pydata.org/docs/)

Pathlib - to create file paths [Pathlib documentation](https://docs.python.org/3/library/pathlib.html)

NumPy - for mathematical functions [NumPy documentation](https://numpy.org/doc/)

hvPlot - to create graphs [hvPlot documentation](https://hvplot.holoviz.org/)

matplotlib - to create graphs [matplotlib documentation](https://matplotlib.org/stable/contents.html)

DateOffset - to create a date range [DateOffset documentation](https://pandas.pydata.org/docs/reference/api/pandas.tseries.offsets.DateOffset.html)

SciKit-Learn - to train models, encode data, and scale data [SciKit Learn documentation](https://scikit-learn.org/0.21/documentation.html)


---

## Installation Guide

Install the Pandas package using the following command: 'import pandas as pd'

Install the Pathlib module using the following command: 'from pathlib import Path'

Install the numpy library using the following command: 'import numpy as np'

Install the hvPlot library using the following command: 'import hvplot.pandas'

Install the matplotlib library using the following command: 'import matplotlib.pyplot as plt'

Install the DateOffset package usi8ng the following command: 'from pandas.tseries.offsets import DateOffset'

Install the SciKit-Learn metrics libraries using the following commands: 'from sklearn import svm', 'from sklearn.preprocessing import StandardScaler', 'from sklearn.metrics import classification_report', 'from sklearn.linear_model import LogisticRegression'


--- 

## Usage

To run this program, clone the repository onto your computer, navigate to its source folder in your terminal and launch it using the command 'jupyter lab' then either run the entire program at once, or run the cells individually (in order) as you move through the file.

---

## Contributors
Susannah Slocum 
suzyslocum@gmail.com

---

## License

None
