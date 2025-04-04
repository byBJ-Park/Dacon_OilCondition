# Dacon_OilCondition
[![image](https://github.com/user-attachments/assets/319914e9-e628-499b-986b-abbfff92d0e7)](https://dacon.io/competitions/official/236013/overview/description)

Public score: 11/517(Macro F1-Score: 0.6027)  
Private score: 15/517(Macro F1-Score: 0.5769)  
*** 
### Dataset
1. train.csv
ID : 부여번호
주어진 모든 Feature (52개)
Y_LABEL : 오일 상태 유무 (0 : 정상 / 1 : 이상)
2. test.csv 
ID : 부여번호
진단 환경에서 사용하는 제한된 Feature (18개)

### 1. Verstack을 통한 Data Preprocessing
 Verstack이라는 framework를 통해서 train.csv와 test.csv 간의 feature 개수의 차이를 해소하였다. Verstack의 lgbmTuner를 사용해서 tree 기반의 boosting 기법들(xgboost, lgbm, catboost) 같은 모델들의 결괏값으로 데이터셋을 새로 생성하였다.
 Verstack(https://github.com/DanilZherebtsov/verstack)
***
### 2. TabNet, Knowledge Distillation
 Tabnet과 Sequential()를 통해 teacher 모델을 3개 생성한 뒤, Tabnet 모델, Sequential 모델(0.4*Teacher + 0.6*Teacher), student 모델을 구축했다. 이 세 가지 모델의 결괏 값의 비중을 조정하여 최종 submission으로 제출하였다.
***
### 3. 느낀점
 2022년 12월 12일에 끝난 대회로 군대에 있을 때 참여했던 대회이다. 높은 대회 성적이 군대 사지방(사이버지식정보방)에서 거뒀다는 점에서 더욱 더 만족스러웠던 대회였다. 하루 일과가 끝나고 매일 같이 사지방으로 가서 모델들과 데이터 전처리 기법들을 찾아보았다. 그 결과로 Verstack과 tabnet이라는 기법에 대해서 찾게 된 것이다.
  이 대회 이전에도 대회를 참가했었지만, 머신러닝 기법으로 대부분 해결하려고 했었다. 반면에 이 대회에서 신경망을 사용함으로써 신경망의 강력함에 대해 더욱 느꼈던 대회인 것 같다. 
