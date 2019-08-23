# craigslist-filter
jupyter notebook data analysis with visualizations, tables and statistics for craigslist used car data. The notebook also features a lot of data cleanup methods. 
Taking a closer look at low priced used cars on craiglist
Focused on cars worth less than $20,000. 
Data on Kaggle: https://www.kaggle.com/austinreese/craigslist-carstrucks-data

CRISP-DM approach to Exploratory Data Analysis
1. Business Understanding
- What is the most common car for sale?
- What car gives the best value? Balance between price and mileage
- Where can we find the best value cars?
2. Data Understanding
- 547,000 lines of cars for sale
- each line has a unique car for sale
- 22 columns
- columns of interest: price, location, description, year, manufacturer, make, odometer, desc
- take a look at cars priced less than $20,000. Research shows this is the popular price range for buying and selling cars (car flipping). Clean up the data and find insights for the questions above.
3. Prepare Data
- eliminate odometer reading of zero, it's incorrect. Ex: Row 21365
- eliminate cars worth 0 or 1 dollars - ad clickbait
- remove postings about leases by removing year greater than 2015 and price less than 4000
- eliminate cars worth more than 20k, not relavant to car flipping focus
- eliminate salvaged titles
- inaccurate odometer readings due to used car dealerships and people not listing correctly, need to eliminate low mileage
- some lines are cars wanted ads. need to eliminate these. search for 'wanted', 'looking to buy', 'I buy cars' in the desc
- manufacturer column has missing data. Fill it in using data from the 'make' column
- if two descriptions match, eliminate one. duplicate entry
4. Data Modeling
- plots and charts showing descriptive data. 
- bar chart comparing most common makes for sale
- box plots showing spread of prices per make
- map of country showing concentration of used cars for sale per state. 
5. Evaluate Results
- most common car for sale is Chevy Silverado, followed closely by Ford F-150
- Corvette seems like the best valued car, highest median price with some available well below market price
- California has the most cars for sale, while Rhode Island has the cheapest used cars for sale. 
6. Deploy

Libraries Used:
from __future__ import division = to do division in a Jupyter notebook box
import numpy as np = for data handling and plotting
import pandas as pd = for data handling and data manipulation
import matplotlib.pyplot as plt = for plotting
import matplotlib.cm as cm = for plotting
import seaborn as sns = for plotting
import os = for finding files
from mpl_toolkits.basemap import Basemap = for plotting on a map
%matplotlib inline
import plotly = for plotting on a map

Motivation for the project:
Craiglist is a great place to find a used car at a great price. There isn't one central location to find all craiglist data and users can only search Craigslist one region at a time. This project allows users to see macro level craigslist details to see how they compare to other regions, what constitutes a good deal and where to go for better deals. Also it gave me a chance to use the craigslist filter which I may use in my future car searches. 

Files in the Repository:
Art of the craigslist deal.ipynb = contains all cleanup, manipulation, and analysis of the craigslist filter data. 
