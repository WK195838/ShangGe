# ARR054D 螢幕規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARR054D |
| 檔案類型 | 螢幕格式檔 (DSPF) |
| 檔案描述 | 轉帳/寄賣發票列印設定 |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 程式名稱 | ARR054 |
| 作業系統 | AS/400 |

## 2. 螢幕規格

| 項目 | 規格 |
|------|------|
| 螢幕大小 | 24×80 |
| 顯示裝置 | DSPSIZ(24 80 *DS3) |
| 訊息位置 | 第24列 |
| 列印支援 | 支援 (PRINT) |
| 參考檔案 | *LIBL/RERF |

## 3. 螢幕布局

```
第1列：  ARR054                    [系統訊息]                   日期: MM/DD/YY
第2列：  SCR001            轉帳／寄賣發票列印                 時間: HH:MM:SS
第3列：                            套表                        USER: XXXXXXXXXX

第5列：                    發票日期: MM/DD/YY - MM/DD/YY
第7列：                    發票號碼: __________ - __________
第9列：                    客戶代碼: _______ - _______
第11列：                   發票類型: _ (1=轉帳 2=寄賣 3=全部)
第13列：                   列印格式: _ (1=套表格式)

第22列： 操作   F3 =回到前頁   F12=執行列印

第24列：                                          [使用者訊息]
```

## 4. 紀錄格式

### 輸入條件

| 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|------|------|------|------|------|
| 發票日期起 | 5,30 | 6 | N | B | 發票日期起始值 |
| 發票日期迄 | 5,42 | 6 | N | B | 發票日期結束值 |
| 發票號碼起 | 7,30 | 10 | A | B | 發票號碼起始值 |
| 發票號碼迄 | 7,42 | 10 | A | B | 發票號碼結束值 |
| 客戶代碼起 | 9,30 | - | A | B | 客戶代碼起始值 |
| 客戶代碼迄 | 9,42 | - | A | B | 客戶代碼結束值 |
| 發票類型 | 11,30 | 1 | A | B | 發票類型選擇 |
| 列印格式 | 13,30 | 1 | A | B | 列印格式選擇 |

## 5. 明細畫面

此為轉帳/寄賣發票列印的參數設定畫面，支援套表格式列印。

## 6. 功能鍵說明

| 功能鍵 | 說明 |
|--------|------|
| F3 | 回到前頁 |
| F12 | 執行列印 |

## 7. 輸入欄位驗證

### 日期欄位驗證
- 格式：MM/DD/YY
- 起始日期不得大於結束日期

### 發票號碼驗證
- 必須為有效的發票號碼格式
- 起始值不得大於結束值

### 客戶代碼驗證
- 參考客戶主檔
- 起始值不得大於結束值

### 發票類型驗證
- 有效值：1=轉帳, 2=寄賣, 3=全部

### 列印格式驗證
- 有效值：1=套表格式

## 8. 錯誤處理

標準錯誤處理機制。

## 9. 使用說明

### 操作流程
1. 設定發票日期範圍
2. 設定發票號碼範圍（可選）
3. 設定客戶範圍（可選）
4. 選擇發票類型
5. 選擇列印格式
6. 按F12執行列印

### 相關程式
- **主程式**: ARR054
- **系統**: 應收帳款系統
- **功能**: 轉帳／寄賣發票列印設定 