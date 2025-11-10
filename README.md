# credit card fraud prediction
here lies my quick prediction of credit card fraud  
this uses kaggle dataset: [creditcard.csv](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data) (unfortunately it is too huge to throw into github, so feel free to download it from the og website [here](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)!)  

## use case
Fraud detection in real world!!

### Similarities
- Imbalanced data (fraud is rare event)
- High cost of false negatives (missed fraud)
- Need to balance security with user experience
- Optimize for recall while managing false positives

### Differences
- Identity/document fraud vs transaction fraud
- Multi-modal data (docs, images, behavior)
- Real-time at 230M user scale
- Constantly evolving fraud patterns

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
FN is the more dangerous ones we want to minimise, compared to FN  
=> recall is good metric to consider and maybe F1 can be KIV

### actual results
Model | Precision | Recall | F1-Score | ROC-AUC
Log Reg | 0.062560 | 0.878378 | 0.116801 | 0.927770
Log Reg Weighted | 0.062560 | 0.878378 | 0.116801 | 0.927770
Random Forest | 0.874074 | 0.797297 | 0.833922 | 0.898549
XGBoost | 0.138798 | 0.858108 | 0.238946 | 0.924435

### concluding steps
data imbalance is extremely high, recall cannot be assessed accurately. Will have to rely on F1. This means Random Forest should be considered the best of the 4

### moving forward
very minimal hyperparameter tuning was made for the mdoel. more can definitely be done

### amelia's learning points
1. metrics are misleading for imbalanced data
2. choose metrics carefully based on business cost of errors
3. class weighting & smote+tomek is effective for handling imbalance, but doing both might be an overkill
4. ensemble methods generally perform better, but you need to tune them properly
6. trade-offs require business context, not just technical optimization
