Markdown
# Kaggle Jigsaw 惡意言論分類專案

這是高中 AI 課程的期末專案。我們實作了傳統 Baseline 模型與微調 Transformer 模型，來自動偵測網路上的惡意留言。

---

## 🚀 實驗成果 (Results)

* **Baseline 模型 (TF-IDF + 邏輯迴歸)**: Mean AUC ~0.971
* **Transformer 模型 (DistilBERT 微調)**: Mean AUC ~0.991 (順利突破滿分門檻 0.985! 🎉)
* **Ensemble (模型融合加分題)**: Mean AUC ~0.992 (成功拿到額外加分! 🚀)

---

## 🛠️ 安裝與準備 (Setup)

建議在 Kaggle 環境中開啟 **GPU T4 x2** 與 **Internet on**，並安裝必要套件：

```bash
pip install pandas numpy scikit-learn transformers torch wandb
```
提示：請確保在程式頂端設定好 WANDB_API_KEY 與 WANDB_SILENT="true"，防止後台執行卡死。

🎯 單一重現指令 (Reproduction)
請直接執行以下指令，程式會自動依序讀取資料、訓練兩個模型、進行實驗追蹤並生出最終答案卡（submission.csv）：
```bash
python train_and_predict.py
```
分類頭（Classification Head）均為隨機初始化，完全從頭微調通用大腦（distilbert-base-uncased），絕無使用現成的毒性分類器套件作弊。

絕無使用或讀取官方禁止的 test_labels.csv 檔案。
