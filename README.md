# LightGBM-Parameter-Tuning

LightGBM or similar ML algorithms have a large number of parameters and it's not always easy to decide which and how to tune them. In this repo I want to explore which parameters are available, their default settings, and what their effects are on the model. As you can see, some of them have a trade-off, which is why I placed them in the overlapping parts. For example, the learning rate affects how fast the model is learning. A high learning rate will lead to faster learning but the model might not find the optimal solution as it might skip over it. Reversely, a low learning rate will likely find a better solution but training will take much longer.

I also list a few parameters that are also useful but didn't really fit in the Venn diagram. For a complete list of parameters see: https://lightgbm.readthedocs.io/en/latest/Parameters.html. 

<p align="center">
  <img src="https://github.com/AleKosc/LGBM-Parameter-Tuning/blob/master/Images/Parameter-Tradeoff.PNG" width="480">
</p>

## Accuracy

## Speed
- save_binary = False --> Set to True for faster loading next time you run LightGBM.
- enable_load_from_binary_file = True --> Set to True if a binary file exists (created through save_binary) but you don't want to use it.
### Parallelisation
- tree_learner = "serial" --> Set to "feature", "data" or "voting" if you can use parallelisation.

<p align="left">
  <img src="https://github.com/AleKosc/LGBM-Parameter-Tuning/blob/master/Images/parallel.PNG">
</p>

- num_threads = no. of real CPU cores
## Over-Fitting
- min_data_in_leaf = 20 --> Increase this number to avoid overfitting but it can lead to lower accuracy.
- max_depth = -1 --> Set this number to limit the size of the tree. -1 means there is no limit on the tree size.
- lambda_l1 = 0 --> Increase this number up to 1 for L1 regularisation.
- lambda_l2 = 0 --> Increase this number up to 1 for L2 regularisation.
- min_gain_to_split
## 1 - Speed / Over-Fitting
- feature_fraction = 1 --> All features will be used. Reduce this number up to 0 to select fewer randomly chosen features, which reduces over-fitting. 
- bagging_fraction = 1 --> It is like feature_fraction, but will randomly select part of the data without resampling
- bagging_freq = 0 --> Bagging should be carried out after each k iteration.bagging_fraction should be set smaller than 1 in that case.
## 2 - Speed / Accuracy
- learning_rate = 0.1 --> A smaller rate slows down training but increases accuracy. Increase num_iterations when you lower the learning rate.
- num_iterations = 100 --> A larger number of iteration will slow down training but can lead to increased accuracy.
## 3 - Accuracy / Over-Fitting
- num_leaves
## 4 - All
- max_bin = 255 --> The max number of times a feature can be split.
- amount of training data --> The more data the slower the training but better predictions.
## Other Parameters
### Memory
- two_round = False --> Set to True if dataset is too large, which would cause a Memory Error.
### Metric
- metric = "" --> Choose the evaluation metric such as RMSE, MAPE, AUC etc.
