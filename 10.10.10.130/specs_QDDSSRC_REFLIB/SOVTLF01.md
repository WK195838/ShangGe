# SOVTLF01 檔案規格書

## 1. 基本資料

| 欄位 | 內容 |
|------|------|
| 檔案名稱 | SOVTLF01 |
| 檔案描述 | 媒體申報檔邏輯檔 |
| 檔案類型 | 邏輯檔案 (LF) |
| 記錄格式 | VT0 |
| 關鍵字 | VT03 |
| 實體檔案 | SOVTPF |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |
| 存取方式 | 索引存取 |

## 2. 檔案功能說明

媒體申報檔邏輯檔提供按序號排序的媒體申報資料存取功能。本邏輯檔主要用於按序號順序進行媒體申報資料的查詢與處理，支援申報資料的有序存取與管理。

## 3. 系統檔案清單

| 相關檔案 | 檔案名稱 | 說明 |
|----------|----------|------|
| 邏輯檔案 | SOVTLF01 | 媒體申報檔邏輯檔 |
| 實體檔案 | SOVTPF | 媒體申報檔 |
| 工作檔 | SOVQPF | 媒體申報工作檔 |

## 4. 紀錄格式

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| VT03 | 序號 | 1-7 | 7 | 文字 | 索引1 | 申報資料序號 |

## 5. 主鍵欄位

- **排序鍵**：VT03 (序號)
- **索引類型**：單一索引
- **排序方式**：遞增排序

## 6. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| PRIMARY | VT03 | LOGICAL | 序號索引 |

## 7. 使用說明

1. **序號查詢**：按申報資料序號進行查詢
2. **有序存取**：提供按序號排序的申報資料存取
3. **快速定位**：支援按序號的快速資料定位
4. **申報處理**：支援媒體申報的有序處理作業
5. **資料瀏覽**：提供申報資料的循序瀏覽功能

## 8. 備註

- 邏輯檔案基於SOVTPF實體檔案建立
- 簡單的單一索引設計，提供高效能的序號存取
- 支援媒體申報系統的資料定位與瀏覽需求
- 與其他媒體申報檔案配合使用，提供完整的資料存取功能
- 適用於需要按序號排序的申報作業處理 