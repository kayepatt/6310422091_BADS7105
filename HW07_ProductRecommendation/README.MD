:sparkles: This assignment is about Market Basket Analysis which can leads to Product Recommendation result in real business practice. :sparkles:

* Data: Products survey from all class members. Going through 60 products from 47 surveyee answered that had ever bought/ willing to buy each item or not.
* Market Basket analysis: Identify products frequently purchased together
* Algorithm: Apriori

Summary Point by step
1. EDA
-> Top 3: Sunscreen, Bags, Shabu
-> Bottom 3: Food waste composter, PS5, Surfskate

2. Apriori 
This algorithm will pick the frequent items with association rules learing.
Association rules contains antecedent and consequent e.g. morning -> congee, and absolutely either or both could be multi factors.
With the following 3 metrics (measure of performance for rules) we found that;
* Support - the share of transactions that contain an itemset.

 
This time, support is misleading so we will look through another 2 metrics
* Confidence - the probability we will purchase Y given we have purchased X. That means we should increase sales from bundle it!
* Lift - Surprise evaluators. It can generate unforeseen pattern that frequently occur.
If Lift > 1 we can summarize that items occur in transactions together more often than we would expect based on their individual support values. 

So let's filtering the metric by Lift>=1 and Confidence >=0.5


There are 2 more metrics shown in the table so it'd better to understand it!
 
3. Visualization
  * A scatter plot displays pairs of values btw Antecendent and Consequent support ➕ adding 'Lift' by 3rd metric (size)
  Advantages of Scatter plot are visualising entire dataset, Identifying natural threshold
  From below diagram, we know that antecendent has a few fraction of all transaction. Conversely, Consequent be pick more!
  And the size tells that antecendent items with Support value 5 and consequent items with Support value 0.75-0.8 tend to have Surprise pattern.

Special thanks to ⬇️
https://www.srose.biz/research-analysis/market-basket-analysis-in-python/
https://projector-video-pdf-converter.datacamp.com/23877/chapter4.pdf
