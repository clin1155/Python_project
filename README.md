# 信用卡核准預測：多模型比較與參數調校

# 專案背景
本專案使用 Kaggle 的信用卡申請資料集，建立二元分類模型，預測申請者的信用卡是否會被核准。資料包含申請者背景、財務與信用相關欄位，適合用來練習資料清理、特徵工程與模型比較

# 資料來源
Kaggle 公開資料集：Credit Card Approval [LINK](https://www.kaggle.com/datasets/youssefaboelwafa/credit-card-approval)  
資料共 690 筆，包含數值型與類別型特徵，適合測試不同前處理與模型的表現

# 專案結構
專案說明：README.md  
分析流程：analysis.ipynb  
原始資料：cc_approvals.data

# 專案目的
本專案旨在建立一套可重複使用的機器學習流程，從資料清理、特徵工程到模型訓練與調參，並比較不同分類模型的表現

# 環境與執行方式
+ Python 3.12
+ 主要套件 pandas、numpy、scikit-learn
+ 執行方式 analysis.ipynb

# 前置處理
+ 將 ? 視為缺失值並補值
+ 類別欄位進行 one-hot encoding
+ 使用 StandardScaler 標準化特徵
+ 切分 train/test 資料集

# 模型選擇動機
+ Logistic Regression：作為基準模型
+ Random Forest：處理非線性與特徵交互作用
+ KNN：作為距離式分類比較
+ SVM：測試邊界分類的效果
  
# 專案結果
Accuracy Score 用於判定預測的整體準確率，CV Score 用於評估模型在交叉驗證下的穩定性。下表為各模型在最佳參數搜尋後的測試結果：
| Model | CV Score | Accuracy Score |
| -------- | -------- | -------- |
| Logistic Regression   | 0.8514   | 0.7826   |
| Random Forest   | **0.8749**   | **0.8333**   |
| KNN   | 0.7935   | 0.7246   |
| SVM   | 0.8459   | 0.7463   |

以 Accuracy 而言，Random Forest 表現最佳，且在交叉驗證下也維持穩定；經過 GridSearch 調參後，測試集準確率進一步提升，為本專案表現最佳的模型。SVM 與 Logistic Regression 在交叉驗證階段表現尚可，但測試集表現相對下降，顯示其泛化能力仍有提升空間

# 預期專案可拓展方向
+ 加入Confusion Matrix、ROC Curve 與 F1-score
+ 嘗試更多特徵工程方法
+ 比較更多模型或使用 ensemble 方法
