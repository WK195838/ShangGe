# REWF871 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF871 |
| 檔案名稱 | 產品銷售分析週報－依辦事處 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存產品銷售分析週報－依辦事處資料，在REWF87基礎功能上新增辦事處維度，提供按辦事處分類的產品銷售週期性分析功能，記錄年月、產品出廠編號、產品代號、本週與上週的訂單和公價數量、產品與去年的訂單和公價數量，以及辦事處資訊等完整的週報統計資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF871 | PF | 產品銷售分析週報－依辦事處主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF870

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF8701 | 年月 | 1 | | A | | MA10 | |
| 2 | WF8702 | 產品出廠編號 | | 6 | A | | | |
| 3 | WF8703 | 產品 | | | A | | MA01 | |
| 4 | WF8704 | 本週訂單數 | | 13 | N | 2 | | 2位小數 |
| 5 | WF8705 | 本週公價數 | | 13 | N | 2 | | 2位小數 |
| 6 | WF8706 | 上週訂單數 | | 13 | N | 2 | | 2位小數 |
| 7 | WF8707 | 上週公價數 | | 13 | N | 2 | | 2位小數 |
| 8 | WF8708 | 產品訂單數 | | 13 | N | 2 | | 2位小數 |
| 9 | WF8709 | 產品公價數 | | 13 | N | 2 | | 2位小數 |
| 10 | WF8710 | 去年訂單數 | | 13 | N | 2 | | 2位小數 |
| 11 | WF8711 | 去年公價數 | | 13 | N | 2 | | 2位小數 |
| 12 | WF8712 | 辦事處 | | 1 | A | | | |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF8712 (辦事處)
2. WF8701 (年月)
3. WF8702 (產品出廠編號)
4. WF8703 (產品)

## 7. 索引資料

主要索引以辦事處、年月、產品出廠編號、產品為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示KEY=（未完整顯示）
- 在REWF87基礎上新增辦事處維度分析
- 提供按辦事處分類的產品銷售週期性分析
- 支援本週、上週、去年的比較分析
- 所有數量欄位均支援2位小數精度
- 包含訂單數和公價數的雙重統計
- 協助各辦事處產品銷售績效的比較分析
- 支援分區域的產品銷售管理報表
- 辦事處欄位採用1位字元編碼 