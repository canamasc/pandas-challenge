# pandas-challenge
Georgia Tech Data Science Bootcamp

Three trends observed from data analysis outcomes:

1. While male players make up most of the purchase data and over 80% of the revenue (either because they buy more frequently than women / others or because the total player population is just
   majority male), female and other/non-disclosed gendered players actually spend more money on average than their mail counterparts, and buy slightly more expensive items.

2. Similarly, while the mid-tier age groups (15-24 years old) account for over 63% of all purchases, these age groups actually spend less money on average per person than age groups closer to the extremes, such as 35-39 age group and <10 age group.
   The high average total purchase amount for players <10 years old is possibly explained by the fact that they could be using a parent's money (generally more afluent and willing to spend small amounts than perhaps players in the 10-24 years age group).
   
3. In general, the top spending players got to their positions by buying some of the more expensive items (all of top spenders' average purchase prices are well over the overall average item price of $3.05) - not necessarily making lots of individual purchases of less expensive items.

CODE WALK THROUGH: 

Pandas is used to analyze this game purchasing dataset. 
It is first checked to ensure no fields are empty or null.
Then we start to pull some general info from the data:

    - Number of total players = number of unique SNs (screen names)
    
    - Number of unique items = number of unique Item IDs, along with their average and total prices (found using .mean() and .sum() aggregate functions)
    
    - Breakdown of players' purchases by gender; using .groupby() method on the data frame to get aggregate function values for specific genders
    
    - Breakdown of purchases by age group; using .cut() to split data into age bins and .groupby() to get counts, average prices, and total purchase amounts by age group
    
    - Top 5 Spenders = Use .count() and .mean() to get purchase counts and average prices for all players, and sort them by .sum() to see players that spend the most
    
    - Most popular items = items that appear the most times in the data set, found by using .value_counts() method on Item ID
    
    - Once top 5 popular items are found, aggregate functions .sum() and .mean() are used on original data set to get average item price and total revenue per item, then these 2 results are merged
    
    - Most profitable items are found very similarly = sort to get top 5 by total revenue per item, and use Item ID and Item Name as indeces to match with original dataset to pull aggregate info such as average item price and purchase count
    
Results tables are displayed using Jupyter Notebook, so we just write the name of the dataframe in a new line to get the cell to print it. Formatting is included to display monetary amounts properly and to turn series into dataframes so that they print nicely.
