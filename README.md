# 📊 台股個股初步分析｜TW Stock Initial Analysis

![Profile views](https://komarev.com/ghpvc/?username=mjib007&label=Profile%20views&color=4c8eda&style=flat)
[![Stars](https://img.shields.io/github/stars/mjib007/stock-analysis?style=flat&color=yellow)](https://github.com/mjib007/stock-analysis/stargazers)
[![Forks](https://img.shields.io/github/forks/mjib007/stock-analysis?style=flat&color=blue)](https://github.com/mjib007/stock-analysis/network/members)
![AI](https://img.shields.io/badge/AI-Claude%20(Anthropic)-blueviolet)
![Platform](https://img.shields.io/badge/Platform-claude.ai%20%7C%20ChatGPT%20%7C%20Gemini-orange)
![Language](https://img.shields.io/badge/Language-繁體中文-red)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey)](LICENSE)
![Status](https://img.shields.io/badge/status-active-success)

> 一套六步驟的台股個股初步分析框架，核心原則是「**現金流優先、基本面在後**」——先用現金流量表做「盲測」，避免公司背景、產業地位、法說會樂觀話術等資訊，讓分析帶著先入為主的印象。

> ⚠️ **這是分析方法論，不是投資建議。** 產出的評分、估值、觀察訊號，僅為輔助思考的工具，不構成買賣邀約。投資有風險，請自行判斷並承擔後果。

---

## ✨ 功能特色

- 🔒 **現金流優先，盲測判斷**：第一步只看現金流量表數字本身，避免先入為主，評分低於門檻時主動建議停止後續分析
- 🎭 **擬人化解讀**：把冰冷的財務數字轉譯成「老將自費特訓型」、「寅吃卯糧型」等直覺標籤
- 🔗 **來源必附連結**：任何查得的市場數據都要附上實際查詢頁面連結，可逐項覆核打勾／打叉
- 📈 **雙重估值檢視**：前瞻本益比（股價反推倍數）與目標本益比法（倍數反推目標價）並用，交叉檢視現在貴不貴
- 🧭 **可跳步、可單步執行**：可只問「法說會怎麼看」、「營收趨勢圖」，不必每次從頭走完六步
- 🗂️ **自動化版控**：每完成一步驟即可自動 git push 到 GitHub，並附上 GitHub Pages 連結方便回顧

---

## 📁 專案內容

| 檔案 | 說明 | 適用平台 |
|------|------|----------|
| `SKILL.md` | Claude Skills 工具專屬版（含 create_file／git push 等自動化流程） | Claude.ai Skills 功能 |
| `台股個股分析框架_通用版.md` | 拿掉Claude工具專屬指令的通用版 | ChatGPT、Gemini 等所有 AI 對話介面 |
| `reports/*_analysis.html` | 歷次分析報告範例（每檔股票一份，六步驟累加於同一檔案） | 瀏覽器直接開啟或 GitHub Pages |
| `index.html` | 所有報告的總覽首頁（可搜尋／篩選／依日期排序） | GitHub Pages 進站首頁 |
| `README.md` | 本說明文件 | — |

---

## 🗂️ 流程概覽

**六步驟不是隨意排列的檢查清單，而是仿照中醫「先求不傷身，再求療效」的邏輯層層推進：**

1. **不傷身體**（Step 1）：現金流量表能看到帳面數字之外的隱藏現象，先確認這家公司的體質沒問題，再往下看。
2. **講求療效**（Step 2）：確認安全之後，才看「現在有沒有效」——營收、獲利、EPS 這些當下一般投資人喜歡關注的指標。
3. **未來也會好嗎**（Step 3、4）：現在有效不代表以後也有效，這兩步是在確認「未來的趨勢是不是也好」。一般會先看法說會，這是管理層對未來的說法，月營收則是驗證這個說法有沒有兌現最快的方式（因為季報資料通常已經是一兩個月前的舊消息），當然以後搭配新聞等其他訊息。
4. **掂量貴不貴**（Step 5）：體質、療效、未來趨勢都沒問題後，才問「這個價格划不划算」。
5. **做出決策**（Step 6）：最後才回答「要不要進場」。

| 步驟 | 內容 | 說明 |
|------|------|------|
| Step 1 | 現金流量表六大規則分析 | 盲測階段，最優先，未過門檻可建議停止 |
| Step 2 | 基本資訊查詢 | 股價、EPS、殖利率、營收、法說會連結，附出處 |
| Step 3 | 法說會資料深入討論 | 依前一步驟提供法說會連結，有問題就交互討論 |
| Step 4 | 營收趨勢視覺化 | 近 8-12 期月營收直條圖，使用者主動截圖或AI搜尋二選一 |
| Step 5 | EPS／本益比 預估合理股價 | 前瞻本益比＋目標本益比法雙重檢視，誠實揭露預估不確定性 |
| Step 6 | 投資決策推理 | 僅使用者主動詢問才做，給具體可驗證的觀察訊號，非模糊建議 |

---

## 🚀 使用方法

### 方法一：Claude Skills 版（推薦 Claude.ai 用戶使用）

**步驟：**
1. 進入 [Claude.ai](https://claude.ai)，點選帳號，找到「設定（Settings）」
2. 將本repo的 `SKILL.md`下載到本機電腦
3. **先修改檔案內的佔位符**：把 `{your-username}/{your-repo}` 換成你自己的 GitHub repo，否則 AI 會嘗試 push 到別人的 repository
4. 在設定（Settings）找到Skills，找到新增「Add」，選擇Upload a skill
5. 將第二步驟下載的`SKILL.md`上傳至Claude
6. 之後在Claude內表示分析股票名稱或股票代號，即自動啟動分析程序

> ⚠️ 此版本包含 Claude 專屬工具指令（`create_file`／`present_files`／`bash` 等），**僅限 Claude.ai** 使用。

#### 🔑 關於自動化版控（Git Push）需要的 GitHub Token
 
若你的 `SKILL.md` 保留了「Git 版控與發布規則」章節，Claude 在第一次要 push 報告之前，會**主動向你索取 GitHub Personal Access Token**。準備方式（二選一）：

**方法 A：手動點擊路徑**
1. 點畫面右上角你的頭像（注意：不是在某個 repo 頁面點，要在 GitHub 任何頁面都可以）→ 選單選 **Settings**
2. 進入「你的帳號設定」頁面（網址會變成 `github.com/settings/profile`），**左側選單最下方**會看到 **Developer settings**
3. 依序點：**Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**

**方法 B：網址捷徑（跳過找選單）**
- 登入狀態下，直接在網址列輸入 [github.com/settings/tokens?type=beta](https://github.com/settings/tokens?type=beta)，會直接進入建立 Fine-grained token 的頁面
- ⚠️ 這是捷徑網址，若 GitHub 未來改版導致此網址失效，請改用方法 A 的手動路徑

**兩種方法走到最後，設定步驟相同：**
3. **Repository access** 選 **Only select repositories**，選你自己的 repo
4. **Permissions** 裡把 **Contents** 設成 **Read and write**
5. **Generate token** 後複製給 Claude
**注意事項：**
- 這組 token 只在**當次對話**中使用，Claude 不會把它存進記憶，換一個新對話分析下一檔股票時要重新提供
- Token 直接貼在對話裡屬於明碼傳輸，建議設定過期時間，且用完後可以到 GitHub 設定裡撤銷重發
- 若不想每次都要提供 token，可以刪除 `SKILL.md` 中「Git 版控與發布規則」整個章節，改成手動下載報告自行上傳
  
---

### 方法二：通用 Prompt 版（跨平台通用）

適合使用 ChatGPT、Gemini 等其他 AI 對話工具的使用者。

**步驟：**
1. 開啟 `台股個股分析框架_通用版.md`，複製全部Skills內容
2. 直接貼入任何個別AI 對話框，或專案的使用說明、指令，或其他可貼上Skills內容的地方
3. 執行後，Skills會引導你開始分析

> ⚠️ 此版本不含檔案自動生成與 Git 版控功能，每次**新對話**需重新貼入。

---

## 🧪 使用示範

**輸入：** 「幫我分析華新科（2492）」

**工具回應（第一步關卡判斷）：**
> 總評分 57.5 分（需觀察，未達 60% 門檻）。核心疑慮：連續多年重度投資（B）未能扭轉營業現金流（A）逐年下滑的趨勢，且期末現金餘額也出現大幅回落。建議您先決定是否要繼續往下看基本面，還是先停在這裡？

後續六步走完，還會依現金流結論、估值落差，給出具體可驗證的觀察訊號（例如「等處置期滿、股價企穩至目標本益比區間附近再考慮進場」），而不是模糊的「看情況」。

---

## ⚙️ 使用前必須修改的地方

`SKILL.md` 中的 Git 版控設定為個人化內容，**使用前務必替換**：

| 原始內容（佔位符） | 替換為 |
|---|---|
| `https://github.com/{your-username}/{your-repo}` | 你自己的 repo 網址 |
| `http://{your-username}.github.io/{your-repo}/{檔名}` | 你自己的 GitHub Pages 網址格式 |

若不需要 Git 版控功能，可直接刪除 `SKILL.md` 中「Git 版控與發布規則」整個章節。

---

## 🧩 已知限制

- 股價、EPS、營收等數字依賴網路搜尋與第三方網站，同一時間點不同來源偶爾會不一致；流程設計上會如實並陳、不擅自判斷對錯，但仍建議自行以官方公告（公開資訊觀測站 MOPS）或看盤軟體核實
- 部分官網簡報 PDF 因 robots.txt 限制無法直接讀取內容，只能附連結供自行查閱
- **使用者截圖提供的原始資料，通常比 AI 自行搜尋取得的資料更可靠**，關鍵數字（現金流量表、月營收、月K棒）建議優先用截圖方式提供

---

## 📜 授權

本專案以 [CC BY-NC 4.0（姓名標示－非商業性）](LICENSE) 授權，歡迎自由使用、修改與分享，但需標明出處且不得用於商業用途。

## ⚠️ 免責聲明

本專案及其產出的任何分析報告，均為個人研究輔助工具，不構成任何形式的投資建議、要約或保證。使用本專案進行的任何投資決策及其後果，概由使用者自行負責。作者不對任何資料的準確性、完整性或即時性做出保證。
