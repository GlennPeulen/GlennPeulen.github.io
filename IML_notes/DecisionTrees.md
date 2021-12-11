---
layout: post
title:  "Decision Tree"
date:   2021-12-12 23:00:00 +0530
author: Rem Nector
subject: post
background: /assets/img/DecisionTree.png
---

## Classification and Regression Trees (CART)

Relationship between the outcome and the features is defined as

$$ \hat{y} = \hat{f}(x) = \sum^M_{m=1} c_m I\{x \in R_m\} $$

Each instance falls into exactly one leaf node $R_m$. $I_{\{ x \in R_m\}}$ is the identity function that return 1 if $x$ is in the subset $R_m$. Therefore, when an instance falls into a leaf node $R_l$, the predicted outcocme is $\hat{y} = c_l$, where $c_l$ is the average of all training instances in leaf node $R_l$.


CART relies on finding the best cutoff point that minimizes the variance in the individual nodes after the split. This variance is quantified using Gini Index. In case of categorical features,  the algorithm looks at groupings of categories. Once the best cutoff per features has been determined, the algorithm selects the feature that would result in the best partition in terms of variance of Gini index for splitting. This split is added to the tree.

Possible stop criteria: Minimum number of instances that have to be in a node before the split, or the minimum number of instances that have to be in a terminal node.

### Interpretation

Template: If feature x is [smaller/bigger] than the threshold c AND ... then the predicted outcome is the mean value of y of the instances in that node.

**Feature Importance**
Overall importance: Measuring how much Gini Index/variance is minimized in each split where a particular feature was used as compared the parent node. The sum of all importances can be scaled to 100.

**Tree decomposition**
$$\hat{f}(x) = \bar{y} + \sum^{D}_{d=1} split.contrib(d,x) = \bar{y} + \sum^p_{j=1} feat.contrib(j,x)$$

where D splits exists in a tree and p is the number of features.
