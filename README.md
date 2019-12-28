# Analyze A/B Test Results
The project aimed at understanding the results of A/B Test run by an e-commerce website(sample). Hypothesis and Regression tests were used.

## Introduction
(as provided by Udacity)</br>
For this project, you will be working to understand the results of an A/B test run by an e-commerce website. The company has 
developed a new web page in order to try and increase the number of users who "convert," meaning the number of users who 
decide to pay for the company's product.

## Goal
Your goal is to work through this notebook to help the company understand if they should implement this new page, 
keep the old page, or perhaps run the experiment longer to make their decision.

## Data 
- user_id	- integer
- timestamp	- datetime
- group	- control or experiment
- landing_page - old_page or new_page
- converted - boolean

## Project Description
The code has been discussed in detail with reasoning in the `Analyze_ab_test_results_notebook.ipynb` Jupyter notebook.</br>
The project was completed in three parts:
  - Probability
  - A/B Test
  - Regression
  
- Part 1. Probability
  - Primary Exploratory Data Analysis was performed to find the unique users, proportion of users converted,
and the number of times the new_page and treatment don't line up.
  - Removed the rows where where treatment is not aligned with new_page or control is not aligned with old_page.
  - Removed the duplicate `user_id`s to decrease the redundancy of data.
  - Calculated the probability of an individual converting regardless of the page they receive.
  - Calculated the probability of an individual in `control` group converting to new_page.
  - Calculated the probability of an individual in `treatment` group converting to new_page.
  - Calculated the probability that an individual received the new page.
  
- Part 2. A/B Testing
  - Hypotheses were set as per requirement:
    - Null hypothesis: H(0)= p(new) <= p(old)
    - Alternative hypothesis: H(1) = p(new) > p(old)
  - Calculated the p-value and concluded that the we fail to reject the null hypothesis.
  
- Part 3. Regression Approach
  - Logistic Regression was performed where the dependent variable was `coverted` and independent varaible used was `ab_page`. 
  The new column `ab_page`(boolean) was engineered to display only the true values in `treatment group`.
  - Further new column of `countries` was added, to check whether the conversion of a page is influenced by user's location.
  - By setting the hypotheses and performing Logistic regression, it was concluded that user's location does not influence the
  conversion of a page.
  
- Lastly, it was concluded that we **fail to reject the null hypothesis** for the above perfromed A/B Tests. That means **the new page must not be launched**.
