# Module 14 Challenge Assignment 
---

## Create and Optimize an Algorithmic Trading Bot
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


## Summary
---
Given the lack of improvement in accuracy and loss, I would not recommend that any of the alternative models be used. The original model itself is also not very accurate at only 73%. I would reccommend that more alterations be made until improvement is found, or that an entirely different type of model be used for these predictions given the potential loss of investment capital. 


![original_model_summary](/Images/original_model_summary.jpg)
![original model_accuracy](/Images/original_model_accuracy.jpg)


---

## Technologies

The application is written in Python using Pandas
The following packages are used:

Pandas - to write and run the program [Pandas documentation](https://pandas.pydata.org/docs/)

Pathlib - to create file paths [Pathlib documentation](https://docs.python.org/3/library/pathlib.html)

TensorFlow - to generate deep learning models - [TensorFlow documentation](https://www.tensorflow.org/guide)

SciKit-Learn - to train models, encode data, and scale data [SciKit Learn documentation](https://scikit-learn.org/0.21/documentation.html)


---

## Installation Guide

Install the Pandas package using the following command: 'import pandas as pd'

Install the Pathlib module using the following command: 'from pathlib import Path'

Install the TensorFlow libraries using the following commands: 'import tensorflow as tf', 'from tensorflow.keras.layers import Dense','from tensorflow.keras.models import Sequential'

Install the SciKit-Learn metrics libraries using the following commands: 'from sklearn.model_selection import train_test_split', 'from sklearn.preprocessing import StandardScaler,OneHotEncoder


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
