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


