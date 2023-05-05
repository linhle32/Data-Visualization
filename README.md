# Tutorials on Data Visualization

This repository includes some tutorials on data visualization using Matplotlib, Pandas, and Seaborn. This is not a introductory tutorial, you should be somewhat familiar with statistics, Python, NumPy, and Pandas to follow comfortably.

## Contents so far:

1. Histogram
    - Simple histogram
    - Histogram with normal/density curves
    - Side-by-side histograms
    - Side-by-side density curves
    - Multiple histograms
    - Multiple density curves
2. Box plot
    - Simple box plot
    - Multiple box plots
    - Side-by-side box plots
3. Bar chart
    - Statistics bar chart
    - Frequency bar chart
    - Grouped bar chart
    - Stacked bar chart
4. Scatter plot
    - Simple scatter plot
    - Multi-dimension scatter plot
    - 3D scatter plot
5. Violin plot
    - Simple violin plot
    - Side-by-side violin plot
    - Stratified violin plot
6. Time series plot
    - Simple line plot
    - Line plot with moving average
    - Line plot with moving average and confidence interval
    - Multiple-line plot
    - Stock chart: candlestick plot
7. Regression plot
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
