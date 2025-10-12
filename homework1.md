---
title: "ECON4225 Homework 1"
output: 
  pdf_document:
    number_sections: no
    keep_md: yes
date: "2025-10-06"
author: "Anna Duan"
---


# Part 1: Overview of the Dataset 
## Question 1: household and variable count
This dataset has 9066 households and 38 variables, including the household ID.

```
## [1] "rows: 9066"
```

_ID_, _AGE_HEAD_, _AGE_SPOUSE_, _SEX_HEAD_, _SEX_SPOUSE_, _EDU_HEAD_, _EDU_SPOUSE_, _OCC_HEAD_, _OCC_SPOUSE_, _STATE_, _MARITAL_, _HOUSEHOLD_SIZE_, _CHILDREN_, _SPOUSE_PRESENT_, _WEIGHT_, _INCOME_, _HEAD_LABOR_, _SPOUSE_LABOR_, _WEEKS_HEAD_, _WEEKS_SPOUSE_, _WEEKS_OUT_HEAD_, _WEEKS_OUT_SPOUSE_, _EXP_, _GAS_, _FOOD_HOME_, _FOOD_DELIV_, _FOOD_OUT_, _RENT_, _EDUC_EXP_, _CHILDCARE_, _TRIPS_, _WEALTH_, _HOUSE_VALUE_, _MORTGAGE_, _MORT_PAY_, _HOME_EQUITY_, _BUSINESS_VAL_ and _PROPERTY_TAX_

## Question 2: age of household head  
The average age of the household head is 46.25. The highest age is 102 and the lowest age is 18.

```
## [1] "Mean age: 46.25"
```

```
## [1] "Highest age: 102"
```

```
## [1] "Lowest age: 18"
```

## Question 3: average household income  
The average household income is $78,265.69. This is substantially lower the $142k reported by the SCF in 2022 (Section 1.2, slide 9). One possible reason for this difference is that the SCF surveys a small sample, focusing on high-income individuals, resulting in a less representative mean. The PSID has a larger sample, with less emphasis on the top of the income distribution.

```
## [1] "Mean household income: 78265.69"
```

## Question 4: income range   
The household incomes in the dataset have a wide range: the lowest is -$267,900 and the highest is $2,125,100. The households with negative values likely incurred business or other losses in the survey year, resulting in negative net income.

```
## [1] "Lowest household income: -267900"
```

```
## [1] "Highest household income: 2125100"
```

## Question 5: age of household head's spouse     
Of the 4,523 households with a spouse of the household head present, the average age of the spouse is 45.64 years.

```
## [1] "Mean spouse age: 45.64"
```

## Question 6: household size    
Households with only 1 member make up 28.45% of the data. Households with 5 or more members make up 11.29%. Compared to the histogram shown in class, the PSID has fewer 2-member households and more 3-5 member households. In both datasets, about 28% of households have one member. The PSID dataset has a smaller share of two-member households: only 30.43% compared to the nearly 35% shown on slide 2 [what dataset is this?]. PSID has a slightly larger share of households with 3 members: 15.95%, compared to the slide's 15%; a 13.88% share of 4-member households, compared to the slide's 12.5%; and a 7.2% share of 5-member households, compared to just past 5% in the slide. 

----------------------------
 size_group   count    pct  
------------ ------- -------
     1        2579    28.45 

    2–4       5463    60.26 

     5+       1024    11.29 
----------------------------

Table: Percentage share of PSID households by size



![](homework1_files/figure-latex/hh size hist-1.pdf)<!-- --> 

# Part 2: Income Distribution    
## Question 1: distribution of household income  
The following histogram shows the distribution of household incomes in the PSID, with values above the 99th percentile removed. The distribution is right-skewed, as the median of $55,090 is lower than the mean of $78,266. The majority of households earn less than $100,682, which is the 75th percentile. A small minority of households surveyed have higher household incomes, up to $2.13 million. 137 households have no income, and three households have negative income, with the lowest income being $267,900.


--------------------------------------------------------
  Min.     1st Qu.   Median   Mean    3rd Qu.    Max.   
--------- --------- -------- ------- --------- ---------
 -267900    28000    55090    78266   100681    2125100 
--------------------------------------------------------

Table: Distribution of Household Incomes

![](homework1_files/figure-latex/hh income hist-1.pdf)<!-- --> 

## Question 2: household income Lorenz curve   
The following Lorenz curve visualizes the cumulative share of households (x) against the cumulative share of total household income (y). The dotted line is what the curve would look like at perfect inequality, where 50% of households possess 50% of total household income. The solid red line represents the relationship between cumulative household share and cumulative household income share. 

We see on this curve that the lowest earning 50% of households in the PSID account for only 18% of total household income, and that the bottom 75% of households account for 42% of income. By contrast, the top 10% of highest earning households account for about a third of all household income, and the top 1% of households account for just above 8%. In this dataset, we can tell that higher-earning households account for more than their proportional share of household income.
![](homework1_files/figure-latex/hh income lorenz-1.pdf)<!-- --> 

# ? SCF   
## Question 3: total household income coefficient of variation  
To further quantify the level of income inequality in the dataset, we can calculate the coefficient of variation by dividing the standard deviation in household income by the mean household income. This produces a coefficient of variation of 1.15, which is ______ compared to the ______ derived from the SCF. 

```
## [1] "Coefficient of variation of household income: 1.15"
```

#? adjustment method  
## Question 4: adjusted total household income Lorenz curve   
When we adjust this curve for the number of household heads present, the distance from the line of perfect equality decreases. On the yellow curve representing the relationship between adjusted income share and population share, we see that the bottom 50% of households account for 21% of income, compared to the 18% on the non-adjusted curve. 

This indicates that some of the inequality among households may be attributed to differences in household size and the number of earners. 

![](homework1_files/figure-latex/lorenz curve comparison-1.pdf)<!-- --> 

## Question 5: household income percentile ratios   
The table below displays the 30th, 50th, 90th, and 99th percentiles of household income in the dataset. The wide gap between the 50th and 90th and 50th and 99th percentiles give us a sense of the income inequality among the households, but percentiles themselves are insufficient. 

-----------------------
 percentile    value   
------------ ----------
    30th      $33107.5 

    50th       $55090  

    90th      $161188  

    99th      $396420  
-----------------------

Table: PSID Household Income Percentiles
  
The percentile ratios in the table reveal a markedly unequal income distribution. Households at the top earn several times more than those in the middle or bottom. Specifically, households at the 90th percentile earn nearly three times the median income, while those at the 99th percentile earn 7.2 times the median, indicating extreme concentration of income at the very top. The 2.67 ratio between the 30th and 10th percentiles shows that inequality at the lower end exists but is considerably smaller than that among top earners.  


--------------------------
 percentile_ratio   value 
------------------ -------
      90-30         4.87  

      90-50         2.93  

      30-10         2.67  

      99-50          7.2  
--------------------------

Table: PSID Household Income Percentile Ratios

# ? SCF  
- Comparison with SCF 

## Question 6: mean household income and share by quintile    
The following table further illustrates this pattern of income inequality among PSID households: the greatest disparities between consecutive quintiles are between quintiles 2 and 1 and quintiles 5 and 4. Quintile 2 has a mean income of $33,188, 2.76 times the first quintile's mean income of $12,003. The second quintile's income share of 8.5% is 2.74 times that of the first quintile (3.1%). The fifth quintile's income of $199,894 is 2.21 times that of the fourth quintile ($90,408). The fifth quintile's income share of 51.1% is 2.39 times that of the fourth quintile. It's also notable that the income share of the top quintile is greater than that of the remaining 4 quintiles. Taken together, this shows the high overall income inequality among PSID households, as well as the heightened inequality at the bottom and top of the distributions.  



---------------------------------------
 quintile   income_share   mean_income 
---------- -------------- -------------
    1           3.1%         $12,003   

    2           8.5%         $33,188   

    3          14.3%         $55,883   

    4          23.1%         $90,408   

    5          51.1%        $199,894   
---------------------------------------

Table: Share of total household income and mean income by quintile

![](homework1_files/figure-latex/income quintile viz-1.pdf)<!-- --> 
# ? SCF  


## Question 7: mean total household income and share for the top 1%   
As discussed in class, quintiles can obfuscate the inequality within the top of the distribution. Looking at the top 1% of high earning households, we see that their mean income ($639,974) is 8.81 times that of the bottom 99% ($72,570), and 3.2 times that of the top 20%. In terms of income share, the top 1% accounts for 8% of all household income, making up nearly one-sixth of the top quintile's share. Even within the top quintile, there is drastic inequality between the highest and lowest earners.  

-----------------------------------------
   group      income_share   mean_income 
------------ -------------- -------------
 bottom 99%       92%          $72,570   

   top 1%          8%         $639,974   
-----------------------------------------

Table: Share of total household income and mean income held by the top 1%

# ? SCF    
compare with scf distribution    

# Part 3: Labor Income    
## Question 1: household earnings share and mean by quintile    
Looking at total labor earnings of households, the inequality within the bottom of the distribution is much higher. The table below lists the mean household earnings and share of household earnings by quintile. The second quintile of households ($14,976) earns 516 times the labor income of the first quintile ($29). The earnings inequality at the top 40% of the distribution is also higher than total household income, but by a smaller margin.  


---------------------------------------------------
 quintile   labor_income_share   mean_labor_income 
---------- -------------------- -------------------
    1              0.0%                 $29        

    2              5.0%               $14,976      

    3             13.4%               $39,309      

    4             24.1%               $72,342      

    5             57.4%              $170,395      
---------------------------------------------------

Table: Share of total household labor income and mean labor income by quintile
## Question 2: total household income vs household earnings by quintile    
Side by side, we can see that the distribution of earnings share is more unequal. The bottom quintile's share of earnings rounds to zero, while the bottom quintile's share of total household income is 3.1%. Quintiles 2 and 3 also hold smaller shares of earnings than they do total income. Quintile 4 has a slightly higher share of earnings than total income, and quintile 5's share of earnings is higher than total income by 6.3 percentage points. Compared to the distribution of total income, earnings is more unevenly distributed, with higher percentage shares concentrated in the top 2 quartiles.   

------------------------------------------------
 quintile   total_income_share   earnings_share 
---------- -------------------- ----------------
    1              3.1%               0.0%      

    2              8.5%               5.0%      

    3             14.3%              13.4%      

    4             23.1%              24.1%      

    5             51.1%              57.4%      
------------------------------------------------

Table: Total income vs earnings quintile shares

Calculating the coefficient of variation for both metrics confirms this: earnings have a coefficient of variation of 1.36, compared to 1.15 for household income. This indicates that there is more variability in earnings relative to the mean.    


---------------------------
       metric          cv  
-------------------- ------
  Household Income    1.15 

 Household Earnings   1.36 
---------------------------

Table: Coefficient of Variation: Household Income and Earnings
This trend is seen when plotted on a Lorenz curve, as well. The curve representing the relationship between cumulative shares of households and income for household earnings is more far away from the line of perfect inequality, indicating that its distribution is more unequal than that of total household income. As discussed in class, redistributive policies like social insurance and means-tested transfers may be contributing to the household income of households at the bottom of the income distribution who do not have labor income. Consequently, the bottom quintile can have a higher share of total household income than household earnings.   

![](homework1_files/figure-latex/lorenz, total household income vs earnings-1.pdf)<!-- --> 


## Question 3: average share of total household income from earnings  
The average share of earnings in total household income is 68.51%, indicating that households typically receive just over two-thirds of their income from labor income. This figure is excluding the 137 households with incomes of 0, as the share would be undefined. 

```
## [1] "Mean share of earnings in total household income: 68.51"
```

```
## [1] "Houses with zero household income: 137"
```


## Question 4: mean and share of labor earnings by quintile    
In the dataset, households that have more household income make a larger share of their income from labor earnings. The most stark difference is between quintile 1 and 2: the mean share of labor is 46.6% in the former, and increases by 18.9 percentage points for quintile 2. The difference in the earnings share between the remaining quintiles is modest: from quintile 2 to 5, the increase is less than that between quintile 1 and 2.

-----------------------------
 quintile   mean_labor_share 
---------- ------------------
    1            46.6%       

    2            65.5%       

    3            71.9%       

    4            76.8%       

    5            80.2%       
-----------------------------

Table: Share of total household income from labor earnings by quintile, PSID


# ? SCF    
When we pull out the top 1% of households, however, we see that they only get 68.4% of their income from labor earnings, almost the same as the mean of all households. This is because, as discussed in class, the top earning households have a higher share of capital income in their total income, and rely less on labor. They also tend to be older, and some are retired. Compared to SCF, this figure ________.  

-------------------------------
   group      mean_labor_share 
------------ ------------------
 bottom 99%        77.1%       

   top 1%          68.4%       
-------------------------------

Table: Share of total household income from labor earnings, top 1%, PSID
  
- Compare both to SCF  
- Comment on differences   
  
## Question 5: weekly wage, contribution of hours and wages to labor earnings inequality  
In the dataset, there are 6,971 households where the household head has positive labor earnings and weeks of work. The mean weekly wage for these household heads is $1,117.74.  


```
## [1] 6971
```

```
## [1] 1117.736
```

A variance decomposition shows that most earnings inequality arises from wage dispersion: the variance of log wages (0.87) is much larger than the variance of log weeks worked (0.17). The positive covariance (0.15) indicates that individuals with higher wages also tend to work more weeks, further amplifying overall earnings inequality. These results suggest that differences in wages contribute much more to earnings inequality than differences in weeks worked.

However, a caveat to this decomposition is that it is restricted to household heads with positive weeks worked and positive labor earnings. By excluding those who did not work or earn, the approach may understate the role of weeks worked in earnings inequality, as those at the bottom of the earnings distribution could be working very few weeks or not at all due to limited employment opportunities.


```
## # A tibble: 5 x 2
##   component                   value
##   <chr>                       <dbl>
## 1 Var(log wage)               0.874
## 2 Var(log weeks)              0.167
## 3 2*Cov(log wage, log weeks)  0.149
## 4 Var(log earnings)           1.19 
## 5 Predicted Var(log earnings) 1.19
```



## Question 6 
A linear regression of the log-transformed weekly wage of the household head on the head's age, age-squared, education, and occupation provides further information about the drivers of wage inequality. The observables in this simple regression explain 44% of the variation in log-transformed weekly wages, while the residuals (residual standard error = 0.7243) explain 56%. 

```
## 
## Call:
## lm(formula = log_wage ~ AGE_HEAD + AGE_HEAD_SQ + EDU_HEAD_CAT + 
##     OCC_HEAD_CAT, data = psid_reg)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -5.2241 -0.3201  0.0556  0.4043  2.9036 
## 
## Coefficients:
##                    Estimate Std. Error t value Pr(>|t|)    
## (Intercept)       5.570e+00  2.915e-01  19.105  < 2e-16 ***
## AGE_HEAD          8.667e-02  4.385e-03  19.766  < 2e-16 ***
## AGE_HEAD_SQ      -9.439e-04  4.743e-05 -19.899  < 2e-16 ***
## EDU_HEAD_CAT1     9.103e-01  7.634e-01   1.192 0.233154    
## EDU_HEAD_CAT2    -5.371e-01  3.407e-01  -1.576 0.115020    
## EDU_HEAD_CAT3    -4.021e-01  3.090e-01  -1.301 0.193255    
## EDU_HEAD_CAT4     1.300e-01  3.316e-01   0.392 0.694997    
## EDU_HEAD_CAT5    -9.030e-03  3.792e-01  -0.024 0.981004    
## EDU_HEAD_CAT6    -1.086e-01  2.524e-01  -0.430 0.666926    
## EDU_HEAD_CAT7    -5.192e-02  2.917e-01  -0.178 0.858730    
## EDU_HEAD_CAT8    -2.889e-01  2.648e-01  -1.091 0.275272    
## EDU_HEAD_CAT9    -2.506e-02  2.466e-01  -0.102 0.919069    
## EDU_HEAD_CAT10   -1.480e-01  2.409e-01  -0.614 0.538943    
## EDU_HEAD_CAT11   -1.938e-01  2.372e-01  -0.817 0.413845    
## EDU_HEAD_CAT12    2.601e-02  2.351e-01   0.111 0.911889    
## EDU_HEAD_CAT13    7.139e-02  2.365e-01   0.302 0.762749    
## EDU_HEAD_CAT14    1.365e-01  2.358e-01   0.579 0.562581    
## EDU_HEAD_CAT15    9.390e-02  2.381e-01   0.394 0.693267    
## EDU_HEAD_CAT16    3.268e-01  2.362e-01   1.384 0.166474    
## EDU_HEAD_CAT17    3.710e-01  2.369e-01   1.566 0.117297    
## OCC_HEAD_CAT20   -7.642e-02  1.869e-01  -0.409 0.682616    
## OCC_HEAD_CAT30   -1.457e+00  5.311e-01  -2.743 0.006109 ** 
## OCC_HEAD_CAT40   -1.270e-02  2.593e-01  -0.049 0.960944    
## OCC_HEAD_CAT50   -1.210e-01  1.789e-01  -0.677 0.498628    
## OCC_HEAD_CAT60    2.192e-02  3.272e-01   0.067 0.946607    
## OCC_HEAD_CAT100  -1.050e-01  3.075e-01  -0.342 0.732685    
## OCC_HEAD_CAT110   7.053e-02  1.869e-01   0.377 0.705857    
## OCC_HEAD_CAT120  -1.643e-02  1.779e-01  -0.092 0.926440    
## OCC_HEAD_CAT136  -3.377e-01  2.515e-01  -1.343 0.179356    
## OCC_HEAD_CAT137   8.559e-01  7.380e-01   1.160 0.246187    
## OCC_HEAD_CAT140  -4.616e-01  2.056e-01  -2.245 0.024811 *  
## OCC_HEAD_CAT150  -4.286e-01  4.409e-01  -0.972 0.331059    
## OCC_HEAD_CAT160  -2.947e-01  2.208e-01  -1.335 0.181952    
## OCC_HEAD_CAT205  -4.332e-01  2.337e-01  -1.854 0.063849 .  
## OCC_HEAD_CAT220  -2.318e-01  1.695e-01  -1.367 0.171690    
## OCC_HEAD_CAT230  -7.736e-01  1.924e-01  -4.021 5.87e-05 ***
## OCC_HEAD_CAT300  -1.214e-01  2.082e-01  -0.583 0.559918    
## OCC_HEAD_CAT310  -5.331e-01  2.111e-01  -2.525 0.011590 *  
## OCC_HEAD_CAT325  -4.435e-01  4.408e-01  -1.006 0.314464    
## OCC_HEAD_CAT340  -1.125e+00  3.528e-01  -3.189 0.001432 ** 
## OCC_HEAD_CAT350  -4.059e-01  2.245e-01  -1.808 0.070593 .  
## OCC_HEAD_CAT360  -6.892e-01  5.309e-01  -1.298 0.194286    
## OCC_HEAD_CAT400  -7.394e-01  7.384e-01  -1.001 0.316686    
## OCC_HEAD_CAT410  -4.439e-01  1.994e-01  -2.226 0.026027 *  
## OCC_HEAD_CAT420  -8.092e-01  2.592e-01  -3.122 0.001802 ** 
## OCC_HEAD_CAT425  -2.802e-01  7.378e-01  -0.380 0.704133    
## OCC_HEAD_CAT430  -5.730e-01  1.567e-01  -3.656 0.000258 ***
## OCC_HEAD_CAT500   8.418e-02  7.380e-01   0.114 0.909188    
## OCC_HEAD_CAT510  -2.021e-01  5.312e-01  -0.380 0.703613    
## OCC_HEAD_CAT520  -8.390e-01  2.686e-01  -3.124 0.001792 ** 
## OCC_HEAD_CAT530  -2.025e-01  2.592e-01  -0.781 0.434547    
## OCC_HEAD_CAT540  -7.085e-01  2.336e-01  -3.034 0.002425 ** 
## OCC_HEAD_CAT565  -4.529e-01  2.243e-01  -2.019 0.043486 *  
## OCC_HEAD_CAT600  -6.734e-01  3.076e-01  -2.189 0.028629 *  
## OCC_HEAD_CAT630  -6.187e-01  2.515e-01  -2.460 0.013934 *  
## OCC_HEAD_CAT640  -5.007e-01  3.884e-01  -1.289 0.197353    
## OCC_HEAD_CAT650  -2.707e-01  2.333e-01  -1.160 0.245981    
## OCC_HEAD_CAT700  -7.466e-01  2.919e-01  -2.558 0.010556 *  
## OCC_HEAD_CAT710  -1.549e-01  1.972e-01  -0.786 0.432092    
## OCC_HEAD_CAT725  -9.012e-01  3.271e-01  -2.755 0.005892 ** 
## OCC_HEAD_CAT726  -1.030e+00  4.411e-01  -2.336 0.019533 *  
## OCC_HEAD_CAT735  -5.008e-01  2.141e-01  -2.339 0.019383 *  
## OCC_HEAD_CAT740  -2.902e-01  2.333e-01  -1.244 0.213508    
## OCC_HEAD_CAT800  -5.381e-01  1.737e-01  -3.097 0.001963 ** 
## OCC_HEAD_CAT810  -3.904e-01  2.916e-01  -1.339 0.180654    
## OCC_HEAD_CAT820  -5.838e-01  4.409e-01  -1.324 0.185518    
## OCC_HEAD_CAT830  -6.400e-02  5.308e-01  -0.121 0.904036    
## OCC_HEAD_CAT840   1.456e-01  2.247e-01   0.648 0.517231    
## OCC_HEAD_CAT850   5.137e-02  2.171e-01   0.237 0.813000    
## OCC_HEAD_CAT860  -3.256e-01  4.411e-01  -0.738 0.460485    
## OCC_HEAD_CAT910  -3.537e-01  2.059e-01  -1.717 0.085973 .  
## OCC_HEAD_CAT930  -9.789e-01  7.381e-01  -1.326 0.184824    
## OCC_HEAD_CAT940  -7.022e-01  2.920e-01  -2.405 0.016204 *  
## OCC_HEAD_CAT950  -1.086e+00  5.310e-01  -2.045 0.040895 *  
## OCC_HEAD_CAT1005 -1.892e-01  7.380e-01  -0.256 0.797648    
## OCC_HEAD_CAT1006 -3.064e-01  2.387e-01  -1.284 0.199296    
## OCC_HEAD_CAT1007 -1.401e-01  2.683e-01  -0.522 0.601688    
## OCC_HEAD_CAT1010 -2.241e-01  2.137e-01  -1.048 0.294542    
## OCC_HEAD_CAT1020 -1.364e-01  1.690e-01  -0.807 0.419654    
## OCC_HEAD_CAT1030 -4.881e-01  2.684e-01  -1.819 0.069024 .  
## OCC_HEAD_CAT1050 -5.649e-01  1.790e-01  -3.156 0.001607 ** 
## OCC_HEAD_CAT1060 -2.999e-01  2.448e-01  -1.225 0.220565    
## OCC_HEAD_CAT1105 -3.974e-01  2.171e-01  -1.831 0.067220 .  
## OCC_HEAD_CAT1106 -3.595e-01  3.074e-01  -1.169 0.242310    
## OCC_HEAD_CAT1107 -7.487e-01  3.272e-01  -2.288 0.022177 *  
## OCC_HEAD_CAT1200  2.906e-01  5.311e-01   0.547 0.584255    
## OCC_HEAD_CAT1220 -6.992e-01  5.311e-01  -1.317 0.188003    
## OCC_HEAD_CAT1300 -6.996e-01  3.272e-01  -2.138 0.032559 *  
## OCC_HEAD_CAT1320 -5.466e-02  3.270e-01  -0.167 0.867245    
## OCC_HEAD_CAT1340 -1.567e+00  4.411e-01  -3.553 0.000383 ***
## OCC_HEAD_CAT1350 -7.021e-02  3.527e-01  -0.199 0.842199    
## OCC_HEAD_CAT1360 -1.613e-01  2.446e-01  -0.660 0.509536    
## OCC_HEAD_CAT1400  1.954e-01  4.409e-01   0.443 0.657584    
## OCC_HEAD_CAT1410 -1.053e-01  2.245e-01  -0.469 0.638952    
## OCC_HEAD_CAT1420 -1.494e-01  3.527e-01  -0.424 0.671776    
## OCC_HEAD_CAT1430 -1.424e-01  3.073e-01  -0.463 0.643217    
## OCC_HEAD_CAT1440  9.549e-02  7.378e-01   0.129 0.897032    
## OCC_HEAD_CAT1450 -5.655e-01  5.311e-01  -1.065 0.287052    
## OCC_HEAD_CAT1460 -1.100e-01  2.108e-01  -0.522 0.601732    
## OCC_HEAD_CAT1500 -3.086e-01  7.379e-01  -0.418 0.675836    
## OCC_HEAD_CAT1520 -5.361e-01  4.413e-01  -1.215 0.224534    
## OCC_HEAD_CAT1530  3.534e-01  7.382e-01   0.479 0.632116    
## OCC_HEAD_CAT1540 -4.929e-01  2.923e-01  -1.686 0.091855 .  
## OCC_HEAD_CAT1550 -6.119e-01  1.941e-01  -3.153 0.001625 ** 
## OCC_HEAD_CAT1560 -8.314e-01  4.410e-01  -1.885 0.059428 .  
## OCC_HEAD_CAT1600 -7.522e-01  7.399e-01  -1.017 0.309389    
## OCC_HEAD_CAT1610 -7.483e-01  2.449e-01  -3.056 0.002253 ** 
## OCC_HEAD_CAT1650 -7.081e-01  4.413e-01  -1.605 0.108647    
## OCC_HEAD_CAT1700 -9.414e-02  3.886e-01  -0.242 0.808579    
## OCC_HEAD_CAT1710 -1.458e+00  7.381e-01  -1.976 0.048235 *  
## OCC_HEAD_CAT1720 -7.938e-01  3.270e-01  -2.427 0.015240 *  
## OCC_HEAD_CAT1740 -1.042e+00  2.790e-01  -3.735 0.000189 ***
## OCC_HEAD_CAT1760 -6.741e-01  7.380e-01  -0.913 0.361077    
## OCC_HEAD_CAT1800  7.684e-02  5.312e-01   0.145 0.884987    
## OCC_HEAD_CAT1815 -4.607e-01  3.883e-01  -1.187 0.235397    
## OCC_HEAD_CAT1820 -1.024e+00  3.077e-01  -3.326 0.000886 ***
## OCC_HEAD_CAT1840 -7.697e-01  4.409e-01  -1.746 0.080918 .  
## OCC_HEAD_CAT1860 -1.171e+00  3.884e-01  -3.016 0.002571 ** 
## OCC_HEAD_CAT1900 -3.691e-01  5.334e-01  -0.692 0.489010    
## OCC_HEAD_CAT1920 -5.888e-01  3.886e-01  -1.515 0.129716    
## OCC_HEAD_CAT1930 -2.350e-01  5.313e-01  -0.442 0.658302    
## OCC_HEAD_CAT1950 -2.927e-01  7.380e-01  -0.397 0.691630    
## OCC_HEAD_CAT1965 -7.116e-01  3.075e-01  -2.314 0.020681 *  
## OCC_HEAD_CAT2000 -1.059e+00  1.758e-01  -6.025 1.78e-09 ***
## OCC_HEAD_CAT2010 -9.793e-01  1.909e-01  -5.131 2.97e-07 ***
## OCC_HEAD_CAT2015 -8.714e-01  3.885e-01  -2.243 0.024932 *  
## OCC_HEAD_CAT2016 -1.215e+00  2.686e-01  -4.522 6.24e-06 ***
## OCC_HEAD_CAT2025 -1.157e+00  2.082e-01  -5.557 2.85e-08 ***
## OCC_HEAD_CAT2040 -1.265e+00  2.081e-01  -6.080 1.27e-09 ***
## OCC_HEAD_CAT2050 -7.994e-01  5.310e-01  -1.505 0.132286    
## OCC_HEAD_CAT2100 -1.861e-02  1.862e-01  -0.100 0.920394    
## OCC_HEAD_CAT2105 -1.059e+00  7.381e-01  -1.434 0.151553    
## OCC_HEAD_CAT2110 -6.135e-02  3.274e-01  -0.187 0.851345    
## OCC_HEAD_CAT2145 -6.873e-01  2.790e-01  -2.464 0.013772 *  
## OCC_HEAD_CAT2160 -7.087e-01  3.883e-01  -1.825 0.067992 .  
## OCC_HEAD_CAT2200 -8.297e-01  1.800e-01  -4.610 4.11e-06 ***
## OCC_HEAD_CAT2300 -1.398e+00  2.210e-01  -6.326 2.68e-10 ***
## OCC_HEAD_CAT2310 -1.116e+00  1.629e-01  -6.851 8.02e-12 ***
## OCC_HEAD_CAT2320 -8.670e-01  1.693e-01  -5.123 3.10e-07 ***
## OCC_HEAD_CAT2330 -9.993e-01  2.516e-01  -3.972 7.21e-05 ***
## OCC_HEAD_CAT2340 -1.689e+00  2.293e-01  -7.367 1.96e-13 ***
## OCC_HEAD_CAT2400 -7.589e-01  5.314e-01  -1.428 0.153296    
## OCC_HEAD_CAT2430 -9.820e-01  3.076e-01  -3.192 0.001419 ** 
## OCC_HEAD_CAT2440 -9.972e-01  7.380e-01  -1.351 0.176678    
## OCC_HEAD_CAT2540 -1.446e+00  1.825e-01  -7.920 2.76e-15 ***
## OCC_HEAD_CAT2550 -8.743e-01  2.387e-01  -3.663 0.000252 ***
## OCC_HEAD_CAT2600 -2.669e+00  2.521e-01 -10.588  < 2e-16 ***
## OCC_HEAD_CAT2630 -8.489e-01  1.974e-01  -4.300 1.73e-05 ***
## OCC_HEAD_CAT2700 -7.866e-01  3.890e-01  -2.022 0.043214 *  
## OCC_HEAD_CAT2710 -4.807e-01  3.076e-01  -1.562 0.118223    
## OCC_HEAD_CAT2720 -1.467e+00  2.205e-01  -6.652 3.13e-11 ***
## OCC_HEAD_CAT2740 -1.940e+00  7.384e-01  -2.627 0.008628 ** 
## OCC_HEAD_CAT2750 -1.623e+00  2.209e-01  -7.349 2.24e-13 ***
## OCC_HEAD_CAT2760 -1.820e+00  3.885e-01  -4.685 2.86e-06 ***
## OCC_HEAD_CAT2800 -1.425e+00  4.414e-01  -3.228 0.001251 ** 
## OCC_HEAD_CAT2810 -5.063e-03  4.409e-01  -0.011 0.990838    
## OCC_HEAD_CAT2825 -5.049e-01  3.532e-01  -1.430 0.152856    
## OCC_HEAD_CAT2830 -1.026e+00  3.271e-01  -3.135 0.001723 ** 
## OCC_HEAD_CAT2840 -6.048e-01  3.528e-01  -1.714 0.086521 .  
## OCC_HEAD_CAT2850 -8.386e-01  2.916e-01  -2.876 0.004047 ** 
## OCC_HEAD_CAT2860 -1.166e+00  5.311e-01  -2.195 0.028176 *  
## OCC_HEAD_CAT2900 -4.972e-01  3.527e-01  -1.410 0.158691    
## OCC_HEAD_CAT2910 -6.470e-01  3.273e-01  -1.977 0.048105 *  
## OCC_HEAD_CAT2920 -1.021e+00  3.277e-01  -3.114 0.001853 ** 
## OCC_HEAD_CAT2960 -1.045e+00  7.381e-01  -1.416 0.156888    
## OCC_HEAD_CAT3000 -1.016e+00  5.309e-01  -1.915 0.055577 .  
## OCC_HEAD_CAT3010  2.784e-01  3.079e-01   0.904 0.365883    
## OCC_HEAD_CAT3030 -1.238e+00  7.380e-01  -1.678 0.093464 .  
## OCC_HEAD_CAT3050  6.570e-02  2.796e-01   0.235 0.814226    
## OCC_HEAD_CAT3060  9.229e-02  1.873e-01   0.493 0.622275    
## OCC_HEAD_CAT3110 -6.136e-01  4.411e-01  -1.391 0.164289    
## OCC_HEAD_CAT3150 -3.296e-01  5.310e-01  -0.621 0.534765    
## OCC_HEAD_CAT3160 -4.318e-01  3.887e-01  -1.111 0.266666    
## OCC_HEAD_CAT3220 -7.307e-01  5.313e-01  -1.375 0.169058    
## OCC_HEAD_CAT3230 -7.748e-01  4.410e-01  -1.757 0.078944 .  
## OCC_HEAD_CAT3245 -1.580e+00  5.314e-01  -2.973 0.002959 ** 
## OCC_HEAD_CAT3250  2.142e-01  5.312e-01   0.403 0.686822    
## OCC_HEAD_CAT3255 -4.977e-01  1.676e-01  -2.970 0.002989 ** 
## OCC_HEAD_CAT3257 -6.697e-01  7.381e-01  -0.907 0.364264    
## OCC_HEAD_CAT3258 -5.607e-01  2.920e-01  -1.920 0.054872 .  
## OCC_HEAD_CAT3260 -9.934e-01  5.312e-01  -1.870 0.061535 .  
## OCC_HEAD_CAT3300 -1.110e+00  2.334e-01  -4.754 2.04e-06 ***
## OCC_HEAD_CAT3310 -1.071e+00  4.417e-01  -2.425 0.015331 *  
## OCC_HEAD_CAT3320 -7.051e-01  2.918e-01  -2.417 0.015694 *  
## OCC_HEAD_CAT3400 -7.703e-01  2.685e-01  -2.869 0.004135 ** 
## OCC_HEAD_CAT3420 -1.135e+00  2.450e-01  -4.630 3.73e-06 ***
## OCC_HEAD_CAT3500 -9.196e-01  2.000e-01  -4.598 4.35e-06 ***
## OCC_HEAD_CAT3510 -8.980e-01  3.076e-01  -2.920 0.003516 ** 
## OCC_HEAD_CAT3520 -1.265e+00  5.312e-01  -2.382 0.017263 *  
## OCC_HEAD_CAT3535 -1.007e+00  2.793e-01  -3.606 0.000314 ***
## OCC_HEAD_CAT3540 -6.553e-01  3.882e-01  -1.688 0.091489 .  
## OCC_HEAD_CAT3600 -1.324e+00  1.533e-01  -8.637  < 2e-16 ***
## OCC_HEAD_CAT3610 -5.423e-01  7.381e-01  -0.735 0.462491    
## OCC_HEAD_CAT3620 -9.643e-01  3.533e-01  -2.730 0.006360 ** 
## OCC_HEAD_CAT3630 -1.654e+00  3.888e-01  -4.254 2.13e-05 ***
## OCC_HEAD_CAT3640 -1.021e+00  3.538e-01  -2.887 0.003897 ** 
## OCC_HEAD_CAT3645 -1.075e+00  2.293e-01  -4.691 2.78e-06 ***
## OCC_HEAD_CAT3646 -2.737e-01  7.378e-01  -0.371 0.710644    
## OCC_HEAD_CAT3647 -1.308e+00  5.315e-01  -2.461 0.013862 *  
## OCC_HEAD_CAT3649 -8.238e-01  3.882e-01  -2.122 0.033880 *  
## OCC_HEAD_CAT3655 -1.066e+00  2.600e-01  -4.102 4.14e-05 ***
## OCC_HEAD_CAT3700 -4.956e-01  4.414e-01  -1.123 0.261613    
## OCC_HEAD_CAT3710 -2.984e-01  2.333e-01  -1.279 0.200977    
## OCC_HEAD_CAT3720 -8.934e-02  2.792e-01  -0.320 0.748941    
## OCC_HEAD_CAT3730 -7.268e-01  2.449e-01  -2.967 0.003015 ** 
## OCC_HEAD_CAT3740 -3.663e-01  2.340e-01  -1.565 0.117544    
## OCC_HEAD_CAT3800 -5.777e-01  1.960e-01  -2.948 0.003210 ** 
## OCC_HEAD_CAT3820 -2.742e-01  2.387e-01  -1.149 0.250768    
## OCC_HEAD_CAT3840 -1.022e+00  5.315e-01  -1.922 0.054644 .  
## OCC_HEAD_CAT3850 -4.686e-01  1.763e-01  -2.658 0.007881 ** 
## OCC_HEAD_CAT3860 -5.708e-01  7.384e-01  -0.773 0.439550    
## OCC_HEAD_CAT3910 -6.769e-01  3.272e-01  -2.069 0.038583 *  
## OCC_HEAD_CAT3930 -1.190e+00  1.666e-01  -7.145 1.00e-12 ***
## OCC_HEAD_CAT3940 -3.160e+00  7.380e-01  -4.282 1.88e-05 ***
## OCC_HEAD_CAT3945 -4.242e-01  7.391e-01  -0.574 0.566017    
## OCC_HEAD_CAT3955 -5.696e-01  4.416e-01  -1.290 0.197199    
## OCC_HEAD_CAT4000 -1.010e+00  2.177e-01  -4.641 3.54e-06 ***
## OCC_HEAD_CAT4010 -1.142e+00  1.588e-01  -7.191 7.14e-13 ***
## OCC_HEAD_CAT4020 -1.529e+00  1.625e-01  -9.412  < 2e-16 ***
## OCC_HEAD_CAT4030 -1.397e+00  1.918e-01  -7.287 3.54e-13 ***
## OCC_HEAD_CAT4040 -1.308e+00  2.342e-01  -5.584 2.45e-08 ***
## OCC_HEAD_CAT4050 -1.625e+00  1.720e-01  -9.447  < 2e-16 ***
## OCC_HEAD_CAT4060 -1.850e+00  2.405e-01  -7.693 1.65e-14 ***
## OCC_HEAD_CAT4110 -1.168e+00  1.782e-01  -6.554 6.02e-11 ***
## OCC_HEAD_CAT4120 -1.024e+00  7.386e-01  -1.386 0.165653    
## OCC_HEAD_CAT4130 -9.188e-01  3.534e-01  -2.600 0.009350 ** 
## OCC_HEAD_CAT4140 -1.485e+00  2.458e-01  -6.042 1.60e-09 ***
## OCC_HEAD_CAT4150 -1.499e+00  3.891e-01  -3.851 0.000119 ***
## OCC_HEAD_CAT4160 -1.336e+00  5.322e-01  -2.510 0.012088 *  
## OCC_HEAD_CAT4200 -9.276e-01  1.757e-01  -5.279 1.34e-07 ***
## OCC_HEAD_CAT4210 -9.241e-01  1.998e-01  -4.624 3.83e-06 ***
## OCC_HEAD_CAT4220 -1.346e+00  1.560e-01  -8.631  < 2e-16 ***
## OCC_HEAD_CAT4230 -1.779e+00  1.667e-01 -10.676  < 2e-16 ***
## OCC_HEAD_CAT4240 -6.150e-01  5.352e-01  -1.149 0.250495    
## OCC_HEAD_CAT4250 -1.787e+00  1.603e-01 -11.148  < 2e-16 ***
## OCC_HEAD_CAT4320 -6.196e-01  2.390e-01  -2.593 0.009533 ** 
## OCC_HEAD_CAT4350 -1.820e+00  2.684e-01  -6.779 1.32e-11 ***
## OCC_HEAD_CAT4400 -9.847e-01  4.412e-01  -2.232 0.025641 *  
## OCC_HEAD_CAT4420 -3.684e+00  7.400e-01  -4.979 6.56e-07 ***
## OCC_HEAD_CAT4430 -1.380e+00  4.417e-01  -3.125 0.001788 ** 
## OCC_HEAD_CAT4460 -2.079e+00  5.315e-01  -3.911 9.27e-05 ***
## OCC_HEAD_CAT4465 -9.334e-01  4.409e-01  -2.117 0.034290 *  
## OCC_HEAD_CAT4500 -1.377e+00  2.297e-01  -5.995 2.14e-09 ***
## OCC_HEAD_CAT4510 -1.655e+00  1.861e-01  -8.897  < 2e-16 ***
## OCC_HEAD_CAT4520 -1.474e+00  3.274e-01  -4.501 6.87e-06 ***
## OCC_HEAD_CAT4530 -1.307e+00  5.315e-01  -2.459 0.013962 *  
## OCC_HEAD_CAT4540 -1.282e+00  3.882e-01  -3.303 0.000960 ***
## OCC_HEAD_CAT4600 -2.085e+00  1.651e-01 -12.633  < 2e-16 ***
## OCC_HEAD_CAT4610 -1.599e+00  1.651e-01  -9.684  < 2e-16 ***
## OCC_HEAD_CAT4620 -1.419e+00  2.918e-01  -4.862 1.19e-06 ***
## OCC_HEAD_CAT4640 -8.281e-01  5.311e-01  -1.559 0.119018    
## OCC_HEAD_CAT4650 -1.602e+00  3.886e-01  -4.123 3.78e-05 ***
## OCC_HEAD_CAT4700 -7.333e-01  1.551e-01  -4.729 2.31e-06 ***
## OCC_HEAD_CAT4710  1.683e-02  1.857e-01   0.091 0.927810    
## OCC_HEAD_CAT4720 -1.620e+00  1.641e-01  -9.873  < 2e-16 ***
## OCC_HEAD_CAT4740 -6.522e-01  3.532e-01  -1.847 0.064846 .  
## OCC_HEAD_CAT4750 -7.527e-01  3.080e-01  -2.444 0.014561 *  
## OCC_HEAD_CAT4760 -1.026e+00  1.577e-01  -6.507 8.26e-11 ***
## OCC_HEAD_CAT4800 -6.471e-01  2.920e-01  -2.216 0.026735 *  
## OCC_HEAD_CAT4810 -4.802e-01  1.909e-01  -2.516 0.011902 *  
## OCC_HEAD_CAT4820  2.689e-01  2.919e-01   0.921 0.357047    
## OCC_HEAD_CAT4830 -1.141e+00  4.413e-01  -2.586 0.009740 ** 
## OCC_HEAD_CAT4840 -5.371e-01  1.885e-01  -2.849 0.004394 ** 
## OCC_HEAD_CAT4850 -3.647e-01  1.715e-01  -2.127 0.033447 *  
## OCC_HEAD_CAT4900 -1.588e+00  2.918e-01  -5.443 5.42e-08 ***
## OCC_HEAD_CAT4920 -8.009e-01  1.994e-01  -4.017 5.95e-05 ***
## OCC_HEAD_CAT4930 -1.093e-01  5.310e-01  -0.206 0.836865    
## OCC_HEAD_CAT4940 -5.353e-01  3.532e-01  -1.515 0.129709    
## OCC_HEAD_CAT4950 -1.424e+00  2.699e-01  -5.275 1.37e-07 ***
## OCC_HEAD_CAT4965 -1.517e+00  2.460e-01  -6.165 7.46e-10 ***
## OCC_HEAD_CAT5000 -7.010e-01  1.579e-01  -4.440 9.15e-06 ***
## OCC_HEAD_CAT5010 -1.281e+00  5.310e-01  -2.413 0.015843 *  
## OCC_HEAD_CAT5100 -1.027e+00  3.076e-01  -3.339 0.000844 ***
## OCC_HEAD_CAT5110 -1.027e+00  2.207e-01  -4.653 3.34e-06 ***
## OCC_HEAD_CAT5120 -9.336e-01  1.884e-01  -4.956 7.40e-07 ***
## OCC_HEAD_CAT5130 -1.194e+00  7.383e-01  -1.617 0.105897    
## OCC_HEAD_CAT5140 -9.471e-01  3.272e-01  -2.895 0.003810 ** 
## OCC_HEAD_CAT5150 -8.730e-01  4.415e-01  -1.977 0.048030 *  
## OCC_HEAD_CAT5160 -9.351e-01  2.522e-01  -3.708 0.000210 ***
## OCC_HEAD_CAT5165 -8.093e-01  4.411e-01  -1.835 0.066616 .  
## OCC_HEAD_CAT5200 -6.619e-01  4.412e-01  -1.500 0.133584    
## OCC_HEAD_CAT5220 -5.421e-01  3.276e-01  -1.655 0.098020 .  
## OCC_HEAD_CAT5230 -1.374e+00  3.887e-01  -3.535 0.000411 ***
## OCC_HEAD_CAT5240 -1.033e+00  1.612e-01  -6.406 1.60e-10 ***
## OCC_HEAD_CAT5260 -9.706e-01  3.534e-01  -2.747 0.006039 ** 
## OCC_HEAD_CAT5300 -1.759e+00  2.599e-01  -6.768 1.42e-11 ***
## OCC_HEAD_CAT5310 -1.519e+00  3.077e-01  -4.935 8.20e-07 ***
## OCC_HEAD_CAT5320 -1.266e+00  3.077e-01  -4.115 3.91e-05 ***
## OCC_HEAD_CAT5330 -7.769e-01  3.076e-01  -2.526 0.011556 *  
## OCC_HEAD_CAT5340 -7.652e-01  3.272e-01  -2.338 0.019396 *  
## OCC_HEAD_CAT5350 -3.792e-01  7.380e-01  -0.514 0.607419    
## OCC_HEAD_CAT5360 -7.572e-01  3.882e-01  -1.950 0.051189 .  
## OCC_HEAD_CAT5400 -1.482e+00  2.021e-01  -7.331 2.56e-13 ***
## OCC_HEAD_CAT5410 -8.822e-01  3.533e-01  -2.497 0.012555 *  
## OCC_HEAD_CAT5420 -1.823e+00  2.921e-01  -6.242 4.59e-10 ***
## OCC_HEAD_CAT5500 -9.099e-01  5.314e-01  -1.712 0.086887 .  
## OCC_HEAD_CAT5510 -1.260e+00  1.844e-01  -6.834 9.01e-12 ***
## OCC_HEAD_CAT5520 -7.945e-01  2.213e-01  -3.591 0.000332 ***
## OCC_HEAD_CAT5530 -9.529e-01  7.379e-01  -1.291 0.196613    
## OCC_HEAD_CAT5540 -5.565e-01  3.275e-01  -1.699 0.089300 .  
## OCC_HEAD_CAT5550 -6.211e-01  2.019e-01  -3.077 0.002103 ** 
## OCC_HEAD_CAT5560 -3.728e-01  3.887e-01  -0.959 0.337593    
## OCC_HEAD_CAT5600 -8.252e-01  2.517e-01  -3.279 0.001047 ** 
## OCC_HEAD_CAT5610 -1.029e+00  1.999e-01  -5.147 2.73e-07 ***
## OCC_HEAD_CAT5620 -1.207e+00  1.597e-01  -7.557 4.69e-14 ***
## OCC_HEAD_CAT5630 -5.669e-01  5.310e-01  -1.068 0.285737    
## OCC_HEAD_CAT5700 -1.133e+00  1.654e-01  -6.852 7.94e-12 ***
## OCC_HEAD_CAT5810 -1.084e+00  2.685e-01  -4.036 5.49e-05 ***
## OCC_HEAD_CAT5820 -2.257e+00  7.378e-01  -3.060 0.002225 ** 
## OCC_HEAD_CAT5840 -1.019e+00  2.252e-01  -4.523 6.21e-06 ***
## OCC_HEAD_CAT5850 -8.806e-01  3.535e-01  -2.491 0.012750 *  
## OCC_HEAD_CAT5860 -1.163e+00  2.211e-01  -5.262 1.47e-07 ***
## OCC_HEAD_CAT5910 -1.555e+00  5.315e-01  -2.927 0.003440 ** 
## OCC_HEAD_CAT5940 -1.477e+00  2.685e-01  -5.501 3.92e-08 ***
## OCC_HEAD_CAT6005 -7.686e-01  2.399e-01  -3.204 0.001363 ** 
## OCC_HEAD_CAT6010 -1.172e-01  7.380e-01  -0.159 0.873818    
## OCC_HEAD_CAT6020 -1.496e+00  7.385e-01  -2.026 0.042856 *  
## OCC_HEAD_CAT6050 -1.383e+00  1.915e-01  -7.222 5.72e-13 ***
## OCC_HEAD_CAT6100  1.300e-01  3.890e-01   0.334 0.738294    
## OCC_HEAD_CAT6130 -1.100e+00  3.280e-01  -3.353 0.000803 ***
## OCC_HEAD_CAT6200 -3.795e-01  1.594e-01  -2.381 0.017288 *  
## OCC_HEAD_CAT6220 -1.312e+00  3.305e-01  -3.970 7.26e-05 ***
## OCC_HEAD_CAT6230 -8.731e-01  1.731e-01  -5.043 4.70e-07 ***
## OCC_HEAD_CAT6240 -1.175e+00  2.343e-01  -5.014 5.48e-07 ***
## OCC_HEAD_CAT6250 -9.537e-01  2.824e-01  -3.377 0.000737 ***
## OCC_HEAD_CAT6260 -9.973e-01  1.600e-01  -6.234 4.85e-10 ***
## OCC_HEAD_CAT6300 -9.767e-01  5.332e-01  -1.832 0.067007 .  
## OCC_HEAD_CAT6310 -2.594e-01  7.380e-01  -0.351 0.725259    
## OCC_HEAD_CAT6320 -5.640e-01  2.118e-01  -2.663 0.007762 ** 
## OCC_HEAD_CAT6330 -1.943e+00  3.333e-01  -5.830 5.79e-09 ***
## OCC_HEAD_CAT6355 -5.933e-01  1.902e-01  -3.119 0.001821 ** 
## OCC_HEAD_CAT6360 -4.837e-01  5.314e-01  -0.910 0.362734    
## OCC_HEAD_CAT6400 -6.649e-01  3.300e-01  -2.015 0.043964 *  
## OCC_HEAD_CAT6420 -1.245e+00  1.953e-01  -6.378 1.92e-10 ***
## OCC_HEAD_CAT6430 -6.886e-01  7.388e-01  -0.932 0.351346    
## OCC_HEAD_CAT6440 -5.080e-01  1.933e-01  -2.628 0.008596 ** 
## OCC_HEAD_CAT6460 -9.317e-01  7.380e-01  -1.262 0.206837    
## OCC_HEAD_CAT6500 -3.352e-01  7.380e-01  -0.454 0.649715    
## OCC_HEAD_CAT6515 -1.135e+00  2.613e-01  -4.345 1.42e-05 ***
## OCC_HEAD_CAT6520 -4.164e-01  3.888e-01  -1.071 0.284272    
## OCC_HEAD_CAT6530 -5.942e-01  7.387e-01  -0.804 0.421209    
## OCC_HEAD_CAT6540 -7.754e-01  5.315e-01  -1.459 0.144637    
## OCC_HEAD_CAT6600 -1.078e+00  4.427e-01  -2.436 0.014885 *  
## OCC_HEAD_CAT6660 -4.965e-01  3.533e-01  -1.405 0.159952    
## OCC_HEAD_CAT6700  3.946e-01  5.324e-01   0.741 0.458614    
## OCC_HEAD_CAT6710 -3.046e-01  4.421e-01  -0.689 0.490915    
## OCC_HEAD_CAT6730 -9.334e-01  2.687e-01  -3.473 0.000518 ***
## OCC_HEAD_CAT6740 -4.214e-01  7.400e-01  -0.569 0.569038    
## OCC_HEAD_CAT6750 -5.845e-01  5.329e-01  -1.097 0.272790    
## OCC_HEAD_CAT6765 -8.098e-01  5.318e-01  -1.523 0.127861    
## OCC_HEAD_CAT6800 -5.114e-01  7.381e-01  -0.693 0.488397    
## OCC_HEAD_CAT6820 -2.537e+00  4.413e-01  -5.750 9.34e-09 ***
## OCC_HEAD_CAT6830 -5.208e-01  7.384e-01  -0.705 0.480643    
## OCC_HEAD_CAT6840 -3.294e-01  7.380e-01  -0.446 0.655426    
## OCC_HEAD_CAT6920  2.002e-01  7.382e-01   0.271 0.786278    
## OCC_HEAD_CAT6940  1.903e-01  5.314e-01   0.358 0.720195    
## OCC_HEAD_CAT7000 -5.154e-01  1.822e-01  -2.829 0.004678 ** 
## OCC_HEAD_CAT7010 -1.490e+00  2.595e-01  -5.742 9.78e-09 ***
## OCC_HEAD_CAT7020 -6.527e-01  2.518e-01  -2.593 0.009548 ** 
## OCC_HEAD_CAT7030 -5.200e-01  7.380e-01  -0.705 0.481096    
## OCC_HEAD_CAT7040 -5.654e-01  7.384e-01  -0.766 0.443912    
## OCC_HEAD_CAT7050 -2.772e-01  7.380e-01  -0.376 0.707278    
## OCC_HEAD_CAT7100 -3.327e-01  3.533e-01  -0.942 0.346311    
## OCC_HEAD_CAT7110 -5.533e-01  4.415e-01  -1.253 0.210154    
## OCC_HEAD_CAT7120 -1.452e+00  7.384e-01  -1.967 0.049257 *  
## OCC_HEAD_CAT7130 -8.145e-01  4.413e-01  -1.845 0.065021 .  
## OCC_HEAD_CAT7140 -4.914e-01  2.685e-01  -1.830 0.067341 .  
## OCC_HEAD_CAT7150 -3.750e-01  2.797e-01  -1.341 0.180018    
## OCC_HEAD_CAT7200 -9.077e-01  1.716e-01  -5.289 1.27e-07 ***
## OCC_HEAD_CAT7210 -7.740e-01  2.253e-01  -3.436 0.000594 ***
## OCC_HEAD_CAT7220 -5.897e-01  2.117e-01  -2.785 0.005367 ** 
## OCC_HEAD_CAT7240 -1.156e+00  7.380e-01  -1.567 0.117226    
## OCC_HEAD_CAT7260 -9.670e-01  3.078e-01  -3.141 0.001691 ** 
## OCC_HEAD_CAT7300 -1.002e+00  5.311e-01  -1.886 0.059390 .  
## OCC_HEAD_CAT7315 -5.031e-01  2.148e-01  -2.342 0.019225 *  
## OCC_HEAD_CAT7320 -7.090e-01  4.413e-01  -1.606 0.108230    
## OCC_HEAD_CAT7330 -6.973e-01  2.145e-01  -3.251 0.001156 ** 
## OCC_HEAD_CAT7340 -8.377e-01  2.395e-01  -3.497 0.000473 ***
## OCC_HEAD_CAT7350 -6.009e-01  3.276e-01  -1.834 0.066689 .  
## OCC_HEAD_CAT7410 -4.631e-01  3.079e-01  -1.504 0.132600    
## OCC_HEAD_CAT7420 -4.222e-01  2.454e-01  -1.721 0.085362 .  
## OCC_HEAD_CAT7430 -1.191e-01  5.311e-01  -0.224 0.822528    
## OCC_HEAD_CAT7440 -1.299e-01  7.388e-01  -0.176 0.860390    
## OCC_HEAD_CAT7510 -1.034e+00  4.414e-01  -2.342 0.019233 *  
## OCC_HEAD_CAT7540 -8.786e-01  5.311e-01  -1.654 0.098111 .  
## OCC_HEAD_CAT7550 -1.007e+00  7.388e-01  -1.364 0.172766    
## OCC_HEAD_CAT7560 -1.027e+00  7.381e-01  -1.391 0.164343    
## OCC_HEAD_CAT7610 -4.685e-01  4.417e-01  -1.061 0.288822    
## OCC_HEAD_CAT7630 -8.645e-01  3.531e-01  -2.448 0.014388 *  
## OCC_HEAD_CAT7700 -5.672e-01  1.608e-01  -3.527 0.000423 ***
## OCC_HEAD_CAT7710 -5.478e-01  5.316e-01  -1.030 0.302871    
## OCC_HEAD_CAT7720 -1.092e+00  2.599e-01  -4.201 2.69e-05 ***
## OCC_HEAD_CAT7730 -4.881e-01  3.081e-01  -1.584 0.113208    
## OCC_HEAD_CAT7740 -8.063e-01  4.424e-01  -1.822 0.068437 .  
## OCC_HEAD_CAT7750 -1.044e+00  1.725e-01  -6.053 1.50e-09 ***
## OCC_HEAD_CAT7800 -1.585e+00  3.297e-01  -4.807 1.56e-06 ***
## OCC_HEAD_CAT7810 -1.010e+00  2.107e-01  -4.795 1.66e-06 ***
## OCC_HEAD_CAT7840 -9.548e-01  3.093e-01  -3.087 0.002028 ** 
## OCC_HEAD_CAT7850 -1.417e+00  5.319e-01  -2.665 0.007726 ** 
## OCC_HEAD_CAT7855 -1.135e+00  2.924e-01  -3.881 0.000105 ***
## OCC_HEAD_CAT7900 -4.594e-01  2.522e-01  -1.822 0.068511 .  
## OCC_HEAD_CAT7920 -1.363e-01  5.312e-01  -0.257 0.797476    
## OCC_HEAD_CAT7930 -3.591e-01  5.314e-01  -0.676 0.499179    
## OCC_HEAD_CAT7950 -7.667e-01  3.276e-01  -2.341 0.019281 *  
## OCC_HEAD_CAT8000 -1.027e+00  3.079e-01  -3.337 0.000853 ***
## OCC_HEAD_CAT8010 -1.052e+00  3.532e-01  -2.979 0.002902 ** 
## OCC_HEAD_CAT8030 -5.823e-01  2.520e-01  -2.311 0.020863 *  
## OCC_HEAD_CAT8040 -5.201e-01  4.415e-01  -1.178 0.238795    
## OCC_HEAD_CAT8100 -5.299e-01  3.278e-01  -1.616 0.106045    
## OCC_HEAD_CAT8120 -3.762e-01  7.386e-01  -0.509 0.610583    
## OCC_HEAD_CAT8130 -7.230e-01  5.314e-01  -1.361 0.173657    
## OCC_HEAD_CAT8140 -6.587e-01  1.845e-01  -3.570 0.000359 ***
## OCC_HEAD_CAT8200 -1.121e+00  4.418e-01  -2.538 0.011186 *  
## OCC_HEAD_CAT8210 -2.204e-01  5.342e-01  -0.413 0.679893    
## OCC_HEAD_CAT8220 -7.656e-01  2.342e-01  -3.269 0.001086 ** 
## OCC_HEAD_CAT8255 -1.152e+00  3.280e-01  -3.512 0.000448 ***
## OCC_HEAD_CAT8300 -1.294e+00  2.693e-01  -4.807 1.57e-06 ***
## OCC_HEAD_CAT8310 -6.589e-01  7.401e-01  -0.890 0.373376    
## OCC_HEAD_CAT8320 -1.026e+00  2.925e-01  -3.506 0.000457 ***
## OCC_HEAD_CAT8350 -1.457e+00  5.315e-01  -2.741 0.006148 ** 
## OCC_HEAD_CAT8360 -9.967e-01  5.408e-01  -1.843 0.065347 .  
## OCC_HEAD_CAT8410 -1.172e+00  4.415e-01  -2.654 0.007978 ** 
## OCC_HEAD_CAT8420 -8.605e-01  7.381e-01  -1.166 0.243700    
## OCC_HEAD_CAT8430 -1.018e+00  5.320e-01  -1.914 0.055649 .  
## OCC_HEAD_CAT8440 -9.722e-01  7.440e-01  -1.307 0.191322    
## OCC_HEAD_CAT8450 -5.443e-01  3.897e-01  -1.397 0.162568    
## OCC_HEAD_CAT8500 -7.227e-01  3.532e-01  -2.046 0.040795 *  
## OCC_HEAD_CAT8520 -1.298e-01  7.378e-01  -0.176 0.860400    
## OCC_HEAD_CAT8530 -1.105e+00  3.913e-01  -2.823 0.004778 ** 
## OCC_HEAD_CAT8540 -6.584e-01  3.890e-01  -1.692 0.090645 .  
## OCC_HEAD_CAT8550 -1.204e+00  7.380e-01  -1.631 0.102911    
## OCC_HEAD_CAT8600  9.393e-02  5.316e-01   0.177 0.859748    
## OCC_HEAD_CAT8610 -2.442e-01  7.381e-01  -0.331 0.740780    
## OCC_HEAD_CAT8620 -5.935e-01  2.921e-01  -2.032 0.042225 *  
## OCC_HEAD_CAT8630 -6.653e-01  7.378e-01  -0.902 0.367214    
## OCC_HEAD_CAT8640 -5.712e-02  3.535e-01  -0.162 0.871627    
## OCC_HEAD_CAT8650 -7.846e-01  2.522e-01  -3.111 0.001872 ** 
## OCC_HEAD_CAT8710 -1.172e+00  3.578e-01  -3.275 0.001062 ** 
## OCC_HEAD_CAT8720 -6.421e-01  3.534e-01  -1.817 0.069231 .  
## OCC_HEAD_CAT8730 -4.185e-01  5.314e-01  -0.788 0.430926    
## OCC_HEAD_CAT8740 -7.010e-01  1.812e-01  -3.868 0.000111 ***
## OCC_HEAD_CAT8760 -5.435e-01  7.385e-01  -0.736 0.461818    
## OCC_HEAD_CAT8800 -1.155e+00  2.019e-01  -5.722 1.10e-08 ***
## OCC_HEAD_CAT8810 -9.967e-01  2.692e-01  -3.703 0.000215 ***
## OCC_HEAD_CAT8830 -1.150e+00  5.314e-01  -2.163 0.030553 *  
## OCC_HEAD_CAT8860 -5.068e-01  5.336e-01  -0.950 0.342295    
## OCC_HEAD_CAT8920 -1.189e+00  4.412e-01  -2.695 0.007057 ** 
## OCC_HEAD_CAT8940 -3.897e-01  5.312e-01  -0.734 0.463181    
## OCC_HEAD_CAT8950 -8.867e-01  4.415e-01  -2.009 0.044622 *  
## OCC_HEAD_CAT8965 -8.513e-01  1.906e-01  -4.466 8.12e-06 ***
## OCC_HEAD_CAT9000 -7.810e-01  1.717e-01  -4.549 5.49e-06 ***
## OCC_HEAD_CAT9030 -3.004e-02  2.592e-01  -0.116 0.907738    
## OCC_HEAD_CAT9040  1.098e-01  4.413e-01   0.249 0.803553    
## OCC_HEAD_CAT9050 -8.158e-01  5.309e-01  -1.537 0.124458    
## OCC_HEAD_CAT9110 -4.231e-01  5.312e-01  -0.796 0.425784    
## OCC_HEAD_CAT9120 -9.920e-01  1.786e-01  -5.553 2.92e-08 ***
## OCC_HEAD_CAT9130 -6.918e-01  1.478e-01  -4.680 2.93e-06 ***
## OCC_HEAD_CAT9140 -1.289e+00  1.724e-01  -7.480 8.40e-14 ***
## OCC_HEAD_CAT9150 -1.135e+00  3.281e-01  -3.460 0.000544 ***
## OCC_HEAD_CAT9200  3.541e-02  4.414e-01   0.080 0.936074    
## OCC_HEAD_CAT9230  2.376e-02  7.381e-01   0.032 0.974325    
## OCC_HEAD_CAT9240 -6.261e-01  3.889e-01  -1.610 0.107456    
## OCC_HEAD_CAT9260 -4.724e-01  5.310e-01  -0.890 0.373721    
## OCC_HEAD_CAT9310 -4.973e+00  7.381e-01  -6.738 1.75e-11 ***
## OCC_HEAD_CAT9350 -1.878e+00  3.277e-01  -5.732 1.04e-08 ***
## OCC_HEAD_CAT9360 -1.732e+00  2.797e-01  -6.193 6.24e-10 ***
## OCC_HEAD_CAT9410 -6.822e-01  3.884e-01  -1.757 0.079048 .  
## OCC_HEAD_CAT9420 -4.126e-01  7.388e-01  -0.558 0.576525    
## OCC_HEAD_CAT9500 -2.593e-01  5.313e-01  -0.488 0.625481    
## OCC_HEAD_CAT9510 -5.231e-01  3.275e-01  -1.597 0.110240    
## OCC_HEAD_CAT9520 -9.587e-01  7.382e-01  -1.299 0.194087    
## OCC_HEAD_CAT9600 -7.225e-01  1.585e-01  -4.557 5.27e-06 ***
## OCC_HEAD_CAT9610 -1.422e+00  2.120e-01  -6.707 2.15e-11 ***
## OCC_HEAD_CAT9620 -1.182e+00  1.593e-01  -7.420 1.32e-13 ***
## OCC_HEAD_CAT9630 -7.199e-01  5.313e-01  -1.355 0.175483    
## OCC_HEAD_CAT9640 -1.158e+00  1.972e-01  -5.875 4.44e-09 ***
## OCC_HEAD_CAT9720 -1.074e+00  3.537e-01  -3.037 0.002399 ** 
## OCC_HEAD_CAT9740  2.408e-01  7.381e-01   0.326 0.744233    
## OCC_HEAD_CAT9750 -8.879e-01  5.314e-01  -1.671 0.094800 .  
## OCC_HEAD_CAT9800 -2.023e-01  2.171e-01  -0.932 0.351292    
## OCC_HEAD_CAT9810 -6.493e-01  1.861e-01  -3.489 0.000488 ***
## OCC_HEAD_CAT9820 -6.497e-01  2.921e-01  -2.224 0.026184 *  
## OCC_HEAD_CAT9830 -6.934e-01  2.250e-01  -3.082 0.002063 ** 
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.7243 on 6488 degrees of freedom
## Multiple R-squared:  0.4413,	Adjusted R-squared:  0.3998 
## F-statistic: 10.63 on 482 and 6488 DF,  p-value: < 2.2e-16
```

```
## [1] 0.4413493
```

```
## [1] 0.5586507
```


 
