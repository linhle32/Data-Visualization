# Tutorials on Data Visualization

This repository includes some tutorials on data visualization using Matplotlib, Pandas, and Seaborn. This is not a introductory tutorial, you should be somewhat familiar with statistics, Python, NumPy, and Pandas to follow comfortably.

## Contents so far:

### Histogram
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/3cc3abc7-893e-4c9c-bba3-aedf586dc276)

    - Simple histogram
    - Histogram with normal/density curves
    - Side-by-side histograms
    - Side-by-side density curves
    - Multiple histograms
    - Multiple density curves
### Box plot
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/d76c17b6-42ff-4c77-8349-b33c4e995ef3)

    - Simple box plot
    - Multiple box plots
    - Side-by-side box plots
### Bar chart
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/1d46b307-cc9c-4426-90df-2afd61150c71)

    - Statistics bar chart
    - Frequency bar chart
    - Grouped bar chart
    - Stacked bar chart
### Scatter plot
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/241d8939-4b26-45db-b57e-d9d672b113c0)

    - Simple scatter plot
    - Multi-dimension scatter plot
    - 3D scatter plot
### Violin plot
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/78857972-40e5-455e-99aa-6f7f2f00d5bd)

    - Simple violin plot
    - Side-by-side violin plot
    - Stratified violin plot
### Time series plot
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/b53ee1d8-b3fa-4088-adba-12c3a9c90350)

    - Simple line plot
    - Line plot with moving average
    - Line plot with moving average and confidence interval
    - Multiple-line plot
    - Stock chart: candlestick plot
### Regression plot
![image](https://github.com/linhle32/Data-Visualization/assets/5643444/15ca8696-fd23-4669-80b7-b64f042b701f)

    - Linear regression plot
    - Polynomial regression plot
    - Log regression plot
    - Lowess regression plot
    - Logistic regression plot
    - Stratified regression plot
    
## Code template

I try to write the code similar to a template that you can adapt with minimal modifications. A small assumption is that your data is stored in a pandas dataframe named `data`. If that is satisfied, for complicated code cell, the first several variables are all you need to change to fit your use case. For example, in the cell below, you just need to change the name of the column of interest, the time column, the window size, and the plot title.

```
column = 'Adm'
time_col = 'datetime'
window_size = 7
title = 'Admitted patients from 2000 to 2011 with 7-day moving average'

ma_data = data[[time_col, column]].copy()
ma_data['ma'] = data[[column]].rolling(window_size, min_periods=window_size//2).mean()
plt.figure(figsize=(12,4))
plt.plot(
    ma_data[time_col], 
    ma_data[[column, 'ma']],
    linewidth=2,
)
plt.grid(visible=True)
plt.gcf().autofmt_xdate()
plt.title(title)
plt.show()
```
