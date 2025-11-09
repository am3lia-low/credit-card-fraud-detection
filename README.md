# credit card fraud prediction
here lies my quick prediction of credit card fraud  
this uses kaggle dataset: [creditcard.csv](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data) (unfortunately it is too huge to throw into github, so feel free to download it from the og website [here](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)!)  

## quick understanding of dataset
this guy has been pushed through PCA (understandably so)  
so lots of the numbers don't really make sense to us  
some distributions are similar, as some kaggle notebooks suggest, but because it's amelia's speedrun i didn't really do a detailed analysis of it  

## handling imbalanced data
as data is skewed with a fraud rate of 0.173%, smote + tomek links were used to rebalance the data

## missing data
none! so alls good!
  
## quick summary of models used
- logistic regression
- logistic regression with weights (this was more of a sanity check, really)
- tuned logistic regression
- random forest
- xgboost

## summary of results
### metrics
