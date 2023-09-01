# Ai Academy Capstone Group 4
Presented by Brian Gorbea, Kelvin Cupay, Robert Cofer, Rob Masters, Ryan Lazar

## Overview
Using Explanatory data analysis(EDA) and statistical methods we are going to advice Computing Vision how the best way to jump start their new movie studio, called 'Computing Vision Entertainment'. We used sqlite3 in pandas to query the datasets given and hypothesis testing to evaluate our findings. Essentially, we are generating insights for their business and stake holders by making a two part suggestion, one is the early stage of the movie studio and scalability after several years.

## Business Understanding: 

Goals: The business question we are going to answer
Assumption : The parent company 'Computing Vision' does not have much backgrounk in creating movies.
1. Best investment in order to quick start the revenue of new movie studio 'Computing Vidion Entertainment'
2. Best investment in order to scale the business and future ventures in the business industry

This notebook will drive deeper into how we utilize the data sets to create meaningful visualizations and aggregrations in order to achieve our goals listed above.

We will also create hypothesis test to evaluate our findings and reccomendations which are based in scietific & mathematical reasonings. The reccomendation for the *head of Computing Vision's new movie studio* and help him decide which films to create the best film in terms of profits and appreciation.

### Real World Application(real-world problem): Today less people are going to the theatres and watching movies. Maybe Hollywood has gone stale and have stagnanted with their ways of creating movies, maybe through insights of what is most profitable for a new and small scale movie studio someone can use this information to create and start their new movie business.REVISIT)

## Stakeholders:(REVISIT CHECK WITH ROB)
- `Investors`: Can identify by profits if rate on investment(ROI) is significant for them to invest in Computing Vision Entertainment
- `Computing Vision(Parent Company)`: Is it worth it to make 
- `Critics`: Is this new movie studio just for profits or they actually want to create movies that are well liked
- `Fans`: Do we like the movies from this mobie studio
- `Potential future fans`: Repuation of this new in coming movie studio
- `Competing fans`: How well will this Computing Vision Entertainment handle the competing movie studios

## Data Undertanding: 
The data set comes from several sources where some are compressed into CSV(comma-separated values) or TSV(tab-separated values). The data sets listed below are from these respectable sources: [Box Office Mojo](https://www.boxofficemojo.com/), [IMDB](https://www.imdb.com/), [Rotten Tomatoes](https://www.rottentomatoes.com/), [The MovieDB](https://www.themoviedb.org/), [The Numbers](https://www.the-numbers.com/).

Here is a list of the data sets use:
- `bom.movie_gross.csv.gz`: each record is a movie with a title(object), domestic_gross(object), foreign_gross(float), and year released(int)
- `im.db.zip`: 
- `rt.movie_info.tsv.gz`:
- `rt.reviews.tsv.gz`:
- `tmdb.movies.csv.gz`:
- `tn.movie_budgets.csv.gz:`

# Data Prep
Task: Exploring what types of films are current doing the best at the box office using different samples of available data(we are looking at profitability).

# Data Pulling and Cleaning
Data is pulled from the csv, tsv and database files. Data is columns are renaimed to match each other. Budget and gross data is turned into a readable value by the program to create a new column called profit for each entry.


# 1st Visualization
This graph shows the top 10 studios that have the highest profit on average. It was created by combing the two dataframes movie_gross_df and movie_budgets_df, calculating profit, and then grouping by the studio. The values are the average profit (mean).

[1st Visualization](../../images/Image_One.png)

# Creating New Columns Continued
The genre data from the database has more than one genre per movie stored. The solution was to seperate the genres and pull the first genre that appears and mark that as the primary genre.


# Sorting data
The data is being sorted by most profitable to least profitable. One it has been sorted the data grabs the top 10 results from the list. The top ten list is then used for vizualiation later for top ten profitable movies.

# Creating Data
Data is being merged and calculated to represent the average based on the primary genre of a movie.


# 2nd Vizualization - Top Ten Profitable Movies with a Buget Under 10M
The vizualization is used to get the average profit based on genre while mantaining a budget under 10M.

The data is merged on movie names then sorted to only include production budgets under 10m. Once the data has been sorted the mean value for the primary genre is calculated and is sorted based on the total profit. What this produces is a dataframe with two columns. The first column is the name of the genre and the second column is the averaged profit that genre made in the past 50 years while also maintaing a budget under 10m.

![image-4.png](attachment:image-4.png)



# 3rd Vizualization - Top Average Profits by Genre
The vizualization is used to get the average profit based on genre. This data can represent which genres don't do well and what to potentially avoid. Such as making a Western movie may not produce results.

![image-3.png](attachment:image-3.png)


 
 # Middle : Methodology
* Data Understanding
    
* Data Analysis
    * 3 visualizations
* Statistical Inference

* Rationale
    * For example, why are you using hypothesis testing rather than just a graph?
    * What about the problem or data is suitable for this form of analysis?
    * For a data science audience, this includes your reasoning for the changes you applied and choices you made while building confidence intervals and/or hypothesis tests.
 
 
 # End
* Recommendations
    * 3 reccs
* Next Steps
* Thank You
* This slide should include a prompt for questions as well as your contact information (name and LinkedIn profile)


# End of Note book

# Grading
* Attention to Detail (20%)
* Data Communication (20%)
* Authoring Jupyter Notebooks (20%)
* Data Manipulation and Analysis with pandas (20%)
* Statistical Communication (20%)
