# REWF82 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF82 |
| 檔案名稱 | 產品存量分佈明細表 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存產品存量分佈明細表資料，記錄各產品在不同倉庫的存量分佈狀況，包含產品編號及各倉庫（T0001、W0005、W0001、W0004、W0002、W0003）的已存量和可存量等存量管理資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF82 | PF | 產品存量分佈明細表主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF820

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF8201 | 產品 | 1 | | A | | MA01 | |
| 2 | WF8202 | 已存量T0001 | | | A | | MA29 | |
| 3 | WF8203 | 可存量T0001 | | | A | | MA29 | |
| 4 | WF8204 | 已存量W0005 | | | A | | MA29 | |
| 5 | WF8205 | 可存量W0005 | | | A | | MA29 | |
| 6 | WF8206 | 已存量W0001 | | | A | | MA29 | |
| 7 | WF8207 | 可存量W0001 | | | A | | MA29 | |
| 8 | WF8208 | 已存量W0004 | | | A | | MA29 | |
| 9 | WF8209 | 可存量W0004 | | | A | | MA29 | |
| 10 | WF8210 | 已存量W0002 | | | A | | MA29 | |
| 11 | WF8211 | 可存量W0002 | | | A | | MA29 | |
| 12 | WF8212 | 已存量W0003 | | | A | | MA29 | |
| 13 | WF8213 | 可存量W0003 | | | A | | MA29 | |

## 6. 主鍵欄位

單一主鍵：
1. WF8201 (產品)

## 7. 索引資料

主要索引以產品編號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示KEY=（未完整顯示）
- 提供產品存量分佈的完整管理
- 支援6個不同倉庫的存量管理（T0001、W0005、W0001、W0004、W0002、W0003）
- 每個倉庫區分已存量和可存量兩種狀態
- 所有存量欄位均參考MA29欄位定義
- 提供跨倉庫的產品存量分析功能 