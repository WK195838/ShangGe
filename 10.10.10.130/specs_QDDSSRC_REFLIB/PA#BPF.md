# PA#BPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | PA#BPF |
| 檔案類型 | 實體檔案 (Physical File) |
| 檔案用途 | 公司檔 |
| 紀錄格式 | #B0 |
| 主鍵欄位 | #B01 |
| 排序方式 | 升序 |
| 參照檔案 | RERF |
| 特殊屬性 | UNIQUE |

## 2. 檔案功能說明

PA#BPF是公司基本資料的主檔案：

1. **主要功能**：儲存公司完整的基本資料和聯絡資訊
2. **資料內容**：包含公司代號、名稱、地址、聯絡方式等完整資訊
3. **系統用途**：作為公司管理和業務處理的基礎檔案
4. **索引設計**：以公司代號為唯一主鍵
5. **組織管理**：支援多公司架構的管理需求

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| PA#BPF | 實體檔案 | 公司檔（主檔案） |
| RERF | 參考檔案 | 參考欄位定義檔 |

## 4. 紀錄格式

| 格式名稱 | 說明 |
|----------|------|
| #B0 | 公司基本資料主記錄格式 |

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| #B01 | 公司代號 | 1 | - | 字元 | 參考#B01/主鍵 | 公司代號 |
| #B02 | 公司名稱 | 2 | - | 字元 | 參考#B02 | 公司名稱 |
| #B03 | 公司名稱 | 3 | - | 字元 | 參考#B03 | 公司名稱 |
| #B04 | 公司地址一 | 4 | - | 字元 | 參考#B04 | 公司地址一 |
| #B05 | 公司地址二 | 5 | - | 字元 | 參考#B05 | 公司地址二 |
| #B06 | 公司類型 | 6 | - | 字元 | 參考#B06 | 公司類型（A-直營店，W-試飲店） |
| #B07 | 負責人 | 7 | - | 字元 | 參考#B07 | 負責人 |
| #B08 | 公司電話一 | 8 | - | 字元 | 參考#B08 | 公司電話一 |
| #B09 | 公司電話二 | 9 | - | 字元 | 參考#B09 | 公司電話二 |
| #B10 | 傳真機 | 10 | - | 字元 | 參考#B10 | 傳真機 |
| #B11 | 郵遞區號 | 11 | - | 字元 | 參考#B11 | 郵遞區號 |
| #B12 | 統一編號 | 12 | - | 字元 | 參考#B12 | 統一編號 |
| #B13 | 營業編號 | 13 | - | 字元 | 參考#B13 | 營業編號 |
| #B14 | 倉庫代號 | 14 | - | 字元 | 參考#B14 | 倉庫代號 |
| #B15 | 單據代號 | 15 | - | 字元 | 參考#B15 | 單據代號 |
| #B16 | 營業開始 | 16 | 6 | 數值 | B2CHKA | 營業開始日期 |
| #B17 | 發票最大號 | 17 | - | 字元 | 參考#B17 | 發票最大號（儲存發票的最大號碼） |
| #BXX | 異動日期 | 18 | 8 | 數值 | B2CHKA | 異動日期 |
| #BYY | 異動時間 | 19 | - | 字元 | 參考#BYY | 異動時間 |
| #BZZ | 異動操作者 | 20 | - | 字元 | 參考#BZZ | 異動操作者 |

## 6. 主鍵欄位

本實體檔案的主鍵欄位為：
- #B01（公司代號）

### 主鍵特性：
- **#B01（公司代號）**：唯一識別每家公司
- **UNIQUE屬性**：確保公司代號的唯一性

## 7. 索引資料

| 索引名稱 | 索引鍵 | 排序 | 用途說明 |
|----------|--------|------|----------|
| 主索引 | #B01 | 升序 | 公司代號查詢 |

### 索引特性：
- **唯一索引**：確保公司代號的唯一性
- **主要存取路徑**：所有公司查詢的基礎
- **系統整合**：與其他檔案的關聯基礎

## 8. 備註

1. **公司管理核心**：多公司架構管理的基礎檔案
2. **完整聯絡資訊**：
   - #B02、#B03：公司名稱（可能分為兩欄）
   - #B04、#B05：完整的公司地址資訊
   - #B08、#B09：多個聯絡電話
   - #B10：傳真機號碼
   - #B11：郵遞區號
3. **公司分類管理**：
   - #B06：公司類型（A-直營店，W-試飲店）
   - 支援不同類型公司的管理
4. **法定資訊**：
   - #B12：統一編號
   - #B13：營業編號
   - #B07：負責人
   - 符合法規要求的基本資訊
5. **營運資訊**：
   - #B14：倉庫代號（關聯倉庫管理）
   - #B15：單據代號（關聯單據管理）
   - #B16：營業開始日期（6位數值，B2CHKA檢核）
   - #B17：發票最大號（發票號碼管理）
6. **異動追蹤**：
   - #BXX：異動日期（8位數值，B2CHKA檢核）
   - #BYY：異動時間
   - #BZZ：異動操作者
   - 完整的異動記錄機制
7. **參考欄位設計**：
   - 使用REF(RERF)參考檔案定義
   - 所有欄位都有對應的參考定義
   - 確保資料一致性和完整性
8. **業務應用**：
   - 公司基本資料維護
   - 多公司架構管理
   - 發票管理
   - 營業登記管理
   - 聯絡資訊管理
9. **系統整合**：
   - 與倉庫檔案關聯（#B14）
   - 與單據檔案關聯（#B15）
   - 支援多公司業務處理
10. **資料完整性**：
    - UNIQUE主鍵約束
    - 參考完整性檢核
    - 日期格式檢核（B2CHKA）
11. **發票管理**：
    - #B17記錄發票最大號
    - 支援發票號碼的序號管理
    - 確保發票號碼不重複
12. **營業管理**：
    - #B16記錄營業開始日期
    - 支援營業期間的計算
    - 營業歷史追蹤
13. **地址管理**：
    - 分為兩行地址（#B04、#B05）
    - 配合郵遞區號（#B11）
    - 完整的地址資訊管理
14. **聯絡管理**：
    - 多個電話號碼（#B08、#B09）
    - 傳真號碼（#B10）
    - 負責人資訊（#B07）
15. **組織架構**：
    - 支援集團公司管理
    - 不同類型公司的分類
    - 階層式組織管理 