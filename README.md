# Kaggle - Open Problems - Multimodal Single Cell Integration - 2nd Place Solution

This document is [my part of 2nd place solution](https://www.kaggle.com/competitions/open-problems-multimodal/discussion/366476) for the  [Open Problems - Multimodal Single-Cell Competition](https://www.kaggle.com/competitions/open-problems-multimodal).

For another part, see my team mate [senkin's post](https://www.kaggle.com/competitions/open-problems-multimodal/discussion/366453)

If you have any questions, please feel free to contact me at [baosenguo@163.com](baosenguo@163.com).

### OVERVIEW

This pipeline mainly consists of the following parts:
 - Preprocessing
 - FE
 - Modeling
 
This simple solution produced a quite robust result (Public_lb 1st; Private_lb 2nd).
 
### Preprocessing

- using raw count:

- normalization:

- transformation:

- standardization:

- batch-effect correction:


### Feature engineering

- decomposition

  - pca (64)
  - ipca (128)
  - factor analysis (64)

- features selection

  -  Features highly correlated with target are selected. 245 features are selected in total.

- cell-type (one-hot)


### Modelling

both mlp and lgb used the same features introduced above.

- mlp (simple mlp performs best  (single model with 1 seed - public 0.815; private 0.772))

- lgb

  
### Local CV

- random 5-fold cv
- split according to "day"

### Code

- dataset preparation 
  - /data/prepare.ipynb
  - /data/preprocess.ipynb

- training
  - /model/lgb.ipynb
  - /model/mlp.ipynb
  - /model/blending.ipynb

### requirements

  - python 3.7.5
  - pandas 1.3.5
  - numpy 1.20.3
  - torch 1.9.0
  - sklearn 1.0.2
  
