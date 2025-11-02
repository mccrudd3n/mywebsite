Test information here
### **Scaling**

Another kind of feature transformation is **scaling**. Scaling is when you adjust the range of a feature’s values by applying a normalization function to them. Scaling helps prevent features with very large values from having undue influence over a model compared to features with smaller values, but which may be equally important as predictors.

There are many scaling methodologies available. Some of the most common include:

**Normalization**

**Normalization** (e.g., **MinMaxScaler** in scikit-learn) transforms data to reassign each value to fall within the range [0, 1]. When applied to a feature, the feature’s minimum value becomes zero and its maximum value becomes one. All other values scale to somewhere between them. The formula for this transformation is:

xi,normalized=xi−xminxmax−xmin_xi_,_normalized_=_xmax_−_xminxi_−_xmin_x, start subscript, i, comma, n, o, r, m, a, l, i, z, e, d, end subscript, equals, start fraction, x, start subscript, i, end subscript, minus, x, start subscript, m, i, n, end subscript, divided by, x, start subscript, m, a, x, end subscript, minus, x, start subscript, m, i, n, end subscript, end fraction

For example, suppose you have feature 1, whose values range from 36 to 209; and feature 2, whose values range from 72 to 978:

![Scatterplot of 2 unscaled features, each on its own horizontal axis. #1 is bunched in lower values. #2 is spread out.](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZO9a8dZMRWC8Nz7ph0gLzA_df62827fc26c4c9d80a56a18b80623f1_ADA_R-143_Scatterplot-of-2-unscaled-features.png?expiry=1761523200000&hmac=QftdGIUAOL3j7LniVnrMWcbQPzu-Wbw-5RvpIo5HkD8)

It is apparent that these features are on different scales from one another. Features with higher magnitudes of scale will be more influential in some machine learning algorithms, like K-means, where  Euclidean distances between data points are calculated with the absolute value of the features (so large feature values have major effects, compared to small feature values). By min-max scaling (normalizing) each feature, they are both reduced to the same range:

![Scatterplot of 2 normalized features, each on its own horizontal axis. Both features are fully distributed between 0 and 1.](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/FxjouY0iT3eab20GiXCoxQ_785a6047d66342169c2a5104e037b6f1_ADA_R-143_Scatterplot-of-2-normalized-features.png?expiry=1761523200000&hmac=Uw2RM6JVlCzEzsoXOxRB9iuNr7sjY2JHTfGxSPyFH_c)

**Standardization**

Another type of scaling is called **standardization** (e.g., **StandardScaler** in scikit-learn). Standardization transforms each value within a feature so they collectively have a mean of zero and a standard deviation of one. To do this, for each value, subtract the mean of the feature and divide by the feature’s standard deviation:

xi,standardized=xi−xmeanxstand.dev._xi_,_standardized_=_xstand_._dev_._xi_−_xmean_x, start subscript, i, comma, s, t, a, n, d, a, r, d, i, z, e, d, end subscript, equals, start fraction, x, start subscript, i, end subscript, minus, x, start subscript, m, e, a, n, end subscript, divided by, x, start subscript, s, t, a, n, d, point, d, e, v, point, end subscript, end fraction

This method is useful because it centers the feature’s values on zero, which is useful for some machine learning algorithms. It also preserves outliers, since it does not place a hard cap on the range of possible values. Here is the same data from above after applying standardization:

![Scatterplot of 2 standardized features, each on its own horizontal axis. Both features are distributed between -1.49 and 1.79](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/N3NCgty8SQCMK_BgIBGMbQ_4bba7ed489e949daa4d299925a9a58f1_ADA_R-143_Scatterplot-of-2-standardized-features.png?expiry=1761523200000&hmac=A8epB50Z9aEOGrteOZNkFjU88oVysURrxDwsui-vA6g)

Notice that the points are spatially distributed in a way that is very similar to the result of normalizing, but the values and scales are different. In this case, the values now range from -1.49 to 1.76.

### **Encoding**

Another form of feature transformation is known as **encoding**. Variable encoding is the process of converting categorical data to numerical data. Consider the bank churn dataset. The original data has a feature called “Geography”, whose values represent each customer’s country of residence—France, Germany, or Spain. Most machine learning methodologies cannot extract meaning from strings. Encoding transforms the strings to numbers that can be interpreted mathematically.

The “Geography” column contains nominal values, or values that don’t have an inherent order or ranking. As such, the feature would typically be encoded into binary. This process requires that a column be added to represent each possible class contained within the feature.

|**Geography**|**Is France**|**Is Germany**|**Is Spain**|
|---|---|---|---|
|France|1|0|0|
|Germany|0|1|0|
|Spain|0|0|1|
|France|1|0|0|

Tools commonly used to do this include **pandas.get_dummies()** and **OneHotEncoder()**.  Often methods drop one of the columns to avoid having redundant information in the dataset . Note that information isn’t lost by doing this. If you have this…

|**Customer**|**Is France**|**Is Germany**|
|---|---|---|
|Antonio García|0|0|

… then you know this customer is from Spain!

Keep in mind that some features may be inferred to be numerical by Python or other frameworks but still represent a category. For example, suppose you had a dataset with people assigned to different arbitrary groups: 1, 2, and 3:
