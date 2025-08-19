# Data types

Based upon nature and kind of information it represents:
1. Quantitative data(Numerical data)
	1. Continuous data: Measurable quantities that can take any value within given range. 
		1. e.g., temperature, height, weight, etc.
	2. Discrete data: Countable quantities.
		1. e.g., number of votes, number of bedrooms, etc.
2. Qualitative data(Categorical data)
	1. Ordinal: Categorical data that have meaningful order/ranking, but the interval between the ranks are not necessarily equal.
		1. e.g., ratings(poor, good, best), competition ranking(1<sup>st</sup>, 2<sup>nd</sup>, 3<sup>rd</sup>), etc
	2. Nominal: Categorical data that have no meaningful order/ranking.
		1. e.g., colors, names of places, etc.
	3. Binary data: Categorical data that have only two values.
		1. e.g., true/false, yes/no, pass/fail, positive/negative, etc.
		2. Is binary data ordinal or nominal? - **"otiose to muse on"** as stated in [this stackoverflow discussion](https://stats.stackexchange.com/questions/169604/can-binary-data-be-ordinal).

----

# Encoding Categorical data
Often categorical data are in string format, or in numeric format but their values not representing true nature of order/ranking among them. Often we need to transform/encode these categorical values into new numerical representations for them to be used in different algorithms/AI model training.  

## Nominal categorical data
### One Hot encoding
Each category is represented as unique binary vector.
Pros:
1. Preserves nature of nominal encoding - no inherent ranking.
Cons:
3. High dimensionality: More categories $\implies$ more new features.

## Ordinal categorical data

### Label encoding
Each category is assigned unique integer, such that the values corresponds to their natural order/ranking.  
Pros:
1. Preserves order/ranking of data.
2. Can be effectively used for binary data as well.

Cons:
1. High cardinality: More categories $\implies$ higher integer label values, which can be misinterpreted algorithms as having mathematical significance.

----
