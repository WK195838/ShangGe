# MTMALF1 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | MTMALF1 |
| 檔案名稱 | 產品基本資料檔 |
| 檔案類型 | LF (邏輯檔案) |
| 資料庫 | REFLIB |
| 記錄格式 | MA0L |
| 主鍵 | MA01L |
| 參照檔案 | MTMAPF |
| 建立日期 | - |
| 最後異動日期 | - |

## 2. 檔案功能說明

本檔案為產品基本資料檔的邏輯檔案，使用重新命名的欄位(MA01L, MA15L)，以產品編號為主鍵排序，提供產品編號及容量欄的查詢功能。

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| MTMALF1 | LF | 產品基本資料邏輯檔 |
| MTMAPF | PF | 產品基本資料實體檔 |

## 4. 紀錄格式

**記錄格式名稱：** MA0L

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|----------|
| MA01L | 產品代號 | - | - | R | Key | 重新命名MA01 |
| MA15L | 容量欄 | - | - | R | - | 重新命名MA15 |

## 6. 主鍵欄位

**主鍵組成：** MA01L
- MA01L：產品代號 (重新命名自MA01)

## 7. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| 主索引 | MA01L | - | 按產品代號排序 |

## 8. 備註

1. 本檔案為產品基本資料檔的邏輯檔案
2. 使用PFILE參照MTMAPF實體檔案
3. 使用RENAME重新命名欄位
4. MA01L重新命名自MA01(產品代號)
5. MA15L重新命名自MA15(容量欄)
6. 記錄格式為MA0L而非標準的MA0
7. 提供特定欄位重新命名的查詢介面 