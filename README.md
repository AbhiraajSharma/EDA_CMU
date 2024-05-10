# Exploring the CMU Movie Data Corpus

## Overview

This workbook explores the CMU Movies Dataset along with their plot summaries and a list of oscars. It explores the distributions, patterns and nuances of the dataset, and then answers a set of questions through analysis of the data.


## Table of Contents

- [Introduction](#introduction)
- [Data Sources](#data-sources)
- [Libraries Used](#libraries-used)
- [Plots](#plots)
- [Answering the questions](#answering-the-questions)

## Introduction

This project explores the CMU Movie Data Corpus and aims to answer the following questions through the use of NLP, graph networks and regression
1. Which actors are the most versatile in terms of number of other actors they have worked with?
2. How does the revenue relate to the sentiment conveyed by the plots of movies?
3. Are the oscars biased? Are they influenced by factors like gender, or ethnicity?

## Data Sources

1. movie.metadata.tsv
2. character.metadata.tsv
3. plot_summaries.txt
4. the_oscar_award.csv

## Libraries Used

The project uses the following libraries for exploration:
1. numpy
2. pandas
3. matplotlib.pyplot
4. networkx
5. statsmodels.api
6. seaborn
7. sklearn
8. spacy

---

## Plots

1. A histogram of movie releases by year
- The earliest movies are released around 1890, and releases per year grow consistently as we reach 2012.
- Post 1990 the growth becomes exponential as movie technology swithces to digital, turning movie-making into a mainstream industry. 
- Interestingly, we see that movie releases faced a decline in a few years leading to 1920, and for a few years after 1940, this could possibly be because world wars were fought during both these time brackets, and entertainment cinema would have been the last thing in the minds of people in such dire circumstances!    

2. A pie chart of character genders
- A significant 67.1% of all the characters in the database are men, and the remaining 32.9% are women.

3. A boxplot exploring the age distributions in both genders
- We see that the median age of actresses is quite lower than the median age of actors, with median age of male characters around 40 years, and median age of femal characters being  11 years lower at 29 years.

4. Regression analysis on comparing the runtime of a movie to the revenue it generates
- For each minute added to the runtime, the movie generates 1153280 dollars of additional revenue. 

5. Plotting residuals of the above regression analysis
- Mean of residuals is -1.87e-08, ideally the mean of residuals should be 0 if our assumption of the existence of a linear relationship between the movie runtime and revenue.

6. A bar plot of the top 10 most popular genres by number of movies release
- The genre with the highest number of movies released is Drama. It is followed by Comedy, Romance, Black-and-white, Thriller, Action, Short Film, World Cinema, Indie, and finally Crime Fiction

7. A similar plot of genres with the corresponding average revenue collected is made to understand which genres are the real cash-makers.
- The drama genre makes 

## Answering the questions

1. Which actors are the most versatile in terms of working with other actors?
Top 10 Actors by versatility
- Actor name: Samuel L. Jackson 	   	# actors worked with: 509
- Actor name: Anupam Kher 		        # actors worked with: 450
- Actor name: Amitabh Bachchan 		    # actors worked with: 372
- Actor name: Whoopi Goldberg 	    	# actors worked with: 369
- Actor name: Robert De Niro 		    # actors worked with: 364
- Actor name: Steve Buscemi 	    	# actors worked with: 354
- Actor name: Keith David        		# actors worked with: 349
- Actor name: John Goodman 		        # actors worked with: 338
- Actor name: Paresh Rawal 		        # actors worked with: 330
- Actor name: Christopher Walken 		# actors worked with: 329



2. How does the revenue relate to the sentiment conveyed by the plots of movies?
- By deriving the compound_sentiment from the plot summaries and plotting a scatter matrix of the sentiment and revenue, it is seen that movies with increasingly negative or positive sentiment in the plot summaries yield a larger revenue, with a neutral sentiment yielding lower revenue. 

3. Are the oscars biased? Are they influenced by factors like gender, or ethnicity?
- Through chi-square tests, we concluded that the Oscars are not biased by gender or ethnicity, and we also used logistic regression to show that even an actor's age is not an influence.

For gender:
- Null Hypothesis H0: There is no gender bias in the Oscar awards.
- Alternate Hypothesis H1: There is an gender bias in the Oscar awards.
- Chi-square statistic: 1.6887729080027762
- p-value: 0.1937628059033628
- There is no significant evidence to reject the null hypothesis, suggesting no gender bias in Oscar awards.

For ethnicity
- Null Hypothesis H0: There is no gender bias in the Oscar awards.
- Alternate Hypothesis H1: There is an gender bias in the Oscar awards.
- Chi-square statistic: 424.58466211325265
- p-value: 0.9562428913101307
- There is no significant evidence to reject the null hypothesis, suggesting no ethnicity bias in Oscar awards.
