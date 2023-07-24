# Microsoft Movie Analysis

![director](images/director_shot.jpeg)

**Author**: Trevor Mwangi

## Overview
***

This project uses exploratory data analysis(EDA) to generate insights for Microsoft. Microsoft have decided to create a new movie studio and want to find out what type of films to create. Data containing movie titles, their genres, grossing and number of votes has been used. Three datasets were used in this analysis to come up with recommendation on which combination of genres Microsoft should focus on in order to guarantee success. The analysis yielded that the combination Action, Adventure and SciFi was the most successful in terms of both domestic and foreign grossing and also according to the number of votes received. A combination of adventure with either animation or fantasy is also recommended as an alternative.


## Business Problem
***
Microsoft want to find out what type of films to create. Since they are new to the industry, they need to find out what type of films to create. This is a question of which genre to produce. The genres of the movies in the dataset will be analysed by grossing which is of the most important since that is how much a movie makes. Microsoft will definitely have an interest in this key variable. 



***

## Data Understanding

The data being used from this project was sourced from https://www.imdb.com/ which is a database for everything movies. The data contains movie titles, genres, both domestic and foreign grossing and is in the form of three files, one which contains the primary information about the movies such as titles, one which contains the rating information and the last file which contains information about the gross revenue. 

It is important to note that the domestic grossing relates to North America(USA, Canada and Puerto Rico). Foreign grossing is the grossing outside North America. The target variables of our data are the grossing columns which are numerical columns quoted in the US dollar.
***

## Data Preparation

To prepare the data for analysis, I first combined the new_file and the ratings_file to form the big_df dataframe using the tconst column as it was a unique identifier for both dataframes. I then joined the gross_file with the big_df to now form the main_file dataframe using the title as the unique identifier which was the dataframe used for this analysis.I then created a new column, total_gross which was an addition of the domestic- and the foreign_gross columns. For my analysis, studio, original title and the start_year columns were not relevant and were subsequently dropped.
***

An important issue was dealing with missing values. The columns genres, domestic_gross and foreign_gross all contained missing values. For the genres column, being a categorical column, I replaced the null values with the most occurring value which was Drama. This was appropriate since for categorical values it is impossible to use summary statistics to fill null values and is therefore common to impute the null values with the most occurring value.
***

For the domestic_gross I replaced the missing values with the median value. It is common practice to replace missing values for numerical columns using measures of central tendency. I chose the median because the distribution of this column is skewed and when the distribution is skewed it is better to fill missing values using the median rather than the mean.
***

The foreign_gross was of the wrong data type. It was an object rather than a float. The first step was to convert the column to the correct data type which was done using a defined function and a lambda function. For this analysis, I chose to select movies that had a grossing of not less than $1,000,000. This was appropriate because movies that had a very low grossing would be of no interest to Microsoft. Dropping them had no effect on the distribution of the gross revenue. Most of the elements that were dropped from the foreign_gross column were missing anyway so this did not particularly affect the foreign_gross column.
***
***

## Evaluation

The Most votes by genre and the total grossing graphs both show that the combination of Adventure, Action and SciFi are the most successful genres. It is also clear that the adventure genre cuts across almost all of the genre combinations. This especially yields a lot of success when paired up with an element of action or animation or fantasy.

To improve confidence in these set of results, next time I would;
- include the budget of the movies in order to arrive at a net figure since working with gross figures does not take into account the budgetary element of these movies which sometimes end up being quite large
- broken the data into the relevant years to examine whether there is a change in the top genres year by year or whether adventure, action, scifi would remain the top genre across several years. This will make it possible to determine whether audience tastes change over time which is important when considering such an expensive long term level of investment.


***

***



## Conclusions

This project yields three recommendations with regards to successful movie types;
make movies with the genre combination Action, Adventure, SciFi the number 1 priority. Movies with Adventure, Animation and Comedy can be produced as an alternative. Action, Adventure and Fantasy is included as the third recommendation just to diversify the portfolio but to ensure maximum succesS, the first film combination should be the main focus of the company. Adventure is a key component of the successful films and should therefore be a key feature in any of the films to be produced by Microsoft.

Some of the reasons why this analysis might not fully solve the business problem are due to the inherent limitations of the analysis. These include;
- who does the classification of the genres? Could they be biased?
- could a single film be classified differently by different audiences?
- is it necessary to include critic scores in the evaluation of the success of a film?
- is the classification of genres too broad and could a narrower approach yield different results?

Future analysis would include the budget spent of the films to see the success of the films based on a more financially sound measure such as net profit rather than the gross amount which might be misleading.
***





## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── MICROSOFT MOVIE STUDIO ANALYSIS.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```

