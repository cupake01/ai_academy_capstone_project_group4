# Ai Academy Capstone Group 4
Presented by Brian Gorbea, Kelvin Cupay, Robert Cofer, Rob Masters, Ryan Lazar

Created & Consolidated by Kelvin, Brian, and Robert

## Notebook Structure
1. Overview
2. Business Understanding
* Include stakeholder and key business questions
3. Data Understanding and Analysis
* Source of data
* Description of data
* Three visualizations (the same visualizations presented in the slides and notebook)
4. Statisical Communication & Data Analysis
* Results of statistical inference
* Interpretation of these results in the context of the problem
* Hypothesis testing
5. Conclusion
* Summary of conclusions including three relevant findings
* Future Works

# Overview
Using Explanatory data analysis(EDA) and statistical methods we are going to advice Computing Vision how the best way to jump start their new movie studio, called 'Computing Vision Entertainment'. We used sqlite3 in pandas to query the datasets given and hypothesis testing to evaluate our findings. Essentially, we are generating insights for their business and stake holders by making a two part suggestion, one is the early stage of the movie studio and scalability after several years.

# Business Understanding: 

Goals: The business question we are going to answer
Assumption : The parent company 'Computing Vision' does not have much backgrounk in creating movies.
1. Best investment in order to quick start the revenue of new movie studio 'Computing Vidion Entertainment'
2. Best investment in order to scale the business and future ventures in the business industry

This notebook will drive deeper into how we utilize the data sets to create meaningful visualizations and aggregrations in order to achieve our goals listed above.

We will also create hypothesis test to evaluate our findings and reccomendations which are based in scietific & mathematical reasonings. The reccomendation for the *head of Computing Vision's new movie studio* and help him decide which films to create the best film in terms of profits and appreciation.

## Real World Application:
Today less people are going to the theatres and watching movies. Maybe Hollywood has gone stale and have stagnanted with their ways of creating movies, through our insights of what is most profitable for a new and small scale movie studio someone can use this information to create and start their new movie business. `Note:` that our client is a tech company, this may hinder start-ups.

## Stakeholders:
- `Investors`: Can identify by profits if rate on investment(ROI) is significant for them to invest in Computing Vision Entertainment
- `Computing Vision(Parent Company)`: Is it worth it to make 
- `Critics`: Is this new movie studio just for profits or they actually want to create movies that are well liked
- `Fans`: Do we like the movies from this mobie studio
- `Potential future fans`: Repuation of this new in coming movie studio


## Data Undertanding: 
#### Description of data:
The data set comes from several sources where some are compressed into CSV(comma-separated values) or TSV(tab-separated values). The data sets listed below are from these respectable sources: [Box Office Mojo](https://www.boxofficemojo.com/), [IMDB](https://www.imdb.com/), [Rotten Tomatoes](https://www.rottentomatoes.com/), [The MovieDB](https://www.themoviedb.org/), [The Numbers](https://www.the-numbers.com/).

Here is a list of the data sets use:
- `bom.movie_gross.csv.gz`: 
- `im.db.zip`: 
- `rt.movie_info.tsv.gz`:
- `rt.reviews.tsv.gz`:
- `tmdb.movies.csv.gz`:
- `tn.movie_budgets.csv.gz:`

# Data Prep
Task: Exploring what types of films are current doing the best at the box office using different samples of available data(we are looking at profitability).

# Data Pulling and Cleaning
Data is pulled from the csv, tsv and database files. Data is columns are renaimed to match each other. Budget and gross data is turned into a readable value by the program to create a new column called profit for each entry.

# Data Organizing, Data Merging, Data Formatting, Data Calculation

Change the column "title in the bom.movie dataframe. This will then allow us to merge both dataframes on that column.

After the column name was changed we can now merge and begin our data exploration.

Before we can work with the numbers in the columns we have to remove the $ and any spaces that may exist.

Now we create a profit column in the dataframe and we calculate that by subtracting the "production_budget" column from the "worldwide_gross" column. It is a large number so we then divide by 1,000,000 to change it out of scientific notation.

## 1st Visualization
This graph shows the top 10 studios that have the highest profit on average. It was created by combing the two dataframes movie_gross_df and movie_budgets_df, calculating profit, and then grouping by the studio. The values are the average profit (mean).

![Image](images/Image_One.png)

# Creating New Columns Continued
The genre data from the database has more than one genre per movie stored. The solution was to seperate the genres and pull the first genre that appears and mark that as the primary genre.

# Sorting data
The data is being sorted by most profitable to least profitable. One it has been sorted the data grabs the top 10 results from the list. The top ten list is then used for vizualiation later for top ten profitable movies.

# Creating Data
Data is being merged and calculated to represent the average based on the primary genre of a movie.


# 2nd Vizualization - Top Ten Profitable Movies with a Buget Under 10M
The vizualization is used to get the average profit based on genre while mantaining a budget under 10M.

The data is merged on movie names then sorted to only include production budgets under 10m. Once the data has been sorted the mean value for the primary genre is calculated and is sorted based on the total profit. What this produces is a dataframe with two columns. The first column is the name of the genre and the second column is the averaged profit that genre made in the past 50 years while also maintaing a budget under 10m.

![Image](images/Image_Two.png)



## 3rd Vizualization - Top Average Profits by Genre
The vizualization is used to get the average profit based on genre. This data can represent which genres don't do well and what to potentially avoid. Such as making a Western movie may not produce results.

![Image](images/Image_Three.png)


## Data Analysis(start)
Clean out the new dataframe gross budgets to modify the worldwide_gross and production budget values to ensure we can calculate profit. This starts by removing '$' and ',' from the cells and then converting the data into float.

Clean the data again just for the frequency analysis. Since we dont need studio information, it is better that we use just the movie_budgets_df dataframe as we get better quality data in regards to profits as there isn't data lost from the merge.

Calculate profits and change the vaules of profit and production budget to be represented in the millions. This is just for the movie budget dataframe.

 Analysis on profit

General analysis about profits. We use this dataframe because it has better data quality.

count    5782.000000
mean       59.899704
std       146.088881
min      -200.237650
25%        -2.189071
50%         8.550286
75%        60.968502
max      2351.345279
Name: profit, dtype: float64

## Creating histogram for profit

Below we create a histogram for profit. This provides us with a general anaysis of where profit lines up for all films, generally showing us the types of returns we can expect.

![Image](images/Image_Four.png)

## Null Hypothesis:
Typically there is no relationship between A and B. In our case, profit has no relationship to any of the top 3 occuring studios.

## Alternative Hypothesis:
The alternative hypothesis is traditionally thought of when creating a hypothesis for an experiment. In our case, profit has a relationship to all or some of the top 3 occuring studios.

## General anaylsis for developing hypothesis testing
Here we check for all unique studios in order to get an idea of all the potential studios to emulate.

Check to see the total count of each studio. We are focusing on high studio frequency in the dataset to get an accurate pvalue test, as studios like Trib or FCW will not provide us with accurate results.

## Hypothesis testing
In this code we run a loop to check 3 different top occuring studios independently to see if they are significant to profit. We create a place to store the studios, and then create the loop which counts studios, sorts them by an occurrence count in decending order and then grabs the top 3 to do a p-value test independently of each other for studio and profit. One other condition we check for is if there is a null value for studio and drop it from the results.

Top 3 studio occurances in the dataset significance with profit:
Uni.: 3.688020261558896e-10
Fox: 9.610055205557015e-17
WB: 4.328957530102738e-10

## Rejecting the null hypothesis: 
Based on the results of each of the three studios being significant at the 95% threshold, we reject the null and accept the alternative that any of the top 3 occuring studios will help with profit.

## Confidence Intervals
Here in the code below we check the confidence interval for profit for films with a production budget under 10 million dollars.
The 95.0% confidence interval for movie budgets under 10 million represented in millions is: (15.59, 26.02)

Do the same thing as above but for films with a production budget over 10 million dollars.
The 95.0% confidence interval for movie budgets under 10 million represented in millions is: (115.68, 142.52)
 
## Conclusion
# Business Recommendations
When we started to work and explored data we thought it was Computing Vision's best interest to have a 2 phase recommendation. The first one being the short term phase(0-5 years) which consist of limiting capital expenditure to under 10 million dollars. As we gain familiarity of the movie industry (5-10 years in the future) and grow our entertainment portfolio, we can expand into higher grossing films such as creating movies over 10 million dollar production budget.

We chose 10 million as a threshold number since we strongly believe that this is feasible capital expenditure for a tech company like Computing Vision. We also saw that 10 million is 25th percentile above and below 50th in production budget which makes it safe and retains market viability.

This provides us the general statistical analysis in order to justify a 10 million dollar production budget limit for a new movie studio. This would put us above the bottom quarter but keep our movies viable with the broader film market.

count    5.782000e+03
mean     3.158776e+07
std      4.181208e+07
min      1.100000e+03
25%      5.000000e+06
50%      1.700000e+07
75%      4.000000e+07
max      4.250000e+08
Name: production_budget, dtype: float64

## 1. Short Term Reccommendation
Make horror movies with a 10 million budget or less in the short-term. The genre itself has the highest profits on average for a budget under 10 million and also consists of 9 out of the top 10 most profitable low budget films.

## 2. Growth Phase
Branch into Sci-Fi, Adventure, and Animation Films once you are established. While these are the top profiting genres we do caution about high production budgets.

## 3. Emulating A Studio
Since we have found that they can influence profits, Emulating the right studio is a key to jumpstarting a movie studio based on our findings. The top 3 we recommend are Pixar, BV (Buena Vista International), GrtIndia

## Future Works
The scope of the task allowed only Exploratory Data Analysis(EDA) and Hypothesis Testing. We hope in the future we can use Regression and Machine Learning Algorithms to improve and validate our findings. Here are some of the example of what we would like to do in the future.

1. Look into other variables that have effects on profit (Director, Revenue, Ratings)
2. Regression testing to determine data relationships
3. Predictive modeling with machine learning
4. Perform thorough risk analysis for upcoming projects
5. Risk evaluation on genres


## PDF'S
[Presentation](Top_Quality_Group_Presentation.pdf)
[Notebook_PDF](Capstone_Final_Notebook_Group4_Jupyter_Notebook.pdf)

# End of Note book: Thank you so much for reading to this point!