Download Link: https://assignmentchef.com/product/solved-stats506-problem-set-2
<br>
<h1>Question 1</h1>

Use Stata to estimate the following national <em>totals</em> for residential energy consumption:

<ul>

 <li>Electricity usage in kilowatt hours</li>

 <li>Natural gas usage, in hundreds of cubic feet</li>

 <li>Propane usage, in gallons</li>

 <li>Fuel oil or kerosene usage, in gallons</li>

</ul>

In your analysis, be sure to properly weight the individual observations. Use the replicate weights to compute standard errors. At the end of your .do file, write the estimates and standard errors to a delimited file recs2015_usage.csv.

In your .Rmd read recs2015_usage.csv and produce a nicely formatted table with estimates and 95% confidence intervals.

<h1>Question 2</h1>

For this question you should use the 2005-2006 NHANES ORAL Health data available <a href="https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Examination&amp;CycleBeginYear=2005">here</a> and the demographic data available <a href="https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Demographics&amp;CycleBeginYear=2005">here</a><a href="https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Demographics&amp;CycleBeginYear=2005">.</a> Your analyses for this question should be done in Stata, though you may create plots and format tables using R within

Rmarkdown.

For part (b-d), you can ignore the survey aspect of the data and analyze it as if the data were a simple random sample.

<ul>

 <li>[5 points] Determine how to read both data sets into Stata and merge them together by the participant id SEQN.</li>

 <li>[5 points] Use logistic regression to estimate the relationship between age (in months) and the probability that an individual has a primary rather than a missing or permanent upper right 2nd bicuspid. You can recode permanent root fragments as permanent and drop individuals for whom this tooth was not assessed. Use the fitted model to estimate the ages at which 25, 50, and 75% of individuals lose their primary upper right 2nd bicuspid. Round these to the nearest month. Choose a range of representative age values with one year increments by taking the floor (in years) of the 25%-ile and the ceiling (in years) of the 75%-ile.</li>

 <li>[10 points] In the regression above, control for demographics in the following way:</li>

</ul>

◦ Add gender to the model and retain it if it improves the BIC.

◦ Create indicators for each race/ethnicity category using the largest as the reference and collapsing ‘Other Hispanic’ and ‘Other’. In order of group size in the sample, add each category retaining those that improve BIC.

◦ Add poverty income ratio to the model and retain it if it improves BIC. In your pdf document, include a nicely formatted regression table for the final model and an explanation of the model fitting process.

<ul>

 <li>[10 points] Use the margins command to compute:

  <ol>

   <li>Adjusted predctions at the mean (for other values) at each of the representative ages determined in part b.</li>

   <li>The marginal effects at the mean of any retained categorical variables at the same representative ages.</li>

   <li>The average marginal effect of any retained categorical varialbes at the representative ages.</li>

  </ol></li>

 <li>[5 points] Refit your final model from part c using svy and comment on the differences. Include a nicely formatted regression table and cite evidence to justify your comments.</li>

</ul>

You should use the following command to set up the <a href="ftp://ftp.cdc.gov/pub/health_statistics/nchs/tutorial/nhanes/Continuous/descriptive_mean.do">survey weights</a><a href="ftp://ftp.cdc.gov/pub/health_statistics/nchs/tutorial/nhanes/Continuous/descriptive_mean.do">:</a> svyset sdmvpsu [pweight=wtmec2yr], strata(sdmvstra)

vce(linearized)

<h1>Question 3</h1>

Repeat part a-d of question 2 using <strong>R</strong>. For part d, you may either use the “margins” package or code the computations yourself.