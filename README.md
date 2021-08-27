# Star-Digital

## Star Digital: Assessing the effectiveness of display advertising 

### Background & Overview of the analysis: 
Star Digital is a video service provider, with over 100M in annual advertising spend. They wanted to understand the impact of banner advertising on sales. Their advertising is priced on the basis of CPM - Cost per Thousand Impressions.

Star Digital's problem:
Some users click on banner ad, go to landing page and make purchase (click-through conversion). Other users may not click on the banner ad, but may purchase after a subsequent keyword search. Purchase may be attributed to keyword search, yet banner ad may have influenced them (view-through conversion).

If view-through conversions are ignored, then this would underestimate the return on banner advertising; on the other hand, giving full credit to the banner ads in view-through conversion would overestimate the return.

Solution:
Our solution is to conduct a controlled randomized experiment, with users randomly assigned to treatment group (that views the banner ad) and a control group (that sees a fake ad). This allows the measurement of the causal effect of banner advertising on sales conversion.

* Data includes the following variables:
  + purchase: A dummy variable indicating whether the consumer eventually purchased at Star Digital or not
    + =0: no purchase
    + =1: purchase
  + imp_1: The number of ad impressions for either Star Digital or the charity that the consumer saw at website#1
  + imp_2: The number of ad impressions for either Star Digital or the charity that the consumer saw at website#2
  + imp_3: The number of ad impressions for either Star Digital or the charity that the consumer saw at website#3
  + imp_4: The number of ad impressions for either Star Digital or the charity that the consumer saw at website#4
  + imp_5: The number of ad impressions for either Star Digital or the charity that the consumer saw at website#5
  + imp_6: The number of ad impressions for either Star Digital or the charity that the consumer saw at website#6
  + test: A dummy variable indicating whether the consumer was in the test or control group. 
    + =0: control
    + =1: test

### Part I. Online Advertising effectiveness 
After splitting the data into control and test groups and making sure that the means of this two group are significantly indifferent through a t-test, we ran a logistic regression model of the binary variable "purchase" on variable "test".
<img width="525" alt="Screen Shot 2021-08-27 at 13 39 42" src="https://user-images.githubusercontent.com/73683982/131186062-44d41642-3374-40e4-95f5-c0f0fe8e569d.png">

We assume our level of significance to be 0.1 because our case is in a business context. Since the p-value is 0.0614 which is less than 0.1, the variable “test” is statistically significant and indicates that exposing consumers to Star ads has a positive effect on purchasing the package.

### Part II. Frequency effect of advertising on purchase
To assess whether increasing the frequency of advertising would increase the probability of purchasing, we want to explore the interaction between impression frequency and whether the customer sees the ads of Star Digital.
<img width="565" alt="Screen Shot 2021-08-27 at 13 47 10" src="https://user-images.githubusercontent.com/73683982/131186803-47c97d21-c2ed-45f2-887c-a148d534b1c0.png">

From the model result, we can see that in the test group, with one unit increase in impression, there will be 1.76% increases in the chance of purchasing. In the control group, with every additional unit increase in impression, there will be 1.60% increases in the chance of purchasing.

While the two numbers seem to be very close, the test group is still slightly higher than the control group on increasing the odds of purchasing by 0.16%, we can conclude that increasing the frequency of advertising will increase the probability of purchasing.

### Part III. Conversion effectiveness of Sites 1-5 compare with that of Site 6
In order to compare between site 1-5 and site 6, we added up the impression from site 1-5 and ran a logistic regression model on variables ‘imp_15’, ‘imp_6’, ‘test’ and their interaction terms.

<img width="539" alt="Screen Shot 2021-08-27 at 13 51 03" src="https://user-images.githubusercontent.com/73683982/131187155-ca979587-620c-45bf-9ed7-ff7a2f767d5b.png">

From the model result, we can see that for the test group, increasing 1 unit of impression increases the odds of purchasing by 2.84% on site 1-5 and increasing 1 unit of impression increases the odds of purchasing by 1.14% on site 6. Thus, we can conclude that ads on site 1-5 are more effective in terms of conversion than site 1-5 since the increase of odds of purchasing for site 1-5 is more than site 6.

### Part IV. Which sites to focus on?
From the previous part, we have concluded that site 1-5 is more effective. In this part, we will take the cost of the ads on each website into account to determine which one has a better ROI. The cost of advertising at Site 1-5 is 25 dollars per thousand impressions and the cost of advertising at Site 6 is 20 dollars per thousand impressions. And a purchase results in a lifetime contribution of 1,200 dollars for Star Digital.

We included offset values (Population conversion rate=0.00153; Sample conversion rate=0.50) in our model to recover the biased estimate of the constant term due to oversampling in the dataset. 

<img width="531" alt="Screen Shot 2021-08-27 at 14 05 54" src="https://user-images.githubusercontent.com/73683982/131188584-bd7f6e2f-cf8a-4fb2-bcd2-2682c32f296a.png">

ROI calculation:

<img width="451" alt="Screen Shot 2021-08-27 at 14 12 20" src="https://user-images.githubusercontent.com/73683982/131189119-a1c7ae86-e972-416f-b23b-fa9454ead300.png">

From the above calculation, we can conclude that site 6 has a higher ROI than site 1-5 and thus, Star Digital should put its advertising budget on site 6.

The complete analysis can be found on:
https://hehuiyin.github.io/Star-Digital/index.html

