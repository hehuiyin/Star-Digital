# Star-Digital

#### Star Digital: Assessing the effectiveness of display advertising 

Star Digital is a video service provider, with over 100M in annual advertising spend. They wanted to understand the impact of banner advertising on sales. Their advertising is priced on the basis of CPM - Cost per Thousand Impressions.

Star Digital's problem:
Some users click on banner ad, go to landing page and make purchase (click-through conversion)

Other users may not click on the banner ad, but may purchase after a subsequent keyword search. Purchase may be attributed to keyword search, yet banner ad may have influenced them (view-through conversion)

If view-through conversions are ignored, then this would under-estimate the return on banner advertising; on the other hand, giving full credit to the banner ads in view-through conversion would over-estimate the return.

Solution we can provide is to conduct a controlled randomized experiment, with users randomly assigned to treatment group (that views the banner ad) and a control group (that sees a fake ad). This allows the measurement of the causal effect of banner advertising on sales conversion.

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

The complete analysis can be seen: https://hehuiyin.github.io/Star-Digital/index.html

