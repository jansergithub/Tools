
https://github.com/pandas-profiling/pandas-profiling


pandas-profiling

Generates profile reports from a pandas DataFrame. The pandas df.describe() function is great but a little basic for serious exploratory data analysis.

For each column the following statistics - if relevant for the column type - are presented in an interactive HTML report:

    Essentials: type, unique values, missing values
    Quantile statistics like minimum value, Q1, median, Q3, maximum, range, interquartile range
    Descriptive statistics like mean, mode, standard deviation, sum, median absolute deviation, coefficient of variation, kurtosis, skewness
    Most frequent values
    Histogram
    Correlations highlighting of highly correlated variables, Spearman and Pearson matrixes

Demo

Click here to see a live demo.  
https://nbviewer.jupyter.org/github/JosPolfliet/pandas-profiling/blob/master/examples/meteorites.ipynb  


Installation  
Using pip

You can install using the pip package manager by running

pip install pandas-profiling

Using conda

You can install using the conda package manager by running

conda install -c anaconda pandas-profiling

From source

Download the source code by cloning the repo or by pressing 'Download ZIP' on this page. Install by navigating to the proper directory and running

python setup.py install


