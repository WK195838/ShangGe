# REWF85 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF85 |
| 檔案名稱 | 建議產品採購表 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存建議產品採購表資料，記錄產品採購建議的詳細資訊，包含產品代號、預估目前庫存量、出廠流程公價量、建議在庫量、產品規格等採購分析資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF85 | PF | 建議產品採購表主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF850

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF8501 | 產品代號 | 1 | | A | | MA01 | |
| 2 | WF8502 | 預估目前庫存量 | | 6 | N | 0 | | |
| 3 | WF8503 | 出廠流程公價量 | | 8 | N | 0 | | |
| 4 | WF8504 | 建議在庫量 | | 8 | N | 0 | | |
| 5 | WF8505 | 產品規格 | | | A | | MA03 | |

## 6. 主鍵欄位

單一主鍵：
1. WF8501 (產品代號)

## 7. 索引資料

主要索引以產品代號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示KEY=（未完整顯示）
- 提供產品採購建議的分析功能
- 支援庫存量預估和建議計算
- 整合出廠流程的公價量分析
- 包含產品規格的完整資訊
- 協助採購決策的數據分析 