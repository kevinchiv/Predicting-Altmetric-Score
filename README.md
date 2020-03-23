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
The best model was OLS with a R^2 of 0.59 on train and 0.53 on test.

Ridge and LASSO fared no worse, but offered no additional benefit. 

The results indicate that: <br>

The results indicate that: <br>
- for a 1% increase in the number of times cited, an article increases its Altmetric score by 0.47% <br>
- for every additional reference used, an article decreases its Altmetric score by -0.32% <br>
- for a 1% increase in the number of authors, an article increases its Altmetric score by 0.1% <br>
- for a 1% increase in the number of institutions involved, an article increases its Altmetric score by 0.15% <br>
- for every additional year, an article decreases its Altmetric score by 33.57% <br>

The Altmetric score uses the number of citiations as a factor, so its helpful to note that it is the most important factor <br>
Obviously, some recommendations are more feasible than others. <br>
Interestingly enough, year was the most negative factor, possibly suggesting that some articles become more obscure with time.
