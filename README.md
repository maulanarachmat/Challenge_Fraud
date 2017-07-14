# Challenge_Fraud
Challenge from coursera data science community - Catch the Fraudster

Hello guys!! I am a beginner in data science and just have reach getting and cleaning data lesson.
I try to solve this puzzle because it says on beginner level... and I able to submit this because the help of the forum discussion tip and google.
The data for this challenge can be download on:

    https://docs.google.com/spreadsheets/d/1TufF3QBHK8RsC06V0arvF3PwN3gfz5kg5eV6BjRxEjc/edit#gid=581816440

# My Approaching of solve the challenge
The tips that I get form the forum discussion is about using linear model reggression with first 4 predictor, so we can use:

    #data
    fraud.data <- read.csv("Fraud_Raw_Data.csv")
    #linear model
    fraud.mod <- lm( Fraud.Instance ~ Damaged.Item + Item.Not.Avaiable + Item.Not.In.Stock + Product.Care.Plan, data = fraud.data)

with that we will get the summary:

    Call:
    lm(formula = Fraud.Instance ~ Damaged.Item + Item.Not.Avaiable + 
    Item.Not.In.Stock + Product.Care.Plan, data = fraud.data)

    Residuals:
       Min         1Q     Median         3Q        Max 
    -8.612e-13 -1.750e-15 -5.700e-16 -1.000e-16  2.474e-12 

    Coefficients:
                    Estimate Std. Error    t value Pr(>|t|)    
    (Intercept)        2.000e+00  2.423e-15  8.253e+14   <2e-16 ***
    Damaged.Item      -1.000e+00  1.811e-15 -5.520e+14   <2e-16 ***
    Item.Not.Avaiable -1.000e+00  2.300e-15 -4.348e+14   <2e-16 ***
    Item.Not.In.Stock -1.000e+00  1.741e-15 -5.745e+14   <2e-16 ***
    Product.Care.Plan -1.000e+00  1.882e-15 -5.314e+14   <2e-16 ***
    ---
    Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

    Residual standard error: 4.606e-14 on 4344 degrees of freedom
    Multiple R-squared:      1,	Adjusted R-squared:      1 
    F-statistic: 1.222e+29 on 4 and 4344 DF,  p-value: < 2.2e-16
    
From that we can see that we got R-square 1 and the coefficient for fraud intance is :

    fraud.instance = 2 - 1(Damaged.Item) - 1(Item.Not.Avaiable) - 1(Item.Not.In.Stock) - 1(Product.Care.Plan)

We can see that it will become fraud if ONLY one of the these predictor is claimed

### The things I miss
The process for deciding only use four predictor, how to determined it I still do not know exactly.
My only guess is, when I tried to include all of the predictor into linear model formula (lm) the coefficient for the rest of them is in around e-15 till e-18 order. So I guess we can cancel them out and use only the first four predictor.

### Thats All From Me, Thank You
