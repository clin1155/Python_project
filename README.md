# 信用卡核准預測：多模型比較與參數調校

# 專案背景
本專案使用 Kaggle 的信用卡申請資料集，建立二元分類模型，預測申請者的信用卡是否會被核准。資料包含申請者背景、財務與信用相關欄位，適合用來練習資料清理、特徵工程與模型比較。

# 資料來源
Kaggle 公開資料集：Credit Card Approval [LINK](https://www.kaggle.com/datasets/youssefaboelwafa/credit-card-approval)  
資料共 690 筆，包含數值型與類別型特徵，適合測試不同前處理與模型的表現。

# 專案結構
專案說明：README.md  
分析流程：analysis.ipynb  
原始資料：cc_approvals.data

# 專案目的
本專案旨在建立一套可重複使用的機器學習流程，從資料清理、特徵工程到模型訓練與調參，並比較不同分類模型的表現。

# 環境與執行方式
+ Python 3.12
+ 主要套件: pandas、numpy、scikit-learn
+ 執行方式: 開啟 "analysis.ipynb" 依序執行即可

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
Best CV Score 用於評估模型在交叉驗證下的穩定性，Test Accuracy 用於觀察模型在測試集上的實際表現。下表為各模型在最佳參數搜尋後的結果：
| Model | Best CV Score | Test Accuracy |
| -------- | -------- | -------- |
| Logistic Regression | 0.8514 | 0.7826 |
| Random Forest | **0.8749** | **0.8333** |
| KNN | 0.7935 | 0.7246 |
| SVM | 0.8459 | 0.7463 |

綜合 Best CV Score、Test Accuracy、F1 Score 與 ROC-AUC，Random Forest 表現最佳，因此作為本專案的最佳模型。其在測試集上的表現也較穩定，顯示此模型具備較好的泛化能力。

# 預期專案可拓展方向
+ 嘗試更多特徵工程方法
+ 比較更多模型或使用 ensemble 方法
+ 加入超參數搜尋範圍更廣的 pipeline
+ 針對不平衡資料嘗試 resampling 或 class weight 調整
