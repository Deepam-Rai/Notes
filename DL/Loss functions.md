
General notation:  
$N=$ number of input-output datapoints,  
$x_i =$ i'th input,  
$y_i =$ true/ground truth output corresponding to $x_i$,  
$\hat y_i =$ predicted ouput corresponding to $x_i$,  
$L(y,\hat y) =$ loss,  

----
## MSE (Mean Squared Error)

$$\large L(y,\hat y) = \frac{1}{N}\sum_{i=1}^N(y_i-\hat y_i)^2$$

- Greater the error, greater the penalty.

----
## Cross Entropy

$$\large L(y,\hat y) = -\sum_{c \in C} y_i \log_e(\hat y_i)$$
#TODO verify
$C =$ classes.

----
## Binary Cross Entropy

$$\large L(y, \hat y) = \frac{-1}{N} \sum_{i=1}^N[y_i\log(\hat y_i) + (1-y_i)\log(1- \hat y_i)]$$

----
