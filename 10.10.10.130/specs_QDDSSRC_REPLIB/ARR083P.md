# ARR083P - 收款未分配明細表 報表規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 程式名稱 | ARR083P |
| 程式類型 | PRTF (報表格式) |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 作者 | SAM |
| 建立日期 | 97/01/24 |
| 更新日期 | 1997/01/24 |
| 備註 | 收款未分配明細表報表 |

## 2. 報表結構

### 2.1 報表類型
- 報表類型：收款未分配明細表
- 輸出格式：列印報表
- 報表方向：縱向列印

### 2.2 報表組成
- 報表標題頁 (PH1)
- 明細資料頁 (PD1)
- 小計頁 (PD3)
- 報表結束頁 (PE1, PE2, PE9)

## 3. 報表布局

### 3.1 報表標題頁 (PH1)
```
收款未分配明細表
公司別  : XX - XX
產品代號: XXX - XXX
年度月份: YY/MM/DD - YY/MM/DD
日期    : YY/MM/DD
時間    : HH:MM:SS
<ARR083>
使用者  : XXXXX
============================================================
公司別  產品代號  產品名稱  收款日期  收款金額  未分配金額  客戶代號
============================================================
```

### 3.2 明細資料頁 (PD1)
```
XX      XXX      XXXXX     YY/MM/DD  XXXXXX.XX  XXXXXX.XX  XX
```

### 3.3 小計頁 (PD3)
```
小計    : XXXXXX.XX  XXXXXX.XX
```

### 3.4 報表結束頁
- PE1: 報表結束分隔線
- PE2: 報表結束訊息
- PE9: 報表列印完成訊息

## 4. 報表欄位規格

### 4.1 標題頁欄位規格

| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 報表標題 | - | 45 | 15 | A | O | 顯示 "收款未分配明細表" |
| 程式名稱 | - | 97 | 7 | A | O | 顯示 "<ARR083>" |
| 公司別起 | DAC01S | 13 | 2 | A | O | 公司別起始值 |
| 公司別訖 | DAC01E | 18 | 2 | A | O | 公司別結束值 |
| 產品代號起 | DAC02S | 13 | 6,0 | R | O | 產品代號起始值 |
| 產品代號訖 | DAC02E | 24 | 6,0 | R | O | 產品代號結束值 |
| 年度月份起 | DAC09S | 13 | 6,0 | R | O | 年度月份起始值 |
| 年度月份訖 | DAC09E | 24 | 6,0 | R | O | 年度月份結束值 |
| 日期起 | DAC04S | 13 | 6,0 | Y | O | 日期起始值，格式 MM/DD/YY |
| 日期訖 | DAC04E | 24 | 6,0 | Y | O | 日期結束值，格式 MM/DD/YY |
| 日期 | $EGMDY | 97 | 6,0 | Y | O | 報表產生日期 |
| 時間 | TIME | 126 | 8 | T | O | 報表產生時間 |
| 使用者 | $USER | 97 | 10 | A | O | 執行報表使用者 |

## 5. 明細資料欄位規格

### 5.1 明細資料頁欄位規格

| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 公司別 | AC01 | 3 | 2 | A | O | 公司別代號 |
| 產品代號 | AC02 | 11 | 6,0 | R | O | 產品代號 |
| 產品名稱 | ME04 | 22 | 20 | A | O | 產品名稱 |
| 收款日期 | AC05 | 42 | 6,0 | Y | O | 收款日期 |
| 收款金額 | P#A03 | 48 | 10,2 | P | O | 收款金額 |
| 未分配金額 | AC08 | 65 | 9,2 | P | O | 未分配金額 |
| 客戶代號 | AC10 | 79 | 6,0 | R | O | 客戶代號 |
| 客戶名稱 | MC02 | 98 | 20 | A | O | 客戶名稱 |

### 5.2 小計頁欄位規格

| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 小計收款金額 | ENDTOT | 37 | 9,2 | P | O | 小計收款金額 |
| 小計未分配金額 | ENDCUR | 49 | 9,2 | P | O | 小計未分配金額 |

## 6. 報表標題內容

### 6.1 主要標題
- 報表名稱：收款未分配明細表
- 系統名稱：應收帳款系統
- 報表編號：ARR083

### 6.2 報表參數顯示
- 公司別範圍：顯示查詢的公司別起訖值
- 產品代號範圍：顯示查詢的產品代號起訖值
- 年度月份範圍：顯示查詢的年度月份起訖值
- 日期範圍：顯示查詢的日期起訖值
- 報表產生資訊：日期、時間、使用者

## 7. 報表欄位說明

### 7.1 標題欄位說明
- **報表標題**：顯示報表名稱
- **程式名稱**：顯示報表程式代號
- **公司別範圍**：顯示查詢條件的公司別起訖值
- **產品代號範圍**：顯示查詢條件的產品代號起訖值
- **年度月份範圍**：顯示查詢條件的年度月份起訖值
- **日期範圍**：顯示查詢條件的日期起訖值
- **報表產生資訊**：顯示報表產生的日期、時間和使用者

### 7.2 明細欄位說明
- **公司別**：收款所屬的公司別代號
- **產品代號**：相關產品的識別代號
- **產品名稱**：產品的完整名稱
- **收款日期**：實際收款日期
- **收款金額**：實際收款金額
- **未分配金額**：尚未分配到發票的收款金額
- **客戶代號**：客戶的識別代號
- **客戶名稱**：客戶的完整名稱

### 7.3 小計欄位說明
- **小計收款金額**：該分組的收款金額小計
- **小計未分配金額**：該分組的未分配金額小計

## 8. 使用說明

### 8.1 報表用途
此報表用於顯示收款未分配明細資料，協助管理人員了解收款與發票沖帳的差異情況，便於進行收款分配作業和應收帳款管理。

### 8.2 報表特色
- 可依公司別範圍篩選資料
- 可依產品代號範圍篩選資料
- 可依年度月份範圍篩選資料
- 可依日期範圍篩選資料
- 顯示收款金額與未分配金額的對比
- 提供小計功能便於分析

### 8.3 使用時機
- 定期檢視收款分配狀況
- 進行收款沖帳作業
- 分析收款與發票的差異
- 評估應收帳款管理效率

### 8.4 報表解讀
- **收款金額**：實際收到的款項總額
- **未分配金額**：尚未分配到特定發票的收款金額
- **差異分析**：收款金額與未分配金額的差異，可能原因包括：
  - 預收款項
  - 多收款項
  - 沖帳作業延遲
  - 系統處理差異

### 8.5 注意事項
- 報表資料來源為收款主檔和沖帳明細檔
- 未分配金額為收款金額減去已沖帳金額
- 小計依公司別和產品代號分組計算
- 報表可協助發現收款分配異常情況 