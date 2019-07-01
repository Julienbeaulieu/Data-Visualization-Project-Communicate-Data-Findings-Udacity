# Prosper Loan Exploratory Data Analysis - Udacity Project

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

