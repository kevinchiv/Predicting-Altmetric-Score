# Predicting Altmetric Score

## Description: 
In an age of information, we are constantly presented with too much information to digest at once. The same is true for the sciences where too are many research papers to read. Journals like Nature help highlight important papers, but it can be difficult to tell how impactful a particular paper will be. Enter the Altmetric score. It is a metric that measures the impact factor of an article, based on factors like the number of times it has been viewed or cited. 

## Objective: 
Not every paper has an Altmetric score. 

The goal of this project is to use linear regression to predict Altmetric scores for papers.

## Methodology: 
I used BeautifulSoup and Selenium to web scrape info on research papers published on Nature from the year 2009 to 2018. 

Here are the features I started with:
- title_length, the length of the title of the paper		
- num_times_cited, the number of times the paper was cited	
- abstract_length, the number of words in the abstract of the paper	
- page_length, how many pages long the paper was	
- fig_count, the number of figures in the paper	
- ref_cnt, the number of references that were cited in the paper	
- num_authors, the number of authors that were credited on the paper	
- top100, the number of institutions that the authors belonged to that were within the top 100 biological U.S. universities	
- other, the number of institutions that the authors belonged that were not within the top 100 biological U.S. universities		
- num_institution, the number of institutions that the authors belonged
- year, the number of years since the paper has been published

I used cross-validation with OLS, Ridge, and LASSO to help decide on the best features and model.


## Results: <br>
The best model was OLS with a R^2 of 0.56 on train and 0.53 on test.

Ridge and LASSO fared no worse, but offered no additional benefit. 

The results indicate that: <br>
- for every additional time a paper is cited, a paper increases its Altmetric score by 1.75 
- for every additional reference used, a paper increases its Altmetric score by 0.99
- for every additional author that worked on the paper, a paper increases its Altmetric score by 1.09 
- for every additional institution involved, a paper increases its Altmetric score by 1.15 
- for every additional year since publication, a paper increases its Altmetric score by 0.62

Obviously, some recommendations are more feasible than others. Using additional references and involving more people is one way to increase article impact. Participating in highly distinguished labs and conferences is helpful in generating these type of connections.
However, it may minimize impact from personal contributions as well.
