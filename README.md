# Hedonic_AirBnb
Using TF IDF and a hedonic regression model, see how certain words and clusters of words affect the price of an AirBnB. 

If you save the files and run the notebook, everything should run 

**Findings**
bedrooms (coef = 28.99, p-value = 0.000)
bathroom_num (coef = 26.87, p-value = 0.000)
comment_feat_3 (coef = -96.98, p-value = 0.000)
comment_feat_2 (coef = 64.22, p-value = 0.000)

-Adding one bedroom increases price_num by ~$28.99 on average.
-Adding one bathroom increases price_num by ~$26.87 on average.
-Comment_feat_3 is the comment_feature variable has the largest negative impact on price.
A one-unit increase in comment_feat_3 reduces price by ~$96.98.
Since it is highly significant, it might indicate an important factor (e.g., negative reviews).
--Comment_feat_2 is the comment_feature variable has the largest positive impact on price.

**Interpretation**
comment_feat_2 (+64.12 coefficient):

This topic strongly correlates with higher prices.
Terms strongly associated here were: Logan Square, square, views, rooftop, etc.
This indicates that listings described with words related to Logan Square, good views, rooftops, and desirable location attributes tend to command significantly higher prices.
comment_feat_3 (-96.48 coefficient):

This topic strongly correlates with lower prices.
Terms strongly associated here were: Spanish words ("la", "muy", "es", "que", "en"), and negatively correlated with "field" and "Lincoln".
This suggests that listings described primarily using Spanish-language comments or associated terms are significantly associated with lower-priced listings.

Note: The reason the same word (example: "la") appears with different weights—and even opposite signs—in different topics (comment_feat_X) is because LSA (Truncated SVD) decomposes text data into orthogonal dimensions (topics), each capturing different contextual meanings and associations of the terms across all your comments.

**Real Life Considerations**
This doesn't imply the Spanish language directly reduces prices; rather, it's a proxy indicator for some underlying variable like neighborhood location, listing type, or perceived property value.
Futher Analysis:
Examine the geographical distribution of listings scoring high on comment_feat_3.
Check average property size, condition, or rating differences between groups dominated by comment_feat_2 and comment_feat_3.


**Key Takeaways**
More bedrooms, beds, and bathrooms significantly increase price.
Certain comment features (comment_feat_3, comment_feat_6) have large negative effects, while others (comment_feat_2, comment_feat_1) increase price.
All listed variables are statistically significant (p < 0.05).
The model explains 54% of the variation in price, but additional factors could improve predictions.


Data Source: [AirDnA](https://www.airdna.co/)

