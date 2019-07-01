# Prosper Loan Exploratory Data Analysis - Udacity Project


<br>

Introduction
============

This project is part of the Udacity Data Analyst Nano Degree Program and serves as practice for data visualization. This document explores a dataset containing information about <a href='https://www.prosper.com/'>Prosper's</a> loan data. Prosper is America’s first marketplace lending platform, with over $9 billion in funded loans.
This dataset contains 113,937 loans with 81 variables on each loan. 

We're specifically interested in learning about the types of loans that yield the highest returns, and knowing what are the features that correlate with the lowest Annual Percentage Rate (APR). We'll be looking at the relationships among multiple variables using summary statistics and data visualizations. 

**Borrower rate vs Borrower APR:**

When you take out a loan, your interest rate represents the interest percentage you will be charged for borrowing the money, but does not include origination fees, closing fees, documentation fees, and other finance charges. 
We're looking at APR over interest rates because APR gives you a more comprehensive look at how much you’ll pay when you borrow money by factoring in these additional fees. When it comes to APR vs. interest rate, the former more accurately represents the true cost of the loan.

The outline of this project is:

-   Introduction
-   Univariate Exploration of Data
-   Bivariate Exploration of Data
-   Multivariate Exploration of Data
-   Summary and Conclusion

<br>

Univariate Exploration of Data
========================

### Quantitative Variables

We'll start by looking at our two variables of interest: The distribution of Borrower APR and Estimated Return. 
We'll then proceed in looking at the distribution of other quantitative variables. 

#### Borrower APR
![](/images/univariate_distribution_of_borrower_APR.png)

Borrower APR is slightly skewed to the right. We can see some peaks throughout the whole distribution. This seems to show that there are certain preconstructed borrower annual percentage rates, the most common one being 0.35.  

#### Estimated Return
![](/images/univariate_distribution_of_estimated_return.png)

Most return rates fall between 7% and 13%. Anything over 15% is very rare. 
The average return for a loan is 9.6%. The max in the dataset is 28%. 

#### Loan Amounts
![](/images/univariate_log_distribution_of_loan_amounts.png)

There's a long tail in the distribution for loan amounts, so we used a log scale instead.
Loans can range from 1000\\$ (the minimum amount in the dataset) to 35,000\\$. Most loans range from 4000 to 13000\\$. The graph indicates that some loan amounts are more popular than others. 

#### Monthly Payments

![](/images/univariate_log_distribution_of_monthly_payments.png)

We also used log scale for this graph. This allows us to better understand the distribution of loans between 100 and 500\\$. A commmon loan payment is around 175\\$ / month. The median monthly payment is $217, less than the mean of $272, so the distribution skews toward smaller monthly payments. No payment is more than $2,252, but that appears to be a signficant outlier. There are very few payments above $1,000.

### Ordinal Variables

#### Term duration, income range, credit score and Loan Status

![](/images/univariate_ordinal_variables.png)

Most loans are 36 month terms in this dataset. Borrowers' income are mostly below 75,000\\$ per year. 

Overall, it appears that a large majority of loans are either Completed or Current, though there are also a large number of Charged-off and Defaulted (non-performing). A little later I will want to look at loan performance based on origination vintage.

### Categorical Variables

#### Employment Status and Is Borrower a Homeowner? 

![](/images/univariate_categorical_variables.png)

#### Listing Categories

![](/images/univariate_distribution_of_listing_categories.png)

Most Listing Categories are Debt Consolidation. Other popular ones inclure Home Improvement, Auto, Business, and Other. 

<br>

Bivariate Exploration of Data
========================
Let's start by checking the relationship between Estimated Return and the Loan Amount. Are higher loans related with better returns? 

#### Estimated Return VS Loan Amount

![](/images/bivariate_estimated_return_based_on_loan_amount.png)

We can see a slight negative correlation between the Estimated Return and the log of the Loan Amount. On average, smaller loans tend to yield higher returns. However, there is also more variability in returns for smaller loans. This means that there is more risk associated with smaller loans. 

##### Insight 1: If you were to invest multiple times in different loans, you would yield more returns with smaller loans. For a safer, one time bet, a higher loan would be more appropriate. 

#### Estimated Return VS Months since Origination

![](/images/bivariate_estimated_returb_based_on_number_of_months_of_the_loan.png)

The duration of the loan seems to have no impact on return. We can see from this graph however that longer loans are riskier since they have higher variability in return. 

##### Insight 2: Longer term loans are more risky because they have more variability. On average however, the length of the loan has no impact on estimated returns. 

Let's now look at Estimated Returns and our categorical features. 

#### Estimated Returns VS Listing Category

There are 20 different listing categories, some of which are not represented much. For the next graph, we're only taking the listing categories where there are over 500 loans in the dataset. Otherwise we might get some incomplete information about the loan.  

![](/images/bivariate_estimated_return_average_most_popular_categories.png)

##### Insight 3: Investing in a Home Improvement loan and a large purchase loan, is slightly less profitable than the others on average. The category with the highest returns is Auto (excluding the Not Available category)

#### BorrowerAPR and Estimated Return VS Credit Score and Income Range

![](/images/bivariate_BorrowerAPR_and_Estimated_Return_vs_Credit_Score_and_Income_Range.png)

The average borrower APR becomes lower with better credit scores. Having an Exceptional credit score really makes a difference! The same thing can be said for income bracket, although the difference is less reveling. 

Loaning to borrowers that have lower incomes and lower credit scores yield slightly higher returns. 

##### Insight 4: Having an exceptional credit score makes a huge difference in the APR one can get. 

<br>

Multivariate Exploration of Data
========================

Are there features that strengthened each other in terms of looking at our features of interest?

We saw that the duration of the loan term seemed to have a high impact on returns. Let's have a look of how much difference it makes when comparing our different listing categories. 

### Estimated Return Analysis

![](/images/multivariate_Estimated_Return_based_on_listing_category_and_term_length.png)

##### Insight 5: Investing in a 60 month term loan is clearly a better investment than any other term. This is particularly true for the following categories: houseshold expenses, auto, medical/dental, wedding loans, vacation, business and taxes.

Are there other factors that make a loan more profitable? Let's look at profit for different employment status': <b>Full-time and Not employed.</b>

#### Estimated Return for Full-time employees and the unemployed

![](/images/multivariate_estimated_return_based_on_listing_cateogry_and_term_length_for_full_time_employees.png)

![](/images/multivariate_Estimated_return_basd_on_listing_category_and_term_length_for_the_unemployed.png)

While there are ethical considerations at play, loans from unemployed people are yield more returns on average particularly in the home improvement, auto, and vacation category. 

That said, one listing category yields higher returns than any other category for fulltime employees: <b>vacation</b>

##### Insight 6: A 60 month term loan in the vacation cateogy for a fulltime employee is a very good investment. 

Is there a difference in returns depending on the loan amount? Let's look at the returns based on term duration and loan amount. 

#### Estimated Return Based on Loan Amount and Term Length


![](/images/multivariate_estimated_return_based_on_loan_amount_and_term_length.png)

##### Insight 7: Loans over 6000$ and of a duration of 60 months yield the highest returns on average. 

### Borrower APR Analysis

Let's look at the influence of credit score and term length on borrower APR.

![](/images/multivariate_Borrower_APR_vs_credit_score_and_term_loan.png)


As expected, lower credit scores correlate with higher APR. As the loan amount increases, the APR lowers as well. It's also interesting to see that for the "Very Poor" credit score category there are not 60 month term loans. 

##### Insight 8: Longer term loans have on average lower APR.



Let's look at which listing categories are associated with low APR. 

![](/images/multivariate_borrow_APR_based_on_categories_and_term_length.png)

The lowest rates are in home improvement, vacation and large purchases categories, for a 60 month term.

<br>

Summary and Conclusion
========================

With so many variable it was hard to get started because of my limited financial knowledge. There were 81 features to choose from so narrowing the analysis to something meaningful was a challenge. After reading through the descriptions and definitions, I chose ‘BorrowerAPR’ and ‘EstimatedReturn’ as my target variables to get insights on both sides: the borrower and the lender. 

Limitations
-----------

The analysis done is a good way to begin understanding the data visually. However, in order to determine the true relationships between variables and understand how they influence each other, we would need to conduct statistical tests and anlysis. This is just the first step to comprehending the data. 


Below is a summary of the insights gathered with this analysis: 

 - Insight 1: If you were to invest multiple times in different loans, you would yield more returns with smaller loans. For a safer, one time bet, a higher loan would be more appropriate. 
 - Insight 2: Longer term loans are more risky because they have more variability. On average however, the length of the loan has no impact on estimated returns. 
 - Insight 3: Investing in a Home Improvement loan and a large purchase loan, is slightly less profitable than the others on average. The category with the highest returns is Auto (excluding the Not Available category).
 - Insight 4: Having an good credit score makes a huge difference in the APR one can get. 
 - Insight 5: Investing in a 60 month term loan is a better investment than any other term duration (12 and 30). This is particularly true for the following categories: houseshold expenses, auto, medical/dental, wedding loans, vacation, business and taxes.
 - Insight 6: A 60 month term loan in the vacation cateogy for a fulltime employee is the best investment we have found in our analysis.
 - Insight 7: Loans over 6000$ and of a duration of 60 months yield the highest returns on average. 
 - Insight 8: Longer term loans have on average lower APR. 

