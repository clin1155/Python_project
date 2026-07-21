# Machine Learning with python | 信用卡核准預測多模型比較

# 專案背景
以信用卡申請者的資料建立一個二元分類模型，預測信用卡申請是否會被核准。本資料表包含15個客戶資料訊息欄(性別、年齡、婚姻狀態、是否為銀行客戶、教育程度、種族、工作年資、過去違約紀錄、是否在職、信用分數、駕照、公民身分、郵遞區號、收入)，以及1個核准與否的結果欄

# 資料來源
Kaggle機器學習的公開資料庫

# 專案目的
本專案希望透過一套完整機器學習流程，展示從一開始的資料清洗，直到最後建立模型並進行比較的結果

# 處理流程
1. 以pandas載入資料
2. 原始資料看似沒有缺失值，是因為原始資料以"?"來表示，本專案採以mean填補數值欄位，以mode填補類別欄位
3. 針對類別欄位進行One-hot encoding
4. 確保train/test的資料對齊
5. 以StandardScalar對資料進行標準化，使模型公平處理各項特徵
6. 選用了Logistic Regression、Random Forest、KNN、SVM等四種模型
7. 使用GridSearch進行參數調校
Logistic Regression：C, solver, max_iter
Random Forest：n_estimators, max_depth, max_features
KNN：n_neighbors, weights, metric
SVM：C, kernel, gamma







