Exploratory Data Analysis of White Wines by Eric Perbos-Brinck
This dataset is related to white variants of the Portuguese “Vinho Verde” wine.

Number of Instances: white wine - 4898

The inputs include objective tests (e.g. PH values) and the output is based on sensory data (median of at least 3 evaluations made by wine experts).

Each expert graded the wine quality between 0 (very bad) and 10 (very excellent).

Input variables (based on physicochemical tests):

1 - fixed acidity (tartaric acid - g / dm^3)

2 - volatile acidity (acetic acid - g / dm^3)

3 - citric acid (g / dm^3)

4 - residual sugar (g / dm^3)

5 - chlorides (sodium chloride - g / dm^3)

6 - free sulfur dioxide (mg / dm^3)

7 - total sulfur dioxide (mg / dm^3)

8 - density (g / cm^3)

9 - pH

10 - sulphates (potassium sulphate - g / dm3)

11 - alcohol (% by volume)

Output variable (based on sensory data):

12 - quality (score between 0 and 10)

https://s3.amazonaws.com/udacity-hosted-downloads/ud651/wineQualityInfo.txt

Citation Request: This dataset is public available for research. The details are described in [Cortez et al., 2009]. Please include this citation if you plan to use this database:

P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553. ISSN: 0167-9236.

Available at: [@Elsevier] http://dx.doi.org/10.1016/j.dss.2009.05.016 [Pre-press (pdf)] http://www3.dsi.uminho.pt/pcortez/winequality09.pdf [bib] http://www3.dsi.uminho.pt/pcortez/dss09.bib

UNIVARIATE PLOTS SECTION
## [1] 4898   13
## 'data.frame':    4898 obs. of  13 variables:
##  $ X                   : int  1 2 3 4 5 6 7 8 9 10 ...
##  $ fixed.acidity       : num  7 6.3 8.1 7.2 7.2 8.1 6.2 7 6.3 8.1 ...
##  $ volatile.acidity    : num  0.27 0.3 0.28 0.23 0.23 0.28 0.32 0.27 0.3 0.22 ...
##  $ citric.acid         : num  0.36 0.34 0.4 0.32 0.32 0.4 0.16 0.36 0.34 0.43 ...
##  $ residual.sugar      : num  20.7 1.6 6.9 8.5 8.5 6.9 7 20.7 1.6 1.5 ...
##  $ chlorides           : num  0.045 0.049 0.05 0.058 0.058 0.05 0.045 0.045 0.049 0.044 ...
##  $ free.sulfur.dioxide : num  45 14 30 47 47 30 30 45 14 28 ...
##  $ total.sulfur.dioxide: num  170 132 97 186 186 97 136 170 132 129 ...
##  $ density             : num  1.001 0.994 0.995 0.996 0.996 ...
##  $ pH                  : num  3 3.3 3.26 3.19 3.19 3.26 3.18 3 3.3 3.22 ...
##  $ sulphates           : num  0.45 0.49 0.44 0.4 0.4 0.44 0.47 0.45 0.49 0.45 ...
##  $ alcohol             : num  8.8 9.5 10.1 9.9 9.9 10.1 9.6 8.8 9.5 11 ...
##  $ quality             : int  6 6 6 6 6 6 6 6 6 6 ...
##        X        fixed.acidity    volatile.acidity  citric.acid    
##  Min.   :   1   Min.   : 3.800   Min.   :0.0800   Min.   :0.0000  
##  1st Qu.:1225   1st Qu.: 6.300   1st Qu.:0.2100   1st Qu.:0.2700  
##  Median :2450   Median : 6.800   Median :0.2600   Median :0.3200  
##  Mean   :2450   Mean   : 6.855   Mean   :0.2782   Mean   :0.3342  
##  3rd Qu.:3674   3rd Qu.: 7.300   3rd Qu.:0.3200   3rd Qu.:0.3900  
##  Max.   :4898   Max.   :14.200   Max.   :1.1000   Max.   :1.6600  
##  residual.sugar     chlorides       free.sulfur.dioxide
##  Min.   : 0.600   Min.   :0.00900   Min.   :  2.00     
##  1st Qu.: 1.700   1st Qu.:0.03600   1st Qu.: 23.00     
##  Median : 5.200   Median :0.04300   Median : 34.00     
##  Mean   : 6.391   Mean   :0.04577   Mean   : 35.31     
##  3rd Qu.: 9.900   3rd Qu.:0.05000   3rd Qu.: 46.00     
##  Max.   :65.800   Max.   :0.34600   Max.   :289.00     
##  total.sulfur.dioxide    density             pH          sulphates     
##  Min.   :  9.0        Min.   :0.9871   Min.   :2.720   Min.   :0.2200  
##  1st Qu.:108.0        1st Qu.:0.9917   1st Qu.:3.090   1st Qu.:0.4100  
##  Median :134.0        Median :0.9937   Median :3.180   Median :0.4700  
##  Mean   :138.4        Mean   :0.9940   Mean   :3.188   Mean   :0.4898  
##  3rd Qu.:167.0        3rd Qu.:0.9961   3rd Qu.:3.280   3rd Qu.:0.5500  
##  Max.   :440.0        Max.   :1.0390   Max.   :3.820   Max.   :1.0800  
##     alcohol         quality     
##  Min.   : 8.00   Min.   :3.000  
##  1st Qu.: 9.50   1st Qu.:5.000  
##  Median :10.40   Median :6.000  
##  Mean   :10.51   Mean   :5.878  
##  3rd Qu.:11.40   3rd Qu.:6.000  
##  Max.   :14.20   Max.   :9.000
The variable “X”, not listed in the documentation, is a duplicate ID so we can delete it.

Multiple histograms with raw data
A first look at the summary and the generic histograms shows that many variables have extreme outliers to the right, we may correct it in individual histograms by dropping the extreme 1% values. 

Individual histograms with summary statistics
The individual histograms include average, median, q1 and q3 lines.

Most distributions appear normal and unimodals, with exception of “residual.sugar”.

When running a log_scale, we can see that “residual.sugar” tends to be bimodal.



Fixed Acidity, with bottom and top 1% ignored: normal and unimodal distribution 




Volatile Acidity, with bottom and top 1% ignored: normal and unimodal distribution, skewed to the right. 




Citric Acid, with bottom and top 1% ignored: normal and unimodal distribution 




Residual Sugar, with bottom and top 1% ignored: highly skewed with a long tail to the right 




Residual Sugar, with bottom and top 1% ignored, log10: bimodal distribution around 1.5 and 10.0 values 




Chlorides, with bottom and top 1% ignored: normal and unimodal distribution, small long tail to right 




Free Sulfur Dioxide, with bottom and top 1% ignored: normal and unimodal distribution 




Total Sulfur Dioxide, with bottom and top 1% ignored: normal and unimodal distribution 




Density, with bottom and top 1% ignored: normal and unimodal distribution 




pH, with bottom and top 1% ignored: normal and unimodal distribution 




Sulphates, with bottom and top 1% ignored: normal and unimodal distribution 




Fixed acidity, without bottom and top 1% ignored: normal and unimodal distribution 




Quality, without bottom and top 1% ignored: normal and unimodal distribution






Univariate Analysis
What is the structure of your dataset?
The original dataset consists of 4898 observations of 13 variables. One variable “X” was a duplicate of each observation ID’s and was removed for the analysis.

All variables are numerically measured with the exception of Quality which is a discrete integer from 3 to 9.

What is/are the main feature(s) of interest in your dataset?
The main feature of interest is the Quality variable, discretly measured by a panel of human experts.

What other features in the dataset do you think will help support your investigation into your feature(s) of interest?
The other variables are chemical properties measured by hardware in a laboratory environment, they will serve as a framework to investigate potential relations between chemicals and quality.

Did you create any new variables from existing variables in the dataset?
Beside the use of factor(quality), I created a quality.subset variable (‘Lowest’, ‘Average’, ‘Highest’) for later use in the Multivariate Plots Section.

Of the features you investigated, were there any unusual distributions? Did you perform any operations on the data to tidy, adjust, or change the form of the data? If so, why did you do this?
While looking at the Summary Statistics and the generic Histograms of raw data, I found that most variables suffered from extreme outliers. I chose to remove the bottom and top 1% for individual histograms, while displaying the value of Summary statistics as dotted lines for safeguard.

In the case of residual.sugar, I chose to create a second histogram on a log10 scale which demonstrated a bimodal distribution. 




BIVARIATE PLOTS SECTION
We start with a pairs plot, from psych package, with correlations:



Excluding “free vs total.sulfur.dioxides” due to their direct relationship, We can see strong to moderate correlation in:

density vs residual.sugar 0.84
density vs alcohol -0.78
density vs total.sulfur.dioxide 0.53
alcohol vs total.sulfur.dioxide -0.45
alcohol vs residual.sugar -0.45
alcohol vs quality 0.44
pH vs fixed.acidity -0.43
We are going to represent those via scatter plots.

Scatter Plots


Scatter plot: residual.sugar vs density 




Scatter plot: alcohol vs density 




Scatter plot: total.sulfur.dioxide vs density 




Scatter plot: total.sulfur.dioxide vs alcohol 




Scatter plot: residual.sugar vs alcohol 




Scatter plot: quality vs alcohol 




Scatter plot: fixed.acidity vs pH 




Scatter plot: alcohol vs density 




BOX PLOTS
As Quality is the main feature of interest in the dataset, I chose to dedicate a whole serie of Box Plots to it vs the other variables. Maybe this could reveal some insight.

But in most cases, apart from some diminishing standard deviation as quality rises, little was revealed.

Except in one case: quality vs alcohol, which showed that from Quality=6 and above, there was a clear increase of alcohol levels. 



Box plot: fixed.acidity per quality grade 




Box plot: volatile.acidity per quality grade 




Box plot: citric.acid per quality grade 




Box plot: residual.sugar per quality grade 




Box plot: chlorides per quality grade 




Box plot: free.sulfur.dioxide per quality grade 




Box plot: total.sulfur.dioxide per quality grade 




Box plot: density per quality grade 




Box plot: pH per quality grade 




Box plot: sulphates per quality grade 




Box plot: alcohol per quality grade 




Bivariate Analysis
Talk about some of the relationships you observed in this part of the investigation. How did the feature(s) of interest vary with other features in the dataset?
The feature of interest, Quality, has the strongest variation with the alcohol variable: while lower quality wines seem to share a lower level of alcohol, once quality reach grade 6 and above, there is a significant increase of alcohol means. The other features showed an evenly distribution between the seven quality grades.

Did you observe any interesting relationships between the other features (not the main feature(s) of interest)?
The scatter plots visually confirm the correlations, positive and negative, between chemical components as per the pair plots. For example, there is a strong positive correlation between density and residual.sugar (+0.84) while a strong negative one exists between density and alcohol (-0.78).

What was the strongest relationship you found?
I found the strongest relationship between density and residual.sugar with a correlation (+0.84). 



Multivariate Plots Section
We are going to investigate the Top 3 correlations (> |0.5|) in relation with Quality.

density vs residual.sugar +0.84
density vs alcohol -0.78
density vs total.sulfur.dioxide +0.53 
Also for better ergonomics, we will group the Quality grades into 3 categories:

“Lowest” -> (3, 4)
“Average” -> (5, 6)
“Highest” -> (7, 8, 9)


Scatter plot: residual.sugar vs density by quality 




Scatter plot: density vs alcohol by quality 




Scatter plot: density vs total.sulfur.dioxide by quality 


Building a linear model

We investigate the creation of a linear model using the Top 5 correlated variables, added in decreasing order of correlation below. (comments in the Multivariate Analysis) 

m1 <- lm(I(quality) ~ I(alcohol), data = whites)
m2 <- update(m1, ~ . + density)
m3 <- update(m2, ~ . + chlorides)
m4 <- update(m3, ~ . + volatile.acidity)
m5 <- update(m4, ~ . + total.sulfur.dioxide)

mtable(m1, m2, m3, m4, m5)
## 
## Calls:
## m1: lm(formula = I(quality) ~ I(alcohol), data = whites)
## m2: lm(formula = I(quality) ~ I(alcohol) + density, data = whites)
## m3: lm(formula = I(quality) ~ I(alcohol) + density + chlorides, data = whites)
## m4: lm(formula = I(quality) ~ I(alcohol) + density + chlorides + 
##     volatile.acidity, data = whites)
## m5: lm(formula = I(quality) ~ I(alcohol) + density + chlorides + 
##     volatile.acidity + total.sulfur.dioxide, data = whites)
## 
## ===================================================================================
##                            m1          m2          m3          m4          m5      
## -----------------------------------------------------------------------------------
##   (Intercept)            2.582***  -22.492***  -21.150***  -35.573***  -30.759***  
##                         (0.098)     (6.165)     (6.162)     (6.010)     (6.295)    
##   I(alcohol)             0.313***    0.360***    0.343***    0.389***    0.391***  
##                         (0.009)     (0.015)     (0.015)     (0.015)     (0.015)    
##   density                           24.728***   23.671***   38.217***   33.251***  
##                                     (6.079)     (6.074)     (5.926)     (6.234)    
##   chlorides                                     -2.382***   -1.300*     -1.370*    
##                                                 (0.558)     (0.542)     (0.543)    
##   volatile.acidity                                          -2.043***   -2.070***  
##                                                             (0.111)     (0.111)    
##   total.sulfur.dioxide                                                   0.001*    
##                                                                         (0.000)    
## -----------------------------------------------------------------------------------
##   R-squared                  0.2        0.2         0.2         0.2         0.2    
##   adj. R-squared             0.2        0.2         0.2         0.2         0.2    
##   sigma                      0.8        0.8         0.8         0.8         0.8    
##   F                       1146.4      583.3       396.3       403.0       324.0    
##   p                          0.0        0.0         0.0         0.0         0.0    
##   Log-likelihood         -5839.4    -5831.1     -5822.0     -5657.3     -5654.0    
##   Deviance                3112.3     3101.8      3090.2      2889.2      2885.4    
##   AIC                    11684.8    11670.3     11654.0     11326.6     11322.1    
##   BIC                    11704.3    11696.2     11686.5     11365.6     11367.5    
##   N                       4898       4898        4898        4898        4898      
## ===================================================================================
Multivariate Analysis
Talk about some of the relationships you observed in this part of the investigation. Were there features that strengthened each other in terms of looking at your feature(s) of interest? Were there any interesting or surprising interactions between features?
The Quality subsets, used in scatter plots combined with regression lines, provided a clearer view in two cases:

residual.sugar vs density by Quality: Highest quality wines show significantly higher residual values, per same density, than Lower ones. While Average ones sit in between.

density vs alcohol by Quality: similar distinction but concentrated on lower density values.

There was no such observation in density vs total.sulfur.dioxide by quality, as all three regression lines crossed in the central area of the cloud.

OPTIONAL: Did you create any models with your dataset? Discuss the strengths and limitations of your model.
We created a linear model using the lm() function, gradually including the most correlated variables in descending order (alcohol > density > chlorides …) until completion of m5 model. 
Although it showed some interesting factors as it included more predictors, right from the 1st iteration the R-squared value (adjusted or not) hit a 0.2 value. Thus we felt its potential for prediction was too limited and didn’t convey further investigation with a test set.

Final Plots and Summary
Plot One


Box plot: alcohol per quality grade 

Description One
This plot is the most interesting one as it shows a clear relation between alcohol level and the highest grades of wine quality (7,8,9).

Plot Two


Scatter plot: residual.sugar vs density by quality 

Description Two
This plot positions the three subsets of Quality grades with regards to their combined values of residual.sugar vs density . With the help of regression lines, we can see that Highest Grades tend to have superior residual.sugar values for identical density than Lowest ones.

Plot Three


Scatter plot: density vs alcohol by quality 

Description Three
In accordance with our Plot One (box plot alcohol vs quality), this scatter plot confirms that Highest Grades have distinctively superior alcohol levels than Lowest ones at lower density. But contrary to Plot Two, where both regression lines were parallel, the distinction fades away as density increases; to the point of merging, including with Average Grades, in the vincinity of 1.000 density and 9.0 alcohol. ——

Reflection
This dataset is related to white variants of the Portuguese “Vinho Verde” wine. Number of Instances: white wine - 4898 The inputs include objective tests (e.g. PH values) and the output is based on sensory data (median of at least 3 evaluations made by wine experts). Each expert graded the wine quality between 0 (very bad) and 10 (very excellent). 

I started by understanding the individual variables in the dataset through histograms with summary statistics. Then I investigated the relations of key variables according to their correlations, while setting a specific part to the Feature of Interest being the subjective grade of Quality by the human experts. 
Which showed a stong relation between Higher Grades (7,8,9) and Alcohol levels (12° and above). I then tried to conduct Multivariate Analysis around Quality with other influential variables, based on previous correlation computed. It confirmed some impact on Highest Grades indeed -and Lowest partly- but failed to be fully consistent for Average Grades. 
This reduced scope of efficiency was somehow confirmed when I tried to create a Linear Model to predict Quality with the Top 5 variables: the R-squared value of 0.2 was a show-stopper. 

Based on my own -but limited- experience in oenology, I would suggest including other variables for each wine listed such as type of grape, type of soil and meteorology data during growth and harvest.
