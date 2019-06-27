__1. Chartify — Python library that makes it easy for data scientists to create charts.__  
https://xkcd.com/1945/  

This, for me, is the winner of the year, for Python. If you are in the Python world, most likely you waste a lot of your 
time trying to create a decent plot. Luckily, we have libraries like Seaborn that make our life easier. 
But the issue is that their plots are not dynamic.  
  
Then you have Bokeh—an amazing library—but creating interactive plots with it can be a pain in the a**.   
If you want to know more about Bokeh and interactive plots for Data Science,   
take a look at these great articles by William Koehrsen:  


https://heartbeat.fritz.ai/top-7-libraries-and-packages-of-the-year-for-data-science-and-ai-python-r-6b7cca2bf000



Chartify is built in top of Bokeh. But it’s also so much simpler.

From the authors:
Why use Chartify?

    Consistent input data format: Spend less time transforming data to get your charts to work. All plotting functions use a consistent tidy input data format.
    Smart default styles: Create pretty charts with very little customization required.
    Simple API: We’ve attempted to make to the API as intuitive and easy to learn as possible.
    Flexibility: Chartify is built on top of Bokeh, so if you do need more control you can always fall back on Bokeh’s API.

Installation

    Chartify can be installed via pip:

pip3 install chartify

2. Install chromedriver requirement (Optional. Needed for PNG output):

    Install Google Chrome.
    Download the appropriate version of chromedriver for your OS here.
    Copy the executable file to a directory within your PATH.
    View directories in your PATH variable: echo $PATH
    Copy chromedriver to the appropriate directory, e.g.: cp chromedriver /usr/local/bin

Usage

Let’s say we want to create this chart:

import pandas as pd
import chartify

# Generate example data
data = chartify.examples.example_data()

Now that we have some example data loaded let’s do some transformations:

total_quantity_by_month_and_fruit = (data.groupby(
        [data['date'] + pd.offsets.MonthBegin(-1), 'fruit'])['quantity'].sum()
        .reset_index().rename(columns={'date': 'month'})
        .sort_values('month'))
print(total_quantity_by_month_and_fruit.head())

month          fruit     quantity
0 2017-01-01   Apple         7
1 2017-01-01  Banana         6
2 2017-01-01   Grape         1
3 2017-01-01  Orange         2
4 2017-02-01   Apple         8

And now we can plot it:

# Plot the data
ch = chartify.Chart(blank_labels=True, x_axis_type='datetime')
ch.set_title("Stacked area")
ch.set_subtitle("Represent changes in distribution.")
ch.plot.area(
        data_frame=total_quantity_by_month_and_fruit,
        x_column='month',
        y_column='quantity',
        color_column='fruit',
        stacked=True)
ch.show('png')

Super easy to create a plot, and it’s interactive. If you want more examples to create stuff like this:

And more, check the original repo:
spotify/chartify

Python library that makes it easy for data scientists to create charts. — spotify/chartify
github.com




