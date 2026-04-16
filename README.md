# Loop Compensation Calculator

Buck / Inverting Buck-Boost 頻率補償計算工具，支援 **ISL8117A** 與 **MAX20098** 兩款 DC-DC 控制 IC。

## 線上使用

GitHub Pages：<https://pyangchen.github.io/loop-comp-calculator/>

## 功能

### ISL8117A — Type III 補償計算
- 依資料手冊 FN8752 *Feedback Loop Compensation* 章節公式
- 計算 R1、R2、R3、C1、C2、C3 元件值
- 繪製開迴路波德圖（增益 & 相位）

### MAX20098 — Type II 補償計算
- 依資料手冊 *Compensation-Components Calculation* 章節公式
- 計算 Rc、Cc、Cf 元件值
- 繪製開迴路波德圖（增益 & 相位）

### 使用說明
- 內建第三個分頁，比較兩顆 IC 的補償架構差異與設計流程

### PDF 匯出
- 每個計算頁面皆可匯出 PDF 備份，檔名自動包含日期與時間

## 技術

純前端應用，無需後端伺服器：
- HTML / CSS / JavaScript（單一 `index.html`）
- [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) — PDF 匯出

## 授權

本工具僅供工程設計參考，計算結果請以原廠資料手冊為準。
