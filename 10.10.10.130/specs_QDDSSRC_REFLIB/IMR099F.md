# IMR099F 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | IMR099F |
| 檔案類型 | 實體檔案 (Physical File) |
| 檔案用途 | 派車明細檔，供物流使用 |
| 紀錄格式 | IMR99 |
| 主鍵欄位 | SE02 |
| 排序方式 | 升序 |
| 參照檔案 | RERF |

## 2. 檔案功能說明

IMR099F是專門供物流使用的派車明細檔案：

1. **主要功能**：記錄派車明細資訊供物流系統使用
2. **資料內容**：包含出貨單號、產品資訊、數量、地址等派車相關資料
3. **系統用途**：支援物流派車作業和配送管理
4. **索引設計**：以出貨單號為主鍵進行資料管理
5. **物流整合**：與物流系統進行資料交換

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| IMR099F | 實體檔案 | 派車明細檔（主檔案） |
| RERF | 參考檔案 | 參考欄位定義檔 |

## 4. 紀錄格式

| 格式名稱 | 說明 |
|----------|------|
| IMR99 | 派車明細主記錄格式 |

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| WSE06 | 出貨日期 | 1 | 8 | 數值 | - | 出貨日期 |
| SE22 | 客戶代號 | 2 | - | 字元 | 參考SE22 | 客戶代號 |
| SE101 | 倉庫代號 | 3 | - | 字元 | 參考SE10 | 倉庫代號 |
| SE11 | 單據代號 | 4 | - | 字元 | 參考SE11 | 單據代號 |
| SE02 | 出貨單號 | 5 | - | 字元 | 參考SE02/主鍵 | 出貨單號 |
| WSF045 | 出貨數量 | 6 | 5 | 數值 | - | 出貨數量 |
| SF03 | 產品代號 | 7 | - | 字元 | 參考SF03 | 產品代號 |
| PME042 | 倉庫名稱 | 8 | - | 字元 | 參考ME04 | 倉庫名稱 |
| MA03 | 產品名稱含規格 | 9 | - | 字元 | 參考MA03 | 產品名稱含規格 |
| MA13 | 保存期 | 10 | - | 字元 | 參考MA13 | 保存期 |
| PME052 | 出貨地址一 | 11 | 32 | 字元 | 輸出 | 出貨地址一 |
| PME062 | 出貨地址二 | 12 | 32 | 字元 | 輸出 | 出貨地址二 |
| SE12 | 數量欄一 | 13 | - | 數值 | 參考SE12 | 數量欄一 |
| SE13 | 數量欄二 | 14 | - | 數值 | 參考SE13 | 數量欄二 |
| SE14 | 數量欄三 | 15 | - | 數值 | 參考SE14 | 數量欄三 |

## 6. 主鍵欄位

本實體檔案的主鍵欄位為：
- SE02（出貨單號）

### 主鍵特性：
- **SE02（出貨單號）**：唯一識別每筆派車明細記錄

## 7. 索引資料

| 索引名稱 | 索引鍵 | 排序 | 用途說明 |
|----------|--------|------|----------|
| 主索引 | SE02 | 升序 | 出貨單號查詢 |

### 索引特性：
- **單一索引**：以出貨單號作為主要存取路徑
- **唯一性**：確保出貨單號的唯一性
- **查詢效率**：提供快速的出貨單號查詢

## 8. 備註

1. **物流專用檔案**：專門供物流系統使用的派車明細檔案
2. **參考欄位設計**：
   - 使用REF(RERF)參考檔案定義
   - SE22參考客戶檔案
   - SE101參考倉庫檔案（REFFLD(SE10)）
   - SE11參考單據檔案
   - SE02參考出貨單檔案
   - SF03參考產品檔案
   - PME042參考倉庫名稱（REFFLD(ME04)）
   - MA03參考產品名稱檔案
   - MA13參考保存期檔案
3. **地址管理**：
   - PME052和PME062提供完整的出貨地址資訊
   - 支援32字元的地址描述
   - 分為兩行地址顯示
4. **數量管理**：
   - WSF045記錄主要出貨數量
   - SE12、SE13、SE14提供額外的數量欄位
   - 支援多種數量統計需求
5. **日期管理**：
   - WSE06記錄出貨日期
   - 8位數值格式（YYYYMMDD）
6. **產品資訊**：
   - SF03記錄產品代號
   - MA03記錄完整產品名稱含規格
   - MA13記錄保存期資訊
7. **倉庫資訊**：
   - SE101記錄倉庫代號
   - PME042記錄倉庫名稱
   - 支援多倉庫管理
8. **客戶資訊**：
   - SE22記錄客戶代號
   - 與客戶檔案關聯
9. **單據管理**：
   - SE11記錄單據代號
   - SE02記錄出貨單號
   - 支援單據追蹤
10. **系統整合**：
    - 與物流系統進行資料交換
    - 支援派車作業流程
    - 提供配送管理基礎資料
11. **資料結構**：
    - 15個欄位，涵蓋派車所需完整資訊
    - 支援物流作業各種需求
    - 提供彈性的數量和地址管理
12. **業務應用**：
    - 派車單列印
    - 配送路線規劃
    - 物流績效統計
    - 出貨追蹤管理 