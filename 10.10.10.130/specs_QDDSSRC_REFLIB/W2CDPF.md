# W2CDPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | W2CDPF |
| 檔案類型 | 實體檔 (PF) |
| 檔案描述 | 茂世產品匯總表暫存檔 |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |

## 2. 檔案功能說明

此檔案為茂世產品匯總報表的簡化暫存檔，負責暫存茂世產品的基本匯總資料。主要功能：
- 暫存茂世產品的簡化匯總統計
- 提供產品基本匯總功能
- 支援產品數量及週期的統計分析
- 管理產品的基本統計資料
- 提供簡化的產品匯總暫存機制

## 3. 系統檔案清單

| 項目 | 檔案名稱 | 類型 | 說明 |
|------|----------|------|------|
| 主檔 | W2CDPF | PF | 茂世產品匯總表暫存檔 |
| 關聯檔 | W2CAPF | PF | 茂世產品匯總表暫存檔(詳細版) |

## 4. 紀錄格式

### 記錄格式：CD0
**唯一性約束：UNIQUE**

| 欄位代號 | 欄位名稱 | 型態 | 長度 | 小數 | 說明 |
|----------|----------|------|------|------|------|
| CD01 | 產品代號 | A | 9 | 0 | 產品代號 |
| CD02 | 產品名稱 | O | 18 | 0 | 產品名稱 |
| CD03 | 數量 | S | 8 | 0 | 匯總數量 |
| CD04 | 週期編號 | S | 8 | 0 | 統計週期編號 |

## 5. 主鍵欄位

| 順序 | 欄位代號 | 欄位名稱 | 排序方式 |
|------|----------|----------|----------|
| 1 | CD01 | 產品代號 | 遞增 |

## 6. 索引資料

### 索引鍵值
- **主索引**：CD01
- **唯一性約束**：UNIQUE
- **排序方式**：產品代號遞增

### 存取路徑
此檔案提供以下存取路徑：
1. 依產品代號直接檢索
2. 支援產品基本統計分析
3. 提供簡化的產品匯總檢索

### 與W2CAPF差異
- **結構簡化**：移除專櫃相關欄位
- **主鍵簡化**：僅以產品代號為主鍵
- **分析簡化**：專注於產品層級的基本統計
- **資料精簡**：提供最基本的產品匯總資料

## 7. 使用說明

### 查詢功能
- 支援依產品代號直接查詢
- 提供產品基本統計檢索
- 支援產品數量匯總分析
- 支援週期性統計查詢

### 作業程序
1. 從基礎交易資料彙整產品基本統計
2. 按產品代號分組匯總
3. 記錄匯總數量及週期資訊
4. 提供簡化報表的資料來源
5. 定期更新匯總統計資料

### 維護作業
- **新增**：建立新的產品匯總記錄
- **查詢**：支援產品基本檢索
- **更新**：更新匯總數量及週期資料
- **刪除**：清理過期匯總資料
- **彙總**：產生產品基本統計報表

### 注意事項
- 此為暫存檔，資料具有時效性
- 檔案具有UNIQUE約束，確保產品唯一性
- 單一主鍵設計，提供簡化檢索
- 專注於產品層級的基本統計

## 8. 備註

- 此檔案為茂世產品匯總分析的簡化暫存檔案
- 單一主鍵確保產品記錄唯一性
- 提供產品層級的基本統計功能
- 與W2CAPF提供不同詳細程度的分析
- 產品名稱採用開放長度格式
- 支援簡化報表系統的資料準備 