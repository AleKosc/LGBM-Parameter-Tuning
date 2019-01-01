# LGBM-Parameter-Tuning

LightGBM or similar ML algorithms have a large number of parameters and it's not always easy to decide which and how to tune them. In this repo I want to explore which parameters are available and what their effect is on LightGBM.

<p align="center">
  <img src="https://github.com/AleKosc/LGBM-Parameter-Tuning/blob/master/Images/Parameter-Tradeoff.PNG" width="480">
</p>

## Accuracy

## Speed
- save_binary
## Over-Fitting
- min_data_in_leaf
- min_sum_hessian_in_leaf
- max_depth
- lambda_l1
- lambda_l2
- min_gain_to_split
## 1 - Speed / Over-Fitting
- feature_fraction
- bagging_fraction
- bagging_freq
## 2 - Speed / Accuracy
- learning_rate
- num_iterations
## 3 - Accuracy / Over-Fitting
- num_leaves
## 4 - All
- max_bin
- amount of training data
