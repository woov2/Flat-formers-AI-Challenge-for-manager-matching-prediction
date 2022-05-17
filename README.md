# 플랫포머스(주)와 국민대학교 AI빅데이터융합경영학과가 연계한 [매니저매칭여부 예측 경진대회](https://www.kaggle.com/competitions/2021-daplatformers-final-round/overview)에서 진행된 코드입니다.
## Feature Engineering
* feature create(결측치 개수, n주소, n지역, ...)
* feature drop(매니저최초가입일, 매니저최초서비스일, 매니저주소, 접수시각,...) = 매니저관련 feature들은 비정상적인 score로 인해 drop하도록 되었음.
* data grouping
* NaN processing
* feature subdivision(고객가입일, 접수일,...)
* Mean Encoding
* feature combination(고객개인정보, 매니저개인정보,...)
* One-hot-encoding
* Normalization(numeric feature)
## Feature Selection
* shap package(base=CatBoostClassifier) = feature importance 지수 0이하 feature drop
## Data Split
* Train : 0.7, Valid : 0.3
## Stratified K-fold cross validation(k=4)
* evaluation metrix : AP(average precision) = ROC-AUC로는 자체검증이 불가하였음
## Model
* ExtraTreesClassifier
* CatBoostClassifier
## Training
* Total data Training
## Inference
* ExtraTreesClassifier and CatBoostClassifier 8:2 SoftVoting Ensemble
## Score
* Public(0.88365) 4th
* Private(0.87545) 2nd
