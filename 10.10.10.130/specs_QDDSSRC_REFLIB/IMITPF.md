# IMITPF 資料庫檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | IMITPF |
| 檔案類型 | PF (實體檔案) |
| 檔案說明 | 盤點備份主檔－庫存＆成本 |
| 唯一性 | UNIQUE |
| 參考檔案 | RERF |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |

## 2. 檔案功能說明

IMITPF 是盤點備份主檔的實體檔案，用於儲存盤點期間的庫存數量和成本資料備份。具有 UNIQUE 屬性，確保每個產品在每個倉庫的唯一性，支援盤點作業的資料完整性管理。

## 3. 系統檔案清單

核心實體檔案，作為 IMITLF01 等邏輯檔案的基礎資料來源。

## 4. 記錄格式

IT0 記錄格式，包含完整的庫存備份資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

| 欄位代號 | 欄位名稱 | 資料類型 | 長度 | 小數位 | 說明 |
|----------|----------|----------|------|--------|------|
| IT01 | 庫存類別 | REF | - | - | 庫存分類識別 |
| IT02 | 倉庫項次代號 | REF | - | - | 倉庫識別 |
| IT03 | 商品代號 | REF | - | - | 產品識別 |
| IT04 | 商品名稱 | REF | - | - | 產品名稱 |
| IT05 | 商品規格 | REF | - | - | 產品規格 |
| IT06 | 庫存數量 | REF | - | - | 備份庫存數量 |
| IT07 | 期初數量 | REF | - | - | 期初庫存 |
| IT08 | 進貨數量 | REF | - | - | 進貨總量 |
| IT09 | 保留數量 | REF | - | - | 保留庫存 |
| IT10 | 可用數量 | REF | - | - | 可用庫存 |
| ITXX | 異動日期 | NUMERIC | 8 | 0 | 最後異動日期 |
| ITYY | 異動時間 | REF | - | - | 異動時間 |
| ITZZ | 異動者 | REF | - | - | 異動人員 |

## 6. 主鍵欄位

三層主鍵結構：
1. IT01 - 庫存類別
2. IT02 - 倉庫項次代號  
3. IT03 - 商品代號

## 7. 索引資料

### 主索引
- **排序方式**: IT01 + IT02 + IT03
- **唯一性**: UNIQUE 約束確保每個組合的唯一性

## 8. 備註

1. **盤點備份**: 專用於盤點期間的資料備份
2. **唯一性約束**: UNIQUE 屬性確保資料完整性
3. **參考檔案**: 使用 RERF 作為欄位參考
4. **完整記錄**: 包含庫存數量、成本、異動追蹤等完整資訊
5. **三層主鍵**: 支援多倉庫、多類別的庫存管理
6. **審計追蹤**: 包含異動日期、時間、人員等審計資訊
