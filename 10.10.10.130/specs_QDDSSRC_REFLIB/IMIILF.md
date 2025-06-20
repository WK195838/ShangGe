# IMIILF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | IMIILF |
| 檔案名稱 | 存貨調撥主檔 |
| 檔案類型 | LF (邏輯檔案) |
| 資料庫 | REFLIB |
| 記錄格式 | II0 |
| 基礎實體檔案 | IMIIPF |

## 2. 檔案功能說明

此邏輯檔案基於 IMIIPF（存貨調撥主檔實體檔案），提供存貨調撥作業的邏輯存取路徑。主要用於存貨調撥作業的資料查詢和處理，支援產品代號的排序存取，方便進行存貨調撥相關的作業處理。

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|----------|------|
| IMIILF | 存貨調撥主檔 | LF | 邏輯檔案 |
| IMIIPF | 存貨調撥主檔 | PF | 基礎實體檔案 |

## 4. 紀錄格式

### 記錄格式：II0
- **基於實體檔案**：IMIIPF
- **存取方式**：REFACCPTH (參照存取路徑)

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| II01 | 單據編號或出貨 | - | - | - | R | 參照 RERF，單據編號或出貨編號 |
| II02 | 產品代號 | - | - | - | R | 參照 RERF，產品代號 |
| II03 | 出貨產品項次代號 | - | - | - | R | 參照 RERF，出貨產品項次代號 |
| II04 | 入貨產品項次代號 | - | - | - | R | 參照 RERF，入貨產品項次代號 |
| II05 | 調撥日期 | - | 8 | 數值 | R | 調撥日期 (YYYYMMDD 格式) |
| II06 | 產品入庫日期 | - | 8 | 數值 | R | 產品入庫日期 (YYYYMMDD 格式) |
| II07 | 確認狀態 | - | - | - | R | 參照 RERF，確認狀態 |
| II08 | 庫存狀態 | - | - | - | R | 參照 RERF，庫存狀態 |
| II09 | 單據編號或收貨 | - | - | - | R | 參照 RERF，單據編號或收貨編號 |
| IIXX | 建立日期 | - | 8 | 數值 | R | 建立日期 (YYYYMMDD 格式) |
| IIYY | 建立時間 | - | - | - | R | 參照 RERF，建立時間 |
| IIZZ | 建立人員 | - | - | - | R | 參照 RERF，建立人員 |

## 6. 主鍵欄位

| 主鍵順序 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | II02 | 產品代號 | ASC |

## 7. 索引資料

### 主要索引
- **索引鍵值**：II02 (產品代號)
- **索引類型**：繼承自基礎實體檔案 IMIIPF
- **排序方式**：遞增排序
- **存取方式**：REFACCPTH (參照存取路徑)

## 8. 備註

1. 此檔案為邏輯檔案，基於 IMIIPF 實體檔案
2. 使用 REFACCPTH 參照存取路徑，提供與實體檔案相同的存取介面
3. 所有欄位定義均繼承自基礎實體檔案 IMIIPF
4. 支援存貨調撥作業的基本查詢功能
5. 產品代號編碼格式：XX-XX-X-XX-XXXXX (單位-類別-系列人-規格異動-序號)
6. 日期欄位採用 YYYYMMDD 格式儲存
7. 此檔案提供存貨調撥主檔的標準邏輯存取路徑 