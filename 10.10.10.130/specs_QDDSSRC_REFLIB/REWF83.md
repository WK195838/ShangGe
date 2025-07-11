# REWF83 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF83 |
| 檔案名稱 | 銷退主檔明細 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存銷退主檔明細資料，記錄銷售退貨的詳細資訊，包含流水號、客戶代號、流水代號、出貨日期、折讓通路、應收金額、產品代號、數量、公價、稅率、金額等完整的銷退管理資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF83 | PF | 銷退主檔明細主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF830

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF8301 | 流水號 | 1 | | A | | SG01 | |
| 2 | WF8302 | 客戶代號 | | | A | | SG04 | |
| 3 | WF8303 | 流水代號 | | | A | | SG05 | |
| 4 | WF8304 | 出貨日期 | | 8 | N | B2CHK | SG26 | 檢查欄位(B2CHK) |
| 5 | WF8305 | 折讓通路 | | | A | | SG09 | |
| 6 | WF8306 | 應收金額 | | | A | | AC10 | |
| 7 | WF8307 | 產品代號 | | | A | | SH03 | |
| 8 | WF8308 | 數量／已確認 | | | A | | SH04 | |
| 9 | WF8309 | 公價／已確認 | | | A | | SD05 | |
| 10 | WF8310 | 稅率 | | | A | | AG06 | |
| 11 | WF8311 | 金額 | | | A | | SH07 | |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF8301 (流水號)
2. WF8302 (客戶代號)
3. WF8304 (出貨日期)
4. WF8305 (折讓通路)
5. WF8307 (產品代號)

## 7. 索引資料

主要索引以流水號、客戶代號、出貨日期、折讓通路、產品代號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 支援B2CHK檢查功能
- 提供銷售退貨的詳細記錄和管理
- 包含數量和公價的已確認狀態追蹤
- 整合折讓通路和應收金額的管理
- 支援稅率和金額的計算功能
- 提供完整的銷退流程追蹤 