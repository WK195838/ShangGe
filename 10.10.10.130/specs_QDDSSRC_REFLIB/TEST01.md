# TEST01 檔案規格書

## 1. 基本資料

| 欄位 | 內容 |
|------|------|
| 檔案名稱 | TEST01 |
| 檔案描述 | TEST FOR 銷售訂單明細檔 |
| 檔案類型 | 邏輯檔案 (LF) |
| 記錄格式 | SD0 |
| 關鍵字 | SD02+SD03 |
| 實體檔案 | SOSDPF + SOSCPF (JOIN) |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |
| 存取方式 | JOIN存取 |

## 2. 檔案功能說明

TEST01是基於銷貨收入明細檔(SOSDPF)與銷貨收入客戶檔(SOSCPF)建立的JOIN測試檔案。本檔案主要用於測試銷售訂單明細資料的查詢與處理功能，透過JOIN操作整合客戶與銷售明細資訊，支援銷售業務的測試與驗證需求。

## 3. 系統檔案清單

| 相關檔案 | 檔案名稱 | 說明 |
|----------|----------|------|
| 測試檔案 | TEST01 | 銷售訂單明細測試檔 |
| 明細檔案 | SOSDPF | 銷貨收入明細檔 |
| 客戶檔案 | SOSCPF | 銷貨收入客戶檔 |

## 4. 紀錄格式

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| SD01 | 期數編號 | 1-2 | 2 | 文字 | - | 期數編號 |
| SD02 | 單據統編 | 3-14 | 12 | 文字 | 索引1,JOIN | 單據統一編號 |
| SD03 | 產品編號 | 15-19 | 5 | 文字 | 索引2 | 產品編號 |
| SD04 | 訂貨數量 | 20-25 | 6,0 | 數值 | - | 訂貨數量 |
| SD05 | 實現數量 | 26-31 | 6,0 | 數值 | - | 實現數量 |
| SD10 | 進口單價-FOB | 32-42 | 11,2 | 數值 | - | FOB進口單價 |
| SD11 | 進口單價-FHI | 43-53 | 11,2 | 數值 | - | FHI進口單價 |
| SD12 | 進口單價-DUTY | 54-64 | 11,2 | 數值 | - | 關稅進口單價 |
| SDXX | 建立日期 | 65-72 | 8,0 | 數值 | - | 記錄建立日期 |
| SDYY | 建立時間 | 73-78 | 6,0 | 數值 | - | 記錄建立時間 |
| SC02 | 單據統編 | 79-90 | 12 | 文字 | JOIN | 客戶檔單據統編 |
| SC03 | 編號 | 91-93 | 3 | 文字 | 選擇 | 編號(='S2') |
| SC13 | 單據狀態 | 94-94 | 1 | 文字 | 選擇 | 單據狀態(≠'*') |
| SC39 | 確認日期 | 95-102 | 8,0 | 數值 | - | 確認日期 |

## 5. 主鍵欄位

- **排序鍵**：SD02+SD03 (單據統編+產品編號)
- **索引類型**：複合索引
- **排序方式**：遞增排序
- **JOIN條件**：SD02 = SC02
- **選擇條件**：SC03 = 'S2' AND SC13 ≠ '*'

## 6. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| PRIMARY | SD02+SD03 | LOGICAL | 單據產品複合索引 |

## 7. 使用說明

1. **測試功能**：用於測試銷售訂單明細檔的JOIN查詢功能
2. **資料整合**：整合銷售明細與客戶資料
3. **狀態篩選**：自動篩選SC03='S2'且SC13≠'*'的記錄
4. **進口價格**：支援FOB、FHI、DUTY三種進口單價查詢
5. **數量統計**：提供訂貨與實現數量的對比分析

## 8. 備註

- 使用JDFTVAL與DYNSLT屬性提升JOIN效能
- JOIN條件：SOSDPF.SD02 = SOSCPF.SC02
- 選擇條件限制SC03為'S2'，SC13不為'*'
- 支援多種進口單價類型(FOB/FHI/DUTY)
- 包含完整的建立軌跡資訊(日期/時間)
- 作為測試檔案，主要用於功能驗證與資料分析 