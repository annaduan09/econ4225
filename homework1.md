---
title: "ECON4225 Homework 1"
output: 
  pdf_document:
    number_sections: no
    keep_md: yes
date: "10-14-2025"
author: "Anna Duan"
---


# Part 1: Overview of the Dataset 
## Question 1: household and variable count
This dataset has 9066 households and 38 variables, including the household ID.

```
## [1] "PSID row count: 9066"
```

```
## [1] "PSID variable count: 38"
```

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
The average household income is $78,265.69. This is lower than the $142,000 reported by the SCF (based on class slides for Section 1.2, slide 9). One possible reason for this difference is that the SCF intentionally oversamples wealthy households to collect information about the income and wealth patterns at the top of the income distribution. In addition to SCF's intentional focus on a high-income subset of the population, other differences that may create differences in the mean household income collected include SCF's smaller sample size (6k, compared to PSID's 10k) and lower frequency. 

SCF also surveys a smaller (6k) group compared to PSID (10k). 

```
## [1] "Mean household income: 78265.69"
```

## Question 4: income range   
The household incomes in the dataset have a wide range: the lowest is -$267,900 and the highest is $2,125,100. According to the codebook, the households with negative incomes likely incurred business or farm losses. This may include losses from business investments, farming, or other financial decisions. 

```
## [1] "Lowest household income: -267900"
```

```
## [1] "Highest household income: 2125100"
```

## Question 5: age of household head's spouse     
Of the 4,523 households with a spouse present, the average age of the spouse is 45.64 years.

```
## [1] "Mean spouse age: 45.64"
```

## Question 6: household size    
The average household in the dataset has 2.6 members. Households with only 1 member make up 28.45% of the data. Households with 5 or more members make up 11.29%.   


----------------------------
 size_group   count    pct  
------------ ------- -------
     1        2579    28.45 

    2–4       5463    60.26 

     5+       1024    11.29 
----------------------------

Table: Percentage share of PSID households by size

  
The histogram below shows the distribution of households by member count in the PSID dataset. Compared to the SCF histogram shown in class, the PSID histogram has fewer 2-member households and more 3-5 member households. The PSID dataset has 30.43% two-member households compared to the nearly 35% shown on Slide 2 of Section 1.1. PSID has a slightly larger share of households with 3 members: 15.95%, compared to the slide's 15%; a 13.88% share of 4-member households, compared to the slide's 12.5%; and a 7.2% share of 5-member households, compared to just past 5% in the slide.   

![](homework1_files/figure-latex/hh size hist-1.pdf)<!-- --> 

# Part 2: Income Distribution    
## Question 1: distribution of household income  
The following histogram shows the distribution of household incomes in the PSID, with outliers exceeding the 99th percentile ($396,420) omitted. The distribution is right-skewed, meaning there is a long trailing tail of outliers to the right. The median of $55,090 is lower than the mean of $78,266. The majority of households earn less than $100,682, which is the 75th percentile. 25% of households surveyed have higher household incomes, up to $2.125 million. 137 households have no income, and three households have negative income, with the lowest income being -$267,900.


--------------------------------------------------------
  Min.     1st Qu.   Median   Mean    3rd Qu.    Max.   
--------- --------- -------- ------- --------- ---------
 -267900    28000    55090    78266   100681    2125100 
--------------------------------------------------------

Table: Distribution of Household Incomes

![](homework1_files/figure-latex/hh income hist-1.pdf)<!-- --> 

## Question 2: household income Lorenz curve   
The following Lorenz curve visualizes the cumulative share of households (x) against the cumulative share of income (y). The dotted line is what the curve would look like at perfect equality, where the bottom 50% of households possess 50% of total household income. The solid red line represents the relationship between cumulative household share and cumulative income share in reality.
  
![](homework1_files/figure-latex/hh income lorenz-1.pdf)<!-- --> 


We see on this curve that the lowest earning 50% of households in the PSID account for only 18% of total household income, and that the bottom 75% of households account for 42% of income. By contrast, the top 10% of highest earning households account for about a third of all household income, and the top 1% of households make around 8%. In this dataset, we can tell that high-earning households account for more than their proportional share of household income, indicating income inequality within the sample.      


## Question 3: total household income coefficient of variation   
To further quantify the level of income inequality in the dataset, we can calculate the coefficient of variation by dividing the standard deviation in household income by the mean household income. This produces a coefficient of variation of 1.15, which is lower compared to the SCF. Based on slide 14 of Section 1.2 in the lecture slides, the coefficient of variation derived from the SCF was 5.31 in 2022. By this measure, there is less income inequality in the PSID sample than in the SCF sample. 

```
## [1] "Coefficient of variation of household income: 1.152"
```


## Question 4: adjusted total household income Lorenz curve    
When we adjust household income based on the number of household heads present, our Lorenz curve moves closer to the line of perfect equality, meaning that adjusting household income by the number of household heads decreases income inequality. This is intuitive: we are now adjusting for the number of potential earners in a household, allowing for a more fair comparison between households with one and two heads.  

On the yellow curve representing the relationship between adjusted income share and household share, we see that the bottom 50% of households account for 21% of income, compared to the 18% on the non-adjusted curve. This indicates that some of the inequality among households may be attributed to differences in household size and the number of earners. 

![](homework1_files/figure-latex/lorenz curve comparison-1.pdf)<!-- --> 

## Question 5: household income percentile ratios   
The table below displays the 30th, 50th, 90th, and 99th percentiles of household income in the dataset. Based on these percentiles, we know that 30% of the sampled households earn $33,107.50 or less per year; 50% earn $55,090 or less; 90% earn $161,188 or less; and 99% earn $396,420 or less. The wide gap between the 50th and the 90th percentile is a clear marker of income inequality. 

-------------------------
 percentile     value    
------------ ------------
    30th      $33,107.50 

    50th      $55,090.00 

    90th       $161,188  

    99th       $396,420  
-------------------------

Table: PSID Household Income Percentiles
  
The percentile ratios in the following table further illustrate an unequal income distribution, where households at the top earn several times more than those in the middle or bottom. The 90-30 ratio is 4.87, meaning households at the top earn 4.87 times what households at the bottom earn. The 90-50 ratio is 2.93, meaning households at the top earn 2.93 times what households in the middle earn. The 30-10 ratio is 2.67, meaning there is income inequality within the bottom as well, with those at the 30th percentile earning 2.67 times what those at the 10th percentile earn. The 99-50 ratio is 7.2, meaning that households at the very top of the distribution earn 7.2 times what households in the middle earn, indicating extreme concentration of income at the very top. 

The numbers in the SCF are even more drastic: in 2022, the 90-50 ratio was 3.54 and the 99-50 ratio was 17.05. This may be due to SCF's sampling again: by over-sampling the ultra-wealthy, the SCF likely captures much higher incomes in the upper end of its distribution than the PSID does. 


--------------------------
 percentile_ratio   value 
------------------ -------
      90-30         4.87  

      90-50         2.93  

      30-10         2.67  

      99-50          7.2  
--------------------------

Table: PSID Household Income Percentile Ratios


## Question 6: mean household income and share by quintile    
The following table further illustrates the income inequality among PSID households: the highest disparities between consecutive quintiles are between quintiles 1 and 2 and quintiles 4 and 5. Quintile 2 has a mean income of $33,188, 2.76 times the first quintile's mean income of $12,003. The second quintile's income share of 8.5% is 2.74 times that of the first quintile (3.1%). The fifth quintile's income of $199,894 is 2.21 times that of the fourth quintile ($90,408). The fifth quintile's income share of 51.1% is 2.21 times that of the fourth quintile. It's also notable that the income share of the top quintile is greater than that of the 4 lower quintiles combined, visualized in the plot below. Taken together, this shows the high overall income inequality among PSID households, as well as the heightened inequality at the two ends of the distribution. 

Compared to SCF (Section 1.2, slide 9), the average income is lower for all quintiles in the PSID. The first four quintiles have a higher income share in the PSID, while the fifth quintile has a higher income share in the SCF. This pattern once again speaks to the difference in sampling across the two surveys. 


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


## Question 7: mean household income and share for the top 1%   
As discussed in class, looking at mean incomes and income shares by quintiles can obscure the inequality within the top of the distribution. Looking at the top 1% of households, we see that their mean income ($639,974) is 8.81 times that of the bottom 99% ($72,570), and 3.2 times that of the top quintile ($199,894). In terms of income share, the top 1% accounts for 8% of all household income, making up nearly one-sixth of the top quintile's share. Even within the top quintile, there is drastic inequality between the highest and lowest earners.   

Compared to the SCF (based on Section 1.2 Slide 9), the top 1% has a lower income share and mean income in the PSID (SCF reported 22.4% and $3.18 million in 2022).

-----------------------------------------
   group      income_share   mean_income 
------------ -------------- -------------
 bottom 99%       92%          $72,570   

   top 1%          8%         $639,974   
-----------------------------------------

Table: Share of total household income and mean income held by the top 1%

# Part 3: Labor Income    
## Question 1: household earnings share and mean by quintile     
We can create a variable for the total labor income by adding the LABOR_HEAD and LABOR_SPOUSE. Looking at total labor earnings of households, the inequality within the bottom of the distribution is much higher. The table below lists the mean household earnings and share of household earnings by quintile. The second quintile of households ($14,946) earns more than 500 times the labor income of the first quintile ($26). The earnings inequality at the top of the distribution is lower: the ratio between the mean labor income of the fifth and fourth quintiles is 2.36. 


---------------------------------------------------
 quintile   labor_income_share   mean_labor_income 
---------- -------------------- -------------------
    1              0.0%                 $26        

    2              5.0%               $14,946      

    3             13.2%               $39,141      

    4             24.3%               $72,045      

    5             57.4%              $170,314      
---------------------------------------------------

Table: Share of labor income and mean labor income by quintile


## Question 2: total household income vs household earnings by quintile    
Side by side, we can see that the distribution of earnings share is more unequal. The bottom quintile's share of earnings rounds to zero, while the bottom quintile's share of total household income is 3.1%. Quintiles 2 and 3 also hold smaller shares of earnings than they do total income. Quintile 4 has a slightly higher share of earnings than total income, and quintile 5's share of earnings is higher than total income by 6.3 percentage points. Compared to the distribution of total income, earnings is more unevenly distributed, with higher percentage shares in the top 2 quintiles.     


------------------------------------------------
 quintile   total_income_share   earnings_share 
---------- -------------------- ----------------
    1              3.1%               0.0%      

    2              8.5%               5.0%      

    3             14.3%              13.2%      

    4             23.1%              24.3%      

    5             51.1%              57.4%      
------------------------------------------------

Table: Total income vs earnings quintile shares

Calculating the coefficient of variation for both metrics confirms this: earnings have a coefficient of variation of 1.36, compared to 1.15 for household income. This indicates that there is more inequality in earnings than in income.    


---------------------------
       metric          cv  
-------------------- ------
  Household Income    1.15 

 Household Earnings   1.36 
---------------------------

Table: Coefficient of Variation: Household Income and Earnings

This trend is seen when plotted on a Lorenz curve, as well. The curve representing cumulative households against cumulative earnings is more far away from the line of perfect equality, indicating that its distribution is more unequal than that of household income. As discussed in class, redistributive policies like social insurance and means-tested transfers may be contributing to the household income of households at the bottom of the income distribution who do not have labor income. Consequently, the bottom quintile can have a higher share of total household income than household earnings.   

![](homework1_files/figure-latex/lorenz, total household income vs earnings-1.pdf)<!-- --> 


## Question 3: average share of total household income from earnings  
The average share of earnings in household income is 68.51%, indicating that households typically receive just over two-thirds of their income from labor income. This figure is excluding the 137 households with incomes of 0, as their share would be undefined. 

```
## [1] "Mean share of earnings in total household income: 68.51"
```


## Question 4: mean and share of labor earnings by quintile    
In the dataset, higher income households derive a larger share of their income from labor earnings. The most stark difference is between quintile 1 and 2: the mean share of labor is 46.6% in the former, and increases by 18.9 percentage points in quintile 2. The difference in the earnings share between the remaining quintiles is modest: between quintile 2 and 5, the total increase is less than that between quintile 1 and 2. 

  

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

When we separate the top 1% of households, we see that they get 77.1% of their income from labor earnings, higher than the overall mean. 

These shares are all higher than SCF (according to Section 1.2, Slide 11). The subset with the most dramatic different between PSID and SCF is the top 1%: in 2022, the SCF reported that 34.5% of household income in the top 1% came from labor, less than half of the PSID's estimate. The reason for this difference may be that SCF's wealthier sample relies more heavily on capital income, while PSID's sample captures a more representative breakdown of income sources. 

-------------------------------
   group      mean_labor_share 
------------ ------------------
 bottom 99%        68.4%       

   top 1%          77.1%       
-------------------------------

Table: Share of total household income from labor earnings, top 1%, PSID
  

## Question 5: weekly wage, contribution of hours and wages to labor earnings inequality  
In the dataset, there are 6,971 households where the household head has positive labor earnings and weeks of work. The mean weekly wage for these household heads is $1,117.74.  


```
## [1] "Positive weeks worked and labor earnings: 6971"
```

```
## [1] "Mean weekly wage of household head: 1117.74"
```

A variance decomposition shows that most earnings inequality arises from wage dispersion: the variance of log wages (0.87) is much larger than the variance of log weeks worked (0.17). The positive covariance indicates that individuals with higher wages also tend to work more weeks, further amplifying overall earnings inequality. These results suggest that differences in log wages contribute much more to log earnings inequality than differences in log weeks worked.

However, a caveat to this decomposition is that it assumes a covariance of zero when this is not the case. We cannot fully separate out the link between earnings and weeks worked vs weekly wages. Additionally, this analysis is restricted to household heads with positive weeks worked and positive labor earnings. By excluding those who did not work or earn, the approach may understate the role of weeks worked in earnings inequality, as those at the bottom of the earnings distribution could be working very few weeks or not at all due to limited employment opportunities. 


------------------------------------
        component            value  
-------------------------- ---------
      Var(log wage)         0.8741  

      Var(log weeks)        0.1674  

 Cov(log wage, log weeks)   0.07425 

    Var(log earnings)        1.19   
------------------------------------

Table: Labor earnings variance decomposition results



## Question 6: regression: log-weekly wages   
A linear regression of the log-transformed wage of the household head on the head's age, age-squared, education, and occupation provides further information about the drivers of wage inequality. The observables in this regression explain 44% of the variation in log-transformed wages, while the residuals (residual standard error = 0.7243, variance = 0.4883) explain 56%. 

```
## [1] "Share of inequality explained by observables: 0.44"
```

```
## [1] "Share of inequality explained by residuals: 0.56"
```


-----------------------------------------------------------------------
        &nbsp;           Estimate    Std. Error   t value    Pr(>|t|)  
---------------------- ------------ ------------ ---------- -----------
   **(Intercept)**         5.57        0.2915      19.11     3.309e-79 

     **AGE_HEAD**        0.08667      0.004385     19.77     1.706e-84 

   **AGE_HEAD_SQ**      -0.0009439   4.743e-05     -19.9     1.426e-85 

  **EDU_HEAD_CAT1**       0.9103       0.7634      1.192      0.2332   

  **EDU_HEAD_CAT2**      -0.5371       0.3407      -1.576      0.115   

  **EDU_HEAD_CAT3**      -0.4021       0.309       -1.301     0.1933   

  **EDU_HEAD_CAT4**        0.13        0.3316      0.3921      0.695   

  **EDU_HEAD_CAT5**      -0.00903      0.3792     -0.02381     0.981   

  **EDU_HEAD_CAT6**      -0.1086       0.2524     -0.4304     0.6669   

  **EDU_HEAD_CAT7**      -0.05192      0.2917      -0.178     0.8587   

  **EDU_HEAD_CAT8**      -0.2889       0.2648      -1.091     0.2753   

  **EDU_HEAD_CAT9**      -0.02506      0.2466     -0.1016     0.9191   

  **EDU_HEAD_CAT10**      -0.148       0.2409     -0.6144     0.5389   

  **EDU_HEAD_CAT11**     -0.1938       0.2372     -0.8172     0.4138   

  **EDU_HEAD_CAT12**     0.02601       0.2351      0.1107     0.9119   

  **EDU_HEAD_CAT13**     0.07139       0.2365      0.3019     0.7627   

  **EDU_HEAD_CAT14**      0.1365       0.2358      0.579      0.5626   

  **EDU_HEAD_CAT15**      0.0939       0.2381      0.3944     0.6933   

  **EDU_HEAD_CAT16**      0.3268       0.2362      1.384      0.1665   

  **EDU_HEAD_CAT17**      0.371        0.2369      1.566      0.1173   

  **OCC_HEAD_CAT20**     -0.07642      0.1869     -0.4089     0.6826   

  **OCC_HEAD_CAT30**      -1.457       0.5311      -2.743    0.006109  

  **OCC_HEAD_CAT40**     -0.0127       0.2593     -0.04897    0.9609   

  **OCC_HEAD_CAT50**      -0.121       0.1789     -0.6767     0.4986   

  **OCC_HEAD_CAT60**     0.02192       0.3272     0.06697     0.9466   

 **OCC_HEAD_CAT100**      -0.105       0.3075     -0.3416     0.7327   

 **OCC_HEAD_CAT110**     0.07053       0.1869      0.3774     0.7059   

 **OCC_HEAD_CAT120**     -0.01643      0.1779     -0.09233    0.9264   

 **OCC_HEAD_CAT136**     -0.3377       0.2515      -1.343     0.1794   

 **OCC_HEAD_CAT137**      0.8559       0.738        1.16      0.2462   

 **OCC_HEAD_CAT140**     -0.4616       0.2056      -2.245     0.02481  

 **OCC_HEAD_CAT150**     -0.4286       0.4409     -0.9721     0.3311   

 **OCC_HEAD_CAT160**     -0.2947       0.2208      -1.335      0.182   

 **OCC_HEAD_CAT205**     -0.4332       0.2337      -1.854     0.06385  

 **OCC_HEAD_CAT220**     -0.2318       0.1695      -1.367     0.1717   

 **OCC_HEAD_CAT230**     -0.7736       0.1924      -4.021    5.873e-05 

 **OCC_HEAD_CAT300**     -0.1214       0.2082      -0.583     0.5599   

 **OCC_HEAD_CAT310**     -0.5331       0.2111      -2.525     0.01159  

 **OCC_HEAD_CAT325**     -0.4435       0.4408      -1.006     0.3145   

 **OCC_HEAD_CAT340**      -1.125       0.3528      -3.189    0.001432  

 **OCC_HEAD_CAT350**     -0.4059       0.2245      -1.808     0.07059  

 **OCC_HEAD_CAT360**     -0.6892       0.5309      -1.298     0.1943   

 **OCC_HEAD_CAT400**     -0.7394       0.7384      -1.001     0.3167   

 **OCC_HEAD_CAT410**     -0.4439       0.1994      -2.226     0.02603  

 **OCC_HEAD_CAT420**     -0.8092       0.2592      -3.122    0.001802  

 **OCC_HEAD_CAT425**     -0.2802       0.7378     -0.3798     0.7041   

 **OCC_HEAD_CAT430**      -0.573       0.1567      -3.656    0.0002578 

 **OCC_HEAD_CAT500**     0.08418       0.738       0.1141     0.9092   

 **OCC_HEAD_CAT510**     -0.2021       0.5312     -0.3805     0.7036   

 **OCC_HEAD_CAT520**      -0.839       0.2686      -3.124    0.001792  

 **OCC_HEAD_CAT530**     -0.2025       0.2592     -0.7815     0.4345   

 **OCC_HEAD_CAT540**     -0.7085       0.2336      -3.034    0.002425  

 **OCC_HEAD_CAT565**     -0.4529       0.2243      -2.019     0.04349  

 **OCC_HEAD_CAT600**     -0.6734       0.3076      -2.189     0.02863  

 **OCC_HEAD_CAT630**     -0.6187       0.2515      -2.46      0.01393  

 **OCC_HEAD_CAT640**     -0.5007       0.3884      -1.289     0.1974   

 **OCC_HEAD_CAT650**     -0.2707       0.2333      -1.16       0.246   

 **OCC_HEAD_CAT700**     -0.7466       0.2919      -2.558     0.01056  

 **OCC_HEAD_CAT710**     -0.1549       0.1972     -0.7857     0.4321   

 **OCC_HEAD_CAT725**     -0.9012       0.3271      -2.755    0.005892  

 **OCC_HEAD_CAT726**      -1.03        0.4411      -2.336     0.01953  

 **OCC_HEAD_CAT735**     -0.5008       0.2141      -2.339     0.01938  

 **OCC_HEAD_CAT740**     -0.2902       0.2333      -1.244     0.2135   

 **OCC_HEAD_CAT800**     -0.5381       0.1737      -3.097    0.001963  

 **OCC_HEAD_CAT810**     -0.3904       0.2916      -1.339     0.1807   

 **OCC_HEAD_CAT820**     -0.5838       0.4409      -1.324     0.1855   

 **OCC_HEAD_CAT830**      -0.064       0.5308     -0.1206      0.904   

 **OCC_HEAD_CAT840**      0.1456       0.2247      0.6477     0.5172   

 **OCC_HEAD_CAT850**     0.05137       0.2171      0.2366      0.813   

 **OCC_HEAD_CAT860**     -0.3256       0.4411     -0.7381     0.4605   

 **OCC_HEAD_CAT910**     -0.3537       0.2059      -1.717     0.08597  

 **OCC_HEAD_CAT930**     -0.9789       0.7381      -1.326     0.1848   

 **OCC_HEAD_CAT940**     -0.7022       0.292       -2.405     0.0162   

 **OCC_HEAD_CAT950**      -1.086       0.531       -2.045     0.0409   

 **OCC_HEAD_CAT1005**    -0.1892       0.738      -0.2564     0.7976   

 **OCC_HEAD_CAT1006**    -0.3064       0.2387      -1.284     0.1993   

 **OCC_HEAD_CAT1007**    -0.1401       0.2683      -0.522     0.6017   

 **OCC_HEAD_CAT1010**    -0.2241       0.2137      -1.048     0.2945   

 **OCC_HEAD_CAT1020**    -0.1364       0.169      -0.8071     0.4197   

 **OCC_HEAD_CAT1030**    -0.4881       0.2684      -1.819     0.06902  

 **OCC_HEAD_CAT1050**    -0.5649       0.179       -3.156    0.001607  

 **OCC_HEAD_CAT1060**    -0.2999       0.2448      -1.225     0.2206   

 **OCC_HEAD_CAT1105**    -0.3974       0.2171      -1.831     0.06722  

 **OCC_HEAD_CAT1106**    -0.3595       0.3074      -1.169     0.2423   

 **OCC_HEAD_CAT1107**    -0.7487       0.3272      -2.288     0.02218  

 **OCC_HEAD_CAT1200**     0.2906       0.5311      0.5472     0.5843   

 **OCC_HEAD_CAT1220**    -0.6992       0.5311      -1.317      0.188   

 **OCC_HEAD_CAT1300**    -0.6996       0.3272      -2.138     0.03256  

 **OCC_HEAD_CAT1320**    -0.05466      0.327      -0.1672     0.8672   

 **OCC_HEAD_CAT1340**     -1.567       0.4411      -3.553    0.0003832 

 **OCC_HEAD_CAT1350**    -0.07021      0.3527     -0.1991     0.8422   

 **OCC_HEAD_CAT1360**    -0.1613       0.2446     -0.6596     0.5095   

 **OCC_HEAD_CAT1400**     0.1954       0.4409      0.4433     0.6576   

 **OCC_HEAD_CAT1410**    -0.1053       0.2245     -0.4692      0.639   

 **OCC_HEAD_CAT1420**    -0.1494       0.3527     -0.4237     0.6718   

 **OCC_HEAD_CAT1430**    -0.1424       0.3073     -0.4632     0.6432   

 **OCC_HEAD_CAT1440**    0.09549       0.7378      0.1294      0.897   

 **OCC_HEAD_CAT1450**    -0.5655       0.5311      -1.065     0.2871   

 **OCC_HEAD_CAT1460**     -0.11        0.2108     -0.5219     0.6017   

 **OCC_HEAD_CAT1500**    -0.3086       0.7379     -0.4182     0.6758   

 **OCC_HEAD_CAT1520**    -0.5361       0.4413      -1.215     0.2245   

 **OCC_HEAD_CAT1530**     0.3534       0.7382      0.4788     0.6321   

 **OCC_HEAD_CAT1540**    -0.4929       0.2923      -1.686     0.09185  

 **OCC_HEAD_CAT1550**    -0.6119       0.1941      -3.153    0.001625  

 **OCC_HEAD_CAT1560**    -0.8314       0.441       -1.885     0.05943  

 **OCC_HEAD_CAT1600**    -0.7522       0.7399      -1.017     0.3094   

 **OCC_HEAD_CAT1610**    -0.7483       0.2449      -3.056    0.002253  

 **OCC_HEAD_CAT1650**    -0.7081       0.4413      -1.605     0.1086   

 **OCC_HEAD_CAT1700**    -0.09414      0.3886     -0.2423     0.8086   

 **OCC_HEAD_CAT1710**     -1.458       0.7381      -1.976     0.04824  

 **OCC_HEAD_CAT1720**    -0.7938       0.327       -2.427     0.01524  

 **OCC_HEAD_CAT1740**     -1.042       0.279       -3.735    0.000189  

 **OCC_HEAD_CAT1760**    -0.6741       0.738      -0.9134     0.3611   

 **OCC_HEAD_CAT1800**    0.07684       0.5312      0.1447      0.885   

 **OCC_HEAD_CAT1815**    -0.4607       0.3883      -1.187     0.2354   

 **OCC_HEAD_CAT1820**     -1.024       0.3077      -3.326    0.0008864 

 **OCC_HEAD_CAT1840**    -0.7697       0.4409      -1.746     0.08092  

 **OCC_HEAD_CAT1860**     -1.171       0.3884      -3.016    0.002571  

 **OCC_HEAD_CAT1900**    -0.3691       0.5334     -0.6919      0.489   

 **OCC_HEAD_CAT1920**    -0.5888       0.3886      -1.515     0.1297   

 **OCC_HEAD_CAT1930**     -0.235       0.5313     -0.4423     0.6583   

 **OCC_HEAD_CAT1950**    -0.2927       0.738      -0.3967     0.6916   

 **OCC_HEAD_CAT1965**    -0.7116       0.3075      -2.314     0.02068  

 **OCC_HEAD_CAT2000**     -1.059       0.1758      -6.025    1.781e-09 

 **OCC_HEAD_CAT2010**    -0.9793       0.1909      -5.131    2.969e-07 

 **OCC_HEAD_CAT2015**    -0.8714       0.3885      -2.243     0.02493  

 **OCC_HEAD_CAT2016**     -1.215       0.2686      -4.522    6.241e-06 

 **OCC_HEAD_CAT2025**     -1.157       0.2082      -5.557    2.846e-08 

 **OCC_HEAD_CAT2040**     -1.265       0.2081      -6.08     1.268e-09 

 **OCC_HEAD_CAT2050**    -0.7994       0.531       -1.505     0.1323   

 **OCC_HEAD_CAT2100**    -0.01861      0.1862     -0.09994    0.9204   

 **OCC_HEAD_CAT2105**     -1.059       0.7381      -1.434     0.1516   

 **OCC_HEAD_CAT2110**    -0.06135      0.3274     -0.1874     0.8513   

 **OCC_HEAD_CAT2145**    -0.6873       0.279       -2.464     0.01377  

 **OCC_HEAD_CAT2160**    -0.7087       0.3883      -1.825     0.06799  

 **OCC_HEAD_CAT2200**    -0.8297        0.18       -4.61     4.107e-06 

 **OCC_HEAD_CAT2300**     -1.398       0.221       -6.326    2.676e-10 

 **OCC_HEAD_CAT2310**     -1.116       0.1629      -6.851    8.024e-12 

 **OCC_HEAD_CAT2320**     -0.867       0.1693      -5.123    3.097e-07 

 **OCC_HEAD_CAT2330**    -0.9993       0.2516      -3.972    7.211e-05 

 **OCC_HEAD_CAT2340**     -1.689       0.2293      -7.367    1.96e-13  

 **OCC_HEAD_CAT2400**    -0.7589       0.5314      -1.428     0.1533   

 **OCC_HEAD_CAT2430**     -0.982       0.3076      -3.192    0.001419  

 **OCC_HEAD_CAT2440**    -0.9972       0.738       -1.351     0.1767   

 **OCC_HEAD_CAT2540**     -1.446       0.1825      -7.92     2.764e-15 

 **OCC_HEAD_CAT2550**    -0.8743       0.2387      -3.663    0.0002516 

 **OCC_HEAD_CAT2600**     -2.669       0.2521      -10.59    5.526e-26 

 **OCC_HEAD_CAT2630**    -0.8489       0.1974       -4.3     1.729e-05 

 **OCC_HEAD_CAT2700**    -0.7866       0.389       -2.022     0.04321  

 **OCC_HEAD_CAT2710**    -0.4807       0.3076      -1.562     0.1182   

 **OCC_HEAD_CAT2720**     -1.467       0.2205      -6.652    3.134e-11 

 **OCC_HEAD_CAT2740**     -1.94        0.7384      -2.627    0.008628  

 **OCC_HEAD_CAT2750**     -1.623       0.2209      -7.349    2.242e-13 

 **OCC_HEAD_CAT2760**     -1.82        0.3885      -4.685    2.856e-06 

 **OCC_HEAD_CAT2800**     -1.425       0.4414      -3.228    0.001251  

 **OCC_HEAD_CAT2810**   -0.005063      0.4409     -0.01148    0.9908   

 **OCC_HEAD_CAT2825**    -0.5049       0.3532      -1.43      0.1529   

 **OCC_HEAD_CAT2830**     -1.026       0.3271      -3.135    0.001723  

 **OCC_HEAD_CAT2840**    -0.6048       0.3528      -1.714     0.08652  

 **OCC_HEAD_CAT2850**    -0.8386       0.2916      -2.876    0.004047  

 **OCC_HEAD_CAT2860**     -1.166       0.5311      -2.195     0.02818  

 **OCC_HEAD_CAT2900**    -0.4972       0.3527      -1.41      0.1587   

 **OCC_HEAD_CAT2910**     -0.647       0.3273      -1.977     0.0481   

 **OCC_HEAD_CAT2920**     -1.021       0.3277      -3.114    0.001853  

 **OCC_HEAD_CAT2960**     -1.045       0.7381      -1.416     0.1569   

 **OCC_HEAD_CAT3000**     -1.016       0.5309      -1.915     0.05558  

 **OCC_HEAD_CAT3010**     0.2784       0.3079      0.9043     0.3659   

 **OCC_HEAD_CAT3030**     -1.238       0.738       -1.678     0.09346  

 **OCC_HEAD_CAT3050**     0.0657       0.2796      0.235      0.8142   

 **OCC_HEAD_CAT3060**    0.09229       0.1873      0.4927     0.6223   

 **OCC_HEAD_CAT3110**    -0.6136       0.4411      -1.391     0.1643   

 **OCC_HEAD_CAT3150**    -0.3296       0.531      -0.6208     0.5348   

 **OCC_HEAD_CAT3160**    -0.4318       0.3887      -1.111     0.2667   

 **OCC_HEAD_CAT3220**    -0.7307       0.5313      -1.375     0.1691   

 **OCC_HEAD_CAT3230**    -0.7748       0.441       -1.757     0.07894  

 **OCC_HEAD_CAT3245**     -1.58        0.5314      -2.973    0.002959  

 **OCC_HEAD_CAT3250**     0.2142       0.5312      0.4032     0.6868   

 **OCC_HEAD_CAT3255**    -0.4977       0.1676      -2.97     0.002989  

 **OCC_HEAD_CAT3257**    -0.6697       0.7381     -0.9073     0.3643   

 **OCC_HEAD_CAT3258**    -0.5607       0.292       -1.92      0.05487  

 **OCC_HEAD_CAT3260**    -0.9934       0.5312      -1.87      0.06153  

 **OCC_HEAD_CAT3300**     -1.11        0.2334      -4.754    2.036e-06 

 **OCC_HEAD_CAT3310**     -1.071       0.4417      -2.425     0.01533  

 **OCC_HEAD_CAT3320**    -0.7051       0.2918      -2.417     0.01569  

 **OCC_HEAD_CAT3400**    -0.7703       0.2685      -2.869    0.004135  

 **OCC_HEAD_CAT3420**     -1.135       0.245       -4.63     3.729e-06 

 **OCC_HEAD_CAT3500**    -0.9196        0.2        -4.598    4.347e-06 

 **OCC_HEAD_CAT3510**     -0.898       0.3076      -2.92     0.003516  

 **OCC_HEAD_CAT3520**     -1.265       0.5312      -2.382     0.01726  

 **OCC_HEAD_CAT3535**     -1.007       0.2793      -3.606    0.0003137 

 **OCC_HEAD_CAT3540**    -0.6553       0.3882      -1.688     0.09149  

 **OCC_HEAD_CAT3600**     -1.324       0.1533      -8.637    7.207e-18 

 **OCC_HEAD_CAT3610**    -0.5423       0.7381     -0.7348     0.4625   

 **OCC_HEAD_CAT3620**    -0.9643       0.3533      -2.73      0.00636  

 **OCC_HEAD_CAT3630**     -1.654       0.3888      -4.254    2.126e-05 

 **OCC_HEAD_CAT3640**     -1.021       0.3538      -2.887    0.003897  

 **OCC_HEAD_CAT3645**     -1.075       0.2293      -4.691    2.777e-06 

 **OCC_HEAD_CAT3646**    -0.2737       0.7378      -0.371     0.7106   

 **OCC_HEAD_CAT3647**     -1.308       0.5315      -2.461     0.01386  

 **OCC_HEAD_CAT3649**    -0.8238       0.3882      -2.122     0.03388  

 **OCC_HEAD_CAT3655**     -1.066        0.26       -4.102    4.142e-05 

 **OCC_HEAD_CAT3700**    -0.4956       0.4414      -1.123     0.2616   

 **OCC_HEAD_CAT3710**    -0.2984       0.2333      -1.279      0.201   

 **OCC_HEAD_CAT3720**    -0.08934      0.2792     -0.3201     0.7489   

 **OCC_HEAD_CAT3730**    -0.7268       0.2449      -2.967    0.003015  

 **OCC_HEAD_CAT3740**    -0.3663       0.234       -1.565     0.1175   

 **OCC_HEAD_CAT3800**    -0.5777       0.196       -2.948     0.00321  

 **OCC_HEAD_CAT3820**    -0.2742       0.2387      -1.149     0.2508   

 **OCC_HEAD_CAT3840**     -1.022       0.5315      -1.922     0.05464  

 **OCC_HEAD_CAT3850**    -0.4686       0.1763      -2.658    0.007881  

 **OCC_HEAD_CAT3860**    -0.5708       0.7384      -0.773     0.4395   

 **OCC_HEAD_CAT3910**    -0.6769       0.3272      -2.069     0.03858  

 **OCC_HEAD_CAT3930**     -1.19        0.1666      -7.145    1.001e-12 

 **OCC_HEAD_CAT3940**     -3.16        0.738       -4.282    1.875e-05 

 **OCC_HEAD_CAT3945**    -0.4242       0.7391      -0.574      0.566   

 **OCC_HEAD_CAT3955**    -0.5696       0.4416      -1.29      0.1972   

 **OCC_HEAD_CAT4000**     -1.01        0.2177      -4.641    3.544e-06 

 **OCC_HEAD_CAT4010**     -1.142       0.1588      -7.191    7.139e-13 

 **OCC_HEAD_CAT4020**     -1.529       0.1625      -9.412    6.612e-21 

 **OCC_HEAD_CAT4030**     -1.397       0.1918      -7.287    3.536e-13 

 **OCC_HEAD_CAT4040**     -1.308       0.2342      -5.584    2.447e-08 

 **OCC_HEAD_CAT4050**     -1.625       0.172       -9.447    4.754e-21 

 **OCC_HEAD_CAT4060**     -1.85        0.2405      -7.693    1.651e-14 

 **OCC_HEAD_CAT4110**     -1.168       0.1782      -6.554    6.019e-11 

 **OCC_HEAD_CAT4120**     -1.024       0.7386      -1.386     0.1657   

 **OCC_HEAD_CAT4130**    -0.9188       0.3534       -2.6      0.00935  

 **OCC_HEAD_CAT4140**     -1.485       0.2458      -6.042    1.604e-09 

 **OCC_HEAD_CAT4150**     -1.499       0.3891      -3.851    0.0001186 

 **OCC_HEAD_CAT4160**     -1.336       0.5322      -2.51      0.01209  

 **OCC_HEAD_CAT4200**    -0.9276       0.1757      -5.279    1.338e-07 

 **OCC_HEAD_CAT4210**    -0.9241       0.1998      -4.624    3.832e-06 

 **OCC_HEAD_CAT4220**     -1.346       0.156       -8.631    7.555e-18 

 **OCC_HEAD_CAT4230**     -1.779       0.1667      -10.68    2.171e-26 

 **OCC_HEAD_CAT4240**     -0.615       0.5352      -1.149     0.2505   

 **OCC_HEAD_CAT4250**     -1.787       0.1603      -11.15    1.336e-28 

 **OCC_HEAD_CAT4320**    -0.6196       0.239       -2.593    0.009533  

 **OCC_HEAD_CAT4350**     -1.82        0.2684      -6.779    1.317e-11 

 **OCC_HEAD_CAT4400**    -0.9847       0.4412      -2.232     0.02564  

 **OCC_HEAD_CAT4420**     -3.684        0.74       -4.979    6.558e-07 

 **OCC_HEAD_CAT4430**     -1.38        0.4417      -3.125    0.001788  

 **OCC_HEAD_CAT4460**     -2.079       0.5315      -3.911    9.271e-05 

 **OCC_HEAD_CAT4465**    -0.9334       0.4409      -2.117     0.03429  

 **OCC_HEAD_CAT4500**     -1.377       0.2297      -5.995    2.14e-09  

 **OCC_HEAD_CAT4510**     -1.655       0.1861      -8.897    7.332e-19 

 **OCC_HEAD_CAT4520**     -1.474       0.3274      -4.501    6.874e-06 

 **OCC_HEAD_CAT4530**     -1.307       0.5315      -2.459     0.01396  

 **OCC_HEAD_CAT4540**     -1.282       0.3882      -3.303    0.0009601 

 **OCC_HEAD_CAT4600**     -2.085       0.1651      -12.63    3.685e-36 

 **OCC_HEAD_CAT4610**     -1.599       0.1651      -9.684    4.966e-22 

 **OCC_HEAD_CAT4620**     -1.419       0.2918      -4.862    1.188e-06 

 **OCC_HEAD_CAT4640**    -0.8281       0.5311      -1.559      0.119   

 **OCC_HEAD_CAT4650**     -1.602       0.3886      -4.123    3.782e-05 

 **OCC_HEAD_CAT4700**    -0.7333       0.1551      -4.729    2.306e-06 

 **OCC_HEAD_CAT4710**    0.01683       0.1857      0.0906     0.9278   

 **OCC_HEAD_CAT4720**     -1.62        0.1641      -9.873    7.916e-23 

 **OCC_HEAD_CAT4740**    -0.6522       0.3532      -1.847     0.06485  

 **OCC_HEAD_CAT4750**    -0.7527       0.308       -2.444     0.01456  

 **OCC_HEAD_CAT4760**     -1.026       0.1577      -6.507    8.26e-11  

 **OCC_HEAD_CAT4800**    -0.6471       0.292       -2.216     0.02673  

 **OCC_HEAD_CAT4810**    -0.4802       0.1909      -2.516     0.0119   

 **OCC_HEAD_CAT4820**     0.2689       0.2919      0.9211      0.357   

 **OCC_HEAD_CAT4830**     -1.141       0.4413      -2.586     0.00974  

 **OCC_HEAD_CAT4840**    -0.5371       0.1885      -2.849    0.004394  

 **OCC_HEAD_CAT4850**    -0.3647       0.1715      -2.127     0.03345  

 **OCC_HEAD_CAT4900**     -1.588       0.2918      -5.443    5.423e-08 

 **OCC_HEAD_CAT4920**    -0.8009       0.1994      -4.017    5.953e-05 

 **OCC_HEAD_CAT4930**    -0.1093       0.531      -0.2059     0.8369   

 **OCC_HEAD_CAT4940**    -0.5353       0.3532      -1.515     0.1297   

 **OCC_HEAD_CAT4950**     -1.424       0.2699      -5.275    1.371e-07 

 **OCC_HEAD_CAT4965**     -1.517       0.246       -6.165    7.461e-10 

 **OCC_HEAD_CAT5000**     -0.701       0.1579      -4.44     9.15e-06  

 **OCC_HEAD_CAT5010**     -1.281       0.531       -2.413     0.01584  

 **OCC_HEAD_CAT5100**     -1.027       0.3076      -3.339    0.0008441 

 **OCC_HEAD_CAT5110**     -1.027       0.2207      -4.653    3.336e-06 

 **OCC_HEAD_CAT5120**    -0.9336       0.1884      -4.956    7.396e-07 

 **OCC_HEAD_CAT5130**     -1.194       0.7383      -1.617     0.1059   

 **OCC_HEAD_CAT5140**    -0.9471       0.3272      -2.895     0.00381  

 **OCC_HEAD_CAT5150**     -0.873       0.4415      -1.977     0.04803  

 **OCC_HEAD_CAT5160**    -0.9351       0.2522      -3.708    0.0002103 

 **OCC_HEAD_CAT5165**    -0.8093       0.4411      -1.835     0.06662  

 **OCC_HEAD_CAT5200**    -0.6619       0.4412       -1.5      0.1336   

 **OCC_HEAD_CAT5220**    -0.5421       0.3276      -1.655     0.09802  

 **OCC_HEAD_CAT5230**     -1.374       0.3887      -3.535    0.0004111 

 **OCC_HEAD_CAT5240**     -1.033       0.1612      -6.406    1.595e-10 

 **OCC_HEAD_CAT5260**    -0.9706       0.3534      -2.747    0.006039  

 **OCC_HEAD_CAT5300**     -1.759       0.2599      -6.768    1.416e-11 

 **OCC_HEAD_CAT5310**     -1.519       0.3077      -4.935    8.202e-07 

 **OCC_HEAD_CAT5320**     -1.266       0.3077      -4.115    3.913e-05 

 **OCC_HEAD_CAT5330**    -0.7769       0.3076      -2.526     0.01156  

 **OCC_HEAD_CAT5340**    -0.7652       0.3272      -2.338     0.0194   

 **OCC_HEAD_CAT5350**    -0.3792       0.738      -0.5138     0.6074   

 **OCC_HEAD_CAT5360**    -0.7572       0.3882      -1.95      0.05119  

 **OCC_HEAD_CAT5400**     -1.482       0.2021      -7.331    2.559e-13 

 **OCC_HEAD_CAT5410**    -0.8822       0.3533      -2.497     0.01255  

 **OCC_HEAD_CAT5420**     -1.823       0.2921      -6.242    4.586e-10 

 **OCC_HEAD_CAT5500**    -0.9099       0.5314      -1.712     0.08689  

 **OCC_HEAD_CAT5510**     -1.26        0.1844      -6.834    9.008e-12 

 **OCC_HEAD_CAT5520**    -0.7945       0.2213      -3.591    0.0003319 

 **OCC_HEAD_CAT5530**    -0.9529       0.7379      -1.291     0.1966   

 **OCC_HEAD_CAT5540**    -0.5565       0.3275      -1.699     0.0893   

 **OCC_HEAD_CAT5550**    -0.6211       0.2019      -3.077    0.002103  

 **OCC_HEAD_CAT5560**    -0.3728       0.3887      -0.959     0.3376   

 **OCC_HEAD_CAT5600**    -0.8252       0.2517      -3.279    0.001047  

 **OCC_HEAD_CAT5610**     -1.029       0.1999      -5.147    2.727e-07 

 **OCC_HEAD_CAT5620**     -1.207       0.1597      -7.557    4.685e-14 

 **OCC_HEAD_CAT5630**    -0.5669       0.531       -1.068     0.2857   

 **OCC_HEAD_CAT5700**     -1.133       0.1654      -6.852    7.943e-12 

 **OCC_HEAD_CAT5810**     -1.084       0.2685      -4.036    5.488e-05 

 **OCC_HEAD_CAT5820**     -2.257       0.7378      -3.06     0.002225  

 **OCC_HEAD_CAT5840**     -1.019       0.2252      -4.523    6.212e-06 

 **OCC_HEAD_CAT5850**    -0.8806       0.3535      -2.491     0.01275  

 **OCC_HEAD_CAT5860**     -1.163       0.2211      -5.262    1.474e-07 

 **OCC_HEAD_CAT5910**     -1.555       0.5315      -2.927     0.00344  

 **OCC_HEAD_CAT5940**     -1.477       0.2685      -5.501    3.916e-08 

 **OCC_HEAD_CAT6005**    -0.7686       0.2399      -3.204    0.001363  

 **OCC_HEAD_CAT6010**    -0.1172       0.738      -0.1588     0.8738   

 **OCC_HEAD_CAT6020**     -1.496       0.7385      -2.026     0.04286  

 **OCC_HEAD_CAT6050**     -1.383       0.1915      -7.222    5.725e-13 

 **OCC_HEAD_CAT6100**      0.13        0.389       0.3341     0.7383   

 **OCC_HEAD_CAT6130**      -1.1        0.328       -3.353    0.0008027 

 **OCC_HEAD_CAT6200**    -0.3795       0.1594      -2.381     0.01729  

 **OCC_HEAD_CAT6220**     -1.312       0.3305      -3.97     7.257e-05 

 **OCC_HEAD_CAT6230**    -0.8731       0.1731      -5.043    4.704e-07 

 **OCC_HEAD_CAT6240**     -1.175       0.2343      -5.014    5.483e-07 

 **OCC_HEAD_CAT6250**    -0.9537       0.2824      -3.377    0.0007369 

 **OCC_HEAD_CAT6260**    -0.9973        0.16       -6.234    4.845e-10 

 **OCC_HEAD_CAT6300**    -0.9767       0.5332      -1.832     0.06701  

 **OCC_HEAD_CAT6310**    -0.2594       0.738      -0.3515     0.7253   

 **OCC_HEAD_CAT6320**     -0.564       0.2118      -2.663    0.007762  

 **OCC_HEAD_CAT6330**     -1.943       0.3333      -5.83     5.794e-09 

 **OCC_HEAD_CAT6355**    -0.5933       0.1902      -3.119    0.001821  

 **OCC_HEAD_CAT6360**    -0.4837       0.5314     -0.9102     0.3627   

 **OCC_HEAD_CAT6400**    -0.6649        0.33       -2.015     0.04396  

 **OCC_HEAD_CAT6420**     -1.245       0.1953      -6.378    1.922e-10 

 **OCC_HEAD_CAT6430**    -0.6886       0.7388      -0.932     0.3513   

 **OCC_HEAD_CAT6440**     -0.508       0.1933      -2.628    0.008596  

 **OCC_HEAD_CAT6460**    -0.9317       0.738       -1.262     0.2068   

 **OCC_HEAD_CAT6500**    -0.3352       0.738      -0.4542     0.6497   

 **OCC_HEAD_CAT6515**     -1.135       0.2613      -4.345    1.416e-05 

 **OCC_HEAD_CAT6520**    -0.4164       0.3888      -1.071     0.2843   

 **OCC_HEAD_CAT6530**    -0.5942       0.7387     -0.8044     0.4212   

 **OCC_HEAD_CAT6540**    -0.7754       0.5315      -1.459     0.1446   

 **OCC_HEAD_CAT6600**     -1.078       0.4427      -2.436     0.01489  

 **OCC_HEAD_CAT6660**    -0.4965       0.3533      -1.405      0.16    

 **OCC_HEAD_CAT6700**     0.3946       0.5324      0.7412     0.4586   

 **OCC_HEAD_CAT6710**    -0.3046       0.4421     -0.6889     0.4909   

 **OCC_HEAD_CAT6730**    -0.9334       0.2687      -3.473    0.0005175 

 **OCC_HEAD_CAT6740**    -0.4214        0.74      -0.5695      0.569   

 **OCC_HEAD_CAT6750**    -0.5845       0.5329      -1.097     0.2728   

 **OCC_HEAD_CAT6765**    -0.8098       0.5318      -1.523     0.1279   

 **OCC_HEAD_CAT6800**    -0.5114       0.7381     -0.6929     0.4884   

 **OCC_HEAD_CAT6820**     -2.537       0.4413      -5.75     9.337e-09 

 **OCC_HEAD_CAT6830**    -0.5208       0.7384     -0.7053     0.4806   

 **OCC_HEAD_CAT6840**    -0.3294       0.738      -0.4463     0.6554   

 **OCC_HEAD_CAT6920**     0.2002       0.7382      0.2712     0.7863   

 **OCC_HEAD_CAT6940**     0.1903       0.5314      0.3582     0.7202   

 **OCC_HEAD_CAT7000**    -0.5154       0.1822      -2.829    0.004678  

 **OCC_HEAD_CAT7010**     -1.49        0.2595      -5.742    9.775e-09 

 **OCC_HEAD_CAT7020**    -0.6527       0.2518      -2.593    0.009548  

 **OCC_HEAD_CAT7030**     -0.52        0.738      -0.7046     0.4811   

 **OCC_HEAD_CAT7040**    -0.5654       0.7384     -0.7657     0.4439   

 **OCC_HEAD_CAT7050**    -0.2772       0.738      -0.3755     0.7073   

 **OCC_HEAD_CAT7100**    -0.3327       0.3533     -0.9418     0.3463   

 **OCC_HEAD_CAT7110**    -0.5533       0.4415      -1.253     0.2102   

 **OCC_HEAD_CAT7120**     -1.452       0.7384      -1.967     0.04926  

 **OCC_HEAD_CAT7130**    -0.8145       0.4413      -1.845     0.06502  

 **OCC_HEAD_CAT7140**    -0.4914       0.2685      -1.83      0.06734  

 **OCC_HEAD_CAT7150**     -0.375       0.2797      -1.341      0.18    

 **OCC_HEAD_CAT7200**    -0.9077       0.1716      -5.289    1.27e-07  

 **OCC_HEAD_CAT7210**     -0.774       0.2253      -3.436    0.000594  

 **OCC_HEAD_CAT7220**    -0.5897       0.2117      -2.785    0.005367  

 **OCC_HEAD_CAT7240**     -1.156       0.738       -1.567     0.1172   

 **OCC_HEAD_CAT7260**     -0.967       0.3078      -3.141    0.001691  

 **OCC_HEAD_CAT7300**     -1.002       0.5311      -1.886     0.05939  

 **OCC_HEAD_CAT7315**    -0.5031       0.2148      -2.342     0.01923  

 **OCC_HEAD_CAT7320**     -0.709       0.4413      -1.606     0.1082   

 **OCC_HEAD_CAT7330**    -0.6973       0.2145      -3.251    0.001156  

 **OCC_HEAD_CAT7340**    -0.8377       0.2395      -3.497    0.0004731 

 **OCC_HEAD_CAT7350**    -0.6009       0.3276      -1.834     0.06669  

 **OCC_HEAD_CAT7410**    -0.4631       0.3079      -1.504     0.1326   

 **OCC_HEAD_CAT7420**    -0.4222       0.2454      -1.721     0.08536  

 **OCC_HEAD_CAT7430**    -0.1191       0.5311     -0.2243     0.8225   

 **OCC_HEAD_CAT7440**    -0.1299       0.7388     -0.1759     0.8604   

 **OCC_HEAD_CAT7510**     -1.034       0.4414      -2.342     0.01923  

 **OCC_HEAD_CAT7540**    -0.8786       0.5311      -1.654     0.09811  

 **OCC_HEAD_CAT7550**     -1.007       0.7388      -1.364     0.1728   

 **OCC_HEAD_CAT7560**     -1.027       0.7381      -1.391     0.1643   

 **OCC_HEAD_CAT7610**    -0.4685       0.4417      -1.061     0.2888   

 **OCC_HEAD_CAT7630**    -0.8645       0.3531      -2.448     0.01439  

 **OCC_HEAD_CAT7700**    -0.5672       0.1608      -3.527    0.0004231 

 **OCC_HEAD_CAT7710**    -0.5478       0.5316      -1.03      0.3029   

 **OCC_HEAD_CAT7720**     -1.092       0.2599      -4.201    2.695e-05 

 **OCC_HEAD_CAT7730**    -0.4881       0.3081      -1.584     0.1132   

 **OCC_HEAD_CAT7740**    -0.8063       0.4424      -1.822     0.06844  

 **OCC_HEAD_CAT7750**     -1.044       0.1725      -6.053    1.503e-09 

 **OCC_HEAD_CAT7800**     -1.585       0.3297      -4.807    1.563e-06 

 **OCC_HEAD_CAT7810**     -1.01        0.2107      -4.795    1.663e-06 

 **OCC_HEAD_CAT7840**    -0.9548       0.3093      -3.087    0.002028  

 **OCC_HEAD_CAT7850**     -1.417       0.5319      -2.665    0.007726  

 **OCC_HEAD_CAT7855**     -1.135       0.2924      -3.881    0.0001052 

 **OCC_HEAD_CAT7900**    -0.4594       0.2522      -1.822     0.06851  

 **OCC_HEAD_CAT7920**    -0.1363       0.5312     -0.2566     0.7975   

 **OCC_HEAD_CAT7930**    -0.3591       0.5314     -0.6758     0.4992   

 **OCC_HEAD_CAT7950**    -0.7667       0.3276      -2.341     0.01928  

 **OCC_HEAD_CAT8000**     -1.027       0.3079      -3.337    0.0008526 

 **OCC_HEAD_CAT8010**     -1.052       0.3532      -2.979    0.002902  

 **OCC_HEAD_CAT8030**    -0.5823       0.252       -2.311     0.02086  

 **OCC_HEAD_CAT8040**    -0.5201       0.4415      -1.178     0.2388   

 **OCC_HEAD_CAT8100**    -0.5299       0.3278      -1.616      0.106   

 **OCC_HEAD_CAT8120**    -0.3762       0.7386     -0.5093     0.6106   

 **OCC_HEAD_CAT8130**     -0.723       0.5314      -1.361     0.1737   

 **OCC_HEAD_CAT8140**    -0.6587       0.1845      -3.57     0.0003593 

 **OCC_HEAD_CAT8200**     -1.121       0.4418      -2.538     0.01119  

 **OCC_HEAD_CAT8210**    -0.2204       0.5342     -0.4126     0.6799   

 **OCC_HEAD_CAT8220**    -0.7656       0.2342      -3.269    0.001086  

 **OCC_HEAD_CAT8255**     -1.152       0.328       -3.512    0.0004481 

 **OCC_HEAD_CAT8300**     -1.294       0.2693      -4.807    1.566e-06 

 **OCC_HEAD_CAT8310**    -0.6589       0.7401     -0.8902     0.3734   

 **OCC_HEAD_CAT8320**     -1.026       0.2925      -3.506    0.0004574 

 **OCC_HEAD_CAT8350**     -1.457       0.5315      -2.741    0.006148  

 **OCC_HEAD_CAT8360**    -0.9967       0.5408      -1.843     0.06535  

 **OCC_HEAD_CAT8410**     -1.172       0.4415      -2.654    0.007978  

 **OCC_HEAD_CAT8420**    -0.8605       0.7381      -1.166     0.2437   

 **OCC_HEAD_CAT8430**     -1.018       0.532       -1.914     0.05565  

 **OCC_HEAD_CAT8440**    -0.9722       0.744       -1.307     0.1913   

 **OCC_HEAD_CAT8450**    -0.5443       0.3897      -1.397     0.1626   

 **OCC_HEAD_CAT8500**    -0.7227       0.3532      -2.046     0.0408   

 **OCC_HEAD_CAT8520**    -0.1298       0.7378     -0.1759     0.8604   

 **OCC_HEAD_CAT8530**     -1.105       0.3913      -2.823    0.004778  

 **OCC_HEAD_CAT8540**    -0.6584       0.389       -1.692     0.09064  

 **OCC_HEAD_CAT8550**     -1.204       0.738       -1.631     0.1029   

 **OCC_HEAD_CAT8600**    0.09393       0.5316      0.1767     0.8597   

 **OCC_HEAD_CAT8610**    -0.2442       0.7381     -0.3308     0.7408   

 **OCC_HEAD_CAT8620**    -0.5935       0.2921      -2.032     0.04223  

 **OCC_HEAD_CAT8630**    -0.6653       0.7378     -0.9018     0.3672   

 **OCC_HEAD_CAT8640**    -0.05712      0.3535     -0.1616     0.8716   

 **OCC_HEAD_CAT8650**    -0.7846       0.2522      -3.111    0.001872  

 **OCC_HEAD_CAT8710**     -1.172       0.3578      -3.275    0.001062  

 **OCC_HEAD_CAT8720**    -0.6421       0.3534      -1.817     0.06923  

 **OCC_HEAD_CAT8730**    -0.4185       0.5314     -0.7877     0.4309   

 **OCC_HEAD_CAT8740**     -0.701       0.1812      -3.868    0.0001108 

 **OCC_HEAD_CAT8760**    -0.5435       0.7385     -0.7359     0.4618   

 **OCC_HEAD_CAT8800**     -1.155       0.2019      -5.722     1.1e-08  

 **OCC_HEAD_CAT8810**    -0.9967       0.2692      -3.703    0.0002148 

 **OCC_HEAD_CAT8830**     -1.15        0.5314      -2.163     0.03055  

 **OCC_HEAD_CAT8860**    -0.5068       0.5336     -0.9497     0.3423   

 **OCC_HEAD_CAT8920**     -1.189       0.4412      -2.695    0.007057  

 **OCC_HEAD_CAT8940**    -0.3897       0.5312     -0.7337     0.4632   

 **OCC_HEAD_CAT8950**    -0.8867       0.4415      -2.009     0.04462  

 **OCC_HEAD_CAT8965**    -0.8513       0.1906      -4.466    8.117e-06 

 **OCC_HEAD_CAT9000**     -0.781       0.1717      -4.549    5.494e-06 

 **OCC_HEAD_CAT9030**    -0.03004      0.2592     -0.1159     0.9077   

 **OCC_HEAD_CAT9040**     0.1098       0.4413      0.2488     0.8036   

 **OCC_HEAD_CAT9050**    -0.8158       0.5309      -1.537     0.1245   

 **OCC_HEAD_CAT9110**    -0.4231       0.5312     -0.7965     0.4258   

 **OCC_HEAD_CAT9120**     -0.992       0.1786      -5.553    2.919e-08 

 **OCC_HEAD_CAT9130**    -0.6918       0.1478      -4.68     2.933e-06 

 **OCC_HEAD_CAT9140**     -1.289       0.1724      -7.48     8.401e-14 

 **OCC_HEAD_CAT9150**     -1.135       0.3281      -3.46     0.0005436 

 **OCC_HEAD_CAT9200**    0.03541       0.4414     0.08021     0.9361   

 **OCC_HEAD_CAT9230**    0.02376       0.7381     0.03219     0.9743   

 **OCC_HEAD_CAT9240**    -0.6261       0.3889      -1.61      0.1075   

 **OCC_HEAD_CAT9260**    -0.4724       0.531      -0.8896     0.3737   

 **OCC_HEAD_CAT9310**     -4.973       0.7381      -6.738    1.748e-11 

 **OCC_HEAD_CAT9350**     -1.878       0.3277      -5.732    1.038e-08 

 **OCC_HEAD_CAT9360**     -1.732       0.2797      -6.193    6.245e-10 

 **OCC_HEAD_CAT9410**    -0.6822       0.3884      -1.757     0.07905  

 **OCC_HEAD_CAT9420**    -0.4126       0.7388     -0.5585     0.5765   

 **OCC_HEAD_CAT9500**    -0.2593       0.5313     -0.4881     0.6255   

 **OCC_HEAD_CAT9510**    -0.5231       0.3275      -1.597     0.1102   

 **OCC_HEAD_CAT9520**    -0.9587       0.7382      -1.299     0.1941   

 **OCC_HEAD_CAT9600**    -0.7225       0.1585      -4.557    5.274e-06 

 **OCC_HEAD_CAT9610**     -1.422       0.212       -6.707    2.15e-11  

 **OCC_HEAD_CAT9620**     -1.182       0.1593      -7.42     1.316e-13 

 **OCC_HEAD_CAT9630**    -0.7199       0.5313      -1.355     0.1755   

 **OCC_HEAD_CAT9640**     -1.158       0.1972      -5.875    4.436e-09 

 **OCC_HEAD_CAT9720**     -1.074       0.3537      -3.037    0.002399  

 **OCC_HEAD_CAT9740**     0.2408       0.7381      0.3263     0.7442   

 **OCC_HEAD_CAT9750**    -0.8879       0.5314      -1.671     0.0948   

 **OCC_HEAD_CAT9800**    -0.2023       0.2171     -0.9322     0.3513   

 **OCC_HEAD_CAT9810**    -0.6493       0.1861      -3.489    0.0004881 

 **OCC_HEAD_CAT9820**    -0.6497       0.2921      -2.224     0.02618  

 **OCC_HEAD_CAT9830**    -0.6934       0.225       -3.082    0.002063  
-----------------------------------------------------------------------


--------------------------------------------------------------
 Observations   Residual Std. Error   $R^2$    Adjusted $R^2$ 
-------------- --------------------- -------- ----------------
     6971             0.7243          0.4413       0.3998     
--------------------------------------------------------------

Table: Log wages regression results


 
