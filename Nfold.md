## N-fold Cross-Validation
### Intro
<div class="sl-block is-focused" data-block-type="image" data-name="image-904f80" style="width: 908.132px; height: 619px; left: 25.934px; top: 81px; min-width: 1px; min-height: 1px;" data-origin-id="8cbfebf26d437a63825c00a801b80177"><div class="sl-block-content" style="z-index: 11;"><img style="" data-natural-width="1828" data-natural-height="1246" data-lazy-loaded="" src="https://s3.amazonaws.com/media-p.slid.es/uploads/1169602/images/9644935/Screenshot_from_2022-06-15_23-03-24.png"></div></div>
### Code
```python

# scikit-learn k-fold cross-validation
from numpy import array
from sklearn.model_selection import KFold
# data sample
data = array([0.1, 0.2, 0.3, 0.4, 0.5, 0.6])
# prepare cross validation
kfold = KFold(3, True, 1)
# enumerate splits
for train, test in kfold.split(data):
	print('train: %s, test: %s' % (data[train], data[test]))
```

#### Reference
1. Jason Brownlee. (May 23, 2018). "A Gentle Introduction to k-fold Cross-Validation". machinelearningmastery. https://machinelearningmastery.com/k-fold-cross-validation/
