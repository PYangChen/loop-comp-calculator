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

### IBB 模式（Inverting Buck-Boost）
- 兩顆 IC 皆支援 IBB 拓樸，透過等效替換（程式 V<sub>IN</sub> = V<sub>IN,real</sub> + |V<sub>OUT</sub>|）沿用 Buck 補償流程
- 自動計算 RHP Zero：**f<sub>RHPZ</sub> = (1−D)² × R<sub>LOAD</sub> / (2π × L × D)**
- 依 f<sub>C</sub> / f<sub>RHPZ</sub> 比值以顏色警示穩定性（建議 f<sub>C</sub> < f<sub>RHPZ</sub> / 5）

### 實際元件值驗證
- 計算完成後可在「實際元件值」區覆寫購買到的電阻/電容值
- 按「更新波德圖」即可在同一張 Bode 圖上以青/紅曲線疊加比對 PM/GM 差異

### E-series 建議標準值（自動挑選市售值）
- 依指定精度把計算值對齊到 IEC 60063 E-series 標準值，省去手動查表
- 電阻精度可選 **E24 (5%) / E48 (2%) / E96 (1%)**，預設 E96
- 電容精度可選 **E6 (20%) / E12 (10%) / E24 (5%)**，預設 E24
- 採 log-scale 最近值選取（等同百分比誤差最小），跨 decade 亦能正確對齊
- 套用後可再針對個別元件手動微調，不會被鎖死

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
