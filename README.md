

# Movie Data Analysis Project

![Hail Ceaser](./Images/Hail_Ceaser.jpg)

**"Our Big Fat Greek T Distribution"**

**Authors**: [Rachel Goldstein](mailto:rachelhgoldstein1@gmail.com), [Nick Kai](mailto:nhknicholas@gmail.com), [Reyn Chagami](mailto:rchagami17@gmail.com)

## Overview

This project analyzes [data]([https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses](https://www.kaggle.com/datasets/ashpalsingh1525/imdb-movies-dataset)) from IMDB which has data from over 10,000 movies from all over the world from various genres over the last 35 years.

## Business Problem

![img](./Images/indiana.jpg)


We have been charged with exploring what types of films are currently doing the best at the box office by a new movie studio. We have been asked to translate our findings into actionable insights that the head of our company's new movie studio can use to help decide what type of films to create.

## Data

The IMDB database covers information regarding movies from the last 35 years, including Genre, Crew, Revenue, and IMDB score, to name a few of the categories.

## Methods

This project uses a variety of data cleaning methods to organize and subset the data such as: 
- Dropping irrelevant properties.
- Filling in null values.
- Filtering and Creating new categories to analyze different Genres

  
## Results

**This is our results when we decided to break down the average profit per genre**
<p float="left">
  <img src="Images/avg_profit_per_genre_multiplot.png" width=70% height=70% /> 
  <img src="Images/Documentary_Revenue_Count.png" width=45% height=45% />

**Documentaries were the most normally distributed while also being on a large scale**

<p float="left">
  <img src="Images/avg_profit_per_genre.png" width=70% height=70% /> 

# Release Month
Regarding the release month, we found that although most genres have remarkably low margins in September, Documentaries scored particularly well 

<p float="left">
  <img src="Images/profit_vs_release_month_boxplot.png" width=70% height=70% /> 
  <img src="Images/median_profit_by_genre_release_month.png"/>

```
revenue_means = {}

for genre in genre_list:
    mean = imdb_movies[imdb_movies[genre] == True]['revenue'].mean()
    revenue_means[genre] = mean
revenue_means
{'Action': 270245339.678607,
 'Adventure': 340548869.7905797,
 'Comedy': 239921005.32046333,
 'Family': 347019522.43114257,
 'Crime': 167925962.76549864,
 'Thriller': 194499578.42893812,
 'Animation': 401238719.48764336,
 'Horror': 199979449.0441838,
 'Fantasy': 330199644.1764089,
 'Romance': 188007507.25579512,
 'Science Fiction': 306093486.91767675,
 'Documentary': 504977146.8864198,
 'History': 189244794.9480176,
 'Music': 282985112.09090906,
 'Mystery': 221578726.14369604,
 'Drama': 181894333.93492872,
 'War': 182858934.16183206,
 'Western': 220669465.25084746,
 'TV Movie': 471846708.54651165}
```

```
 revenue_medians = {}

for genre in genre_list:
    median = imdb_movies[imdb_movies[genre] == True]['revenue'].median()
    revenue_medians[genre] = median
revenue_medians_sorted = sorted(revenue_medians.items(), key=lambda x: x[1], reverse=True)
revenue_medians_sorted 

 [('Documentary', 542233172.2),
 ('TV Movie', 469568522.4),
 ('Animation', 392188196.0),
 ('Family', 319715683.0),
 ('Adventure', 250191298.7),
 ('Fantasy', 243434798.2),
 ('Science Fiction', 188584535.2),
 ('Music', 167362748.0),
 ('Action', 161929216.5),
 ('Comedy', 146599211.4),
 ('Western', 106515310.0),
 ('Mystery', 98677816.0),
 ('War', 97523020.0),
 ('Romance', 97374152.0),
 ('Horror', 81831866.0),
 ('Thriller', 80073583.0),
 ('History', 76665507.0),
 ('Crime', 71928453.0),
 ('Drama', 69387375.5)]
```


## Conclusions

Our 3 Actionable insights that we recommend are as follows.

#1
- Create a Documentary film
- Documentaries had some of the highest rates of profit while also having the lowest risk of negative revenue
- There seems to be some space in the market for more documentaries
- We also recommend making a Documentary in the Music subgenre as they seem to have some of the highest ratings and revenue scores across the board

#2
- Release it in September if possible, as Documentaries released during this month tend to have the highest average revenue
- If it is not possible to release in September, December, and November, also have a high rate of average revenue

#3
- Spend at least ______ on your documentary
- There seems to be a positive correlation that if you spend at least ____ on your documentary, it has a higher likelihood of profitability
- Do not spend more than ______ on your documentary, as it seems budget has diminishing returns on profit.

  

### Next Steps

**After this analysis, we are left with some questions**

The biggest question is what effect crew has on a Documentary.
-**Is there a documentary director or narrator who tends to make more money on average than others?** We began looking into what subgenres have the highest gross revenue, as well as were the most successful overall, but is there a possible correlation with the cast as well?

-**What types of Movies score the best?** One next step we would hope to take is to use machine learning to help create a predictive model of what types of movies would be most successful and create the most profit with what actors.


## For More Information

See the full analysis in the [Jupyter Notebook](), review this [presentation](), or take a look at our [Tableau Dashboard](https://public.tableau.com/app/profile/nicholas.kai3061/viz/FinalDashPhase2Project/Dashboard1?publish=yes).

For additional info, contact Rachel Goldstein at [rachelhgoldstein1@gmail.com](mailto:rachelhgoldstein1@gmail.com), Nick Kai at [nhknicholas@gmail.com](mailto:nhknicholas@gmail.com), or Reyn Chagami at [rchagami17@gmail.com](mailto:rchagami17@gmail.com).

## Repository Structure
