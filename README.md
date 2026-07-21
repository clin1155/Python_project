# 信用卡核准預測：多模型比較與參數調校

# 專案背景
本專案使用 Kaggle 的信用卡申請資料集，建立二元分類模型，預測申請者的信用卡是否會被核准。資料包含申請者背景、財務與信用相關欄位，適合用來練習資料清理、特徵工程與模型比較

# 資料來源
Kaggle機器學習的公開資料庫 [LINK](https://www.kaggle.com/datasets/youssefaboelwafa/credit-card-approval)

# 專案目的
本專案旨在建立一套可重複使用的機器學習流程，從資料清理、特徵工程到模型訓練與調參，並比較不同分類模型的表現

# 專案結果
| Model | CV Score | Accuracy Score |
| -------- | -------- | -------- |
| Logistic Regression   | 0.8514   | 0.7826   |
| Random Forest   | 0.8749   | 0.8333   |
| KNN   | 0.7935   | 0.7246   |
| SVM   | 0.8459   | 0.746   |


