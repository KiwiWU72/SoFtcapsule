# 軟膠囊精算系統 (Softgel Actuarial System)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SheetJS](https://img.shields.io/badge/SheetJS-00A65A?style=for-the-badge&logo=spreadsheet&logoColor=white)

這是一個專為保健食品與快消品（FMCG）產業設計的輕量化、視覺化軟膠囊生產試算工具。

本系統摒棄傳統經驗法則，改以**第一性原理（First Principles）**為基礎，對軟膠囊的生產流程進行最極限的底層機制檢視。從明膠粉投入的「質量守恆」，到膠網廢料回收的「幾何收斂級數」，再到終端包裝的精細成本拆解，提供研發與業務端具備科學數據支持的決策模型。

## 核心底層機制

本系統的計算核心立足於兩大物理與數學模型：

### 1. 質量守恆與配比極限 (Mass Conservation)
化膠過程中的總重量，嚴格遵循原料投入配比。系統內建針對不同溫濕度環境的極限測試參數：
* **冬季配方（高塑化型）**：明膠 : 塑化劑（甘油） = 1 : 0.40。擴大自由體積，抵抗低溫脆性斷裂，代價為乾燥時間拉長。
* **夏季配方（低塑化型）**：明膠 : 塑化劑 = 1 : 0.28。限制甘油吸收環境水分，維持膠囊外殼機械剛性，防止高溫熱熔合沾黏。

### 2. 膠網回收的幾何收斂級數 (Geometric Convergence Model)
生產過程中的「有效利用率（U）」並非單純的線性扣除，而是基於膠網廢料不斷回填再利用的無窮等比級數。
系統採用的極限收斂公式為：
> **U = (1 − S) ÷ (1 − S × R)**
* *S = 膠網廢料率 (Scrap Rate)*
* *R = 極限回收率 (Recovery Rate)*

透過此公式，系統能精準推算出在給定損耗下，實際轉化為成品膠皮的極限量。

## 主要功能 (Features)

* 📊 **即時動態產量預估**：透過 SVG 動畫流程圖，視覺化呈現從明膠（如 GELITA 牛骨膠）、純水、塑化劑到濕膠液，再到成品膠皮的質量流動與損耗變化。
* 💰 **全鏈路成本精算**：
  * **內料**：支援魚油、藻油、印加果油等多種填充物，並計入桶底損耗。
  * **膠皮**：精算明膠、甘油、山梨醇的單價與實際消耗量。
  * **包裝**：涵蓋 PTP 打片（10 粒/片）、鋁袋（3 片/包）、紙盒與附加耗材（雷射標、圓點貼紙、收縮膜）的成本疊加。
* 📈 **逆向定價與毛利分析**：輸入目標終端市場售價或預期毛利率，系統自動反推批次總盈虧與單盒/單箱出貨建議價。
* 📑 **Excel 報表匯出**：整合 `SheetJS (xlsx.js)`，一鍵匯出包含所有參數設定與計算明細的 `.xlsx` 報表，便於建檔與跨部門溝通。

## 系統截圖 (Screenshots)

*(請在此處替換為系統的實際畫面截圖，建議包含「動態流程圖」與「成本計算結果」的特寫)*
## 安裝與使用方式 (Usage)

本系統為純前端架構 (Vanilla JS/HTML/CSS)，無須安裝任何後端環境或進行 Build 流程。

1. `git clone` 此專案。
2. 直接使用瀏覽器（推薦 Chrome 或 Edge）開啟 `index.html`。
3. 於左側面板調整原料配比、損耗率或各環節單價，右側數據與動畫將即時更新。

## 依賴套件 (Dependencies)

* [SheetJS (xlsx.js)](https://github.com/SheetJS/sheetjs) - 於 `<script>` 標籤中透過 CDN 引入，用於前端直接匯出 Excel 檔案。
* 字體：Google Fonts (`Inter`, `Cormorant Garamond`)

## 目錄結構 (Structure)

```text
.
├── index.html       # 主程式入口（包含所有 HTML, CSS 與核心運算 JS）
└── README.md        # 專案說明文件
