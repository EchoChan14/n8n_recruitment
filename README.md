# Resume Screening Automation with n8n

## 📌 專案簡介
本專案為一套以 n8n 為核心所建立的履歷自動篩選系統，從履歷接收 → 自動評分 → Email 應對 → 報到通知與 Google Calendar 整合，模擬 HR 自動化流程。

透過巨量資料處理與流程自動化，替代傳統手動篩選，節省時間、人力與作業錯誤風險。

## 🔍 資料來源
- **履歷內容來源**：Kaggle Dataset  
  🔗 [Kaggle - Resume Dataset](https://www.kaggle.com/datasets/anu0012/resume-dataset)  
- **原始資料夾位置**：`/Resume_Dataset`  
  包含：
  - `resume_json_preview.json`（模擬 Webhook 輸入）
  - `/data/ENGINEERING`、`/data/ACCOUNTANT` 等履歷 PDF
  - `simulated_resume_event_log.xlsx` 為模擬事件紀錄

## 🧠 專案內容說明
| 模組 | 說明 |
|------|------|
| 🟩 resume_json_preview | 解析 PDF 摘要關鍵字與類別標註 |
| ⚙️ n8n 自動化流程 | Webhook → 多層 If 判斷（學歷、技能）→ 自動寄信 + Google Sheets 寫入 |
| 📈 resume_score 評分系統 | 根據關鍵字 + 權重進行履歷自動打分，並給出建議等級（推薦／保留／拒絕） |
| 📧 Email 模板 | 通過者寄出面試邀請，未通過者發出感謝信 |
| 📅 Google Calendar | 面試通知與 HR 自動加入日曆事件 |

## ⏱ 自動化成效
| 項目 | 人工作業 | 自動化後（n8n） |
|------|-----------|------------------|
| 單筆履歷篩選與通知 | 3~5 分鐘 | < 10 秒 |
| 自動寄送 Email | 手動複製＋傳送 | 模板自動寄送 |
| 篩選依據一致性 | 高錯誤率／遺漏風險 | 全程關鍵字自動分析 |

## 🛠 環境需求
- n8n 自架／雲端服務
- Node.js v16+
- Jupyter Notebook（分析模擬用）

## 📂 檔案結構

Resume_Dataset/
├── resume_json_preview.json
├── simulated_resume_event_log.xlsx
├── /data
│ ├── /ENGINEERING
│ ├── /ACCOUNTANT
├── /N8N
│ ├── 自動化流程匯出圖與模擬 .png


## 💡 致謝與備註
資料來源感謝 Kaggle 使用者提供匿名履歷樣本。
本專案僅供學術與流程模擬使用，無實際錄取行為。
