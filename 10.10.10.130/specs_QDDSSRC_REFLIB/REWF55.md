# REWF55 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF55 |
| 檔案名稱 | 客戶銷售明細表 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存客戶銷售明細表資料，記錄客戶銷售的詳細資訊，包含通路、地區、客戶、產品、數量、金額等完整銷售資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF55 | PF | 客戶銷售明細表主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF550

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF5501 | 流水號 | 1 | | A | | SC01 | |
| 2 | WF5502 | 通路 | | | A | | SC33 | |
| 3 | WF5503 | 地區 | | | A | | SC34 | |
| 4 | WF5504 | 地區 | | | A | | SC04 | |
| 5 | WF5505 | 通路 | | | A | | SC05 | |
| 6 | WF5506 | 產品代號 | | | A | | SD03 | |
| 7 | WF5507 | 訂單日期 | | 8 | N | B2CHK | SC07 | 檢查欄位(B2CHK) |
| 8 | WF5508 | 訂單編號 | | | A | | SC02 | |
| 9 | WF5509 | 訂單數 | | | N | | SD04 | |
| 10 | WF5510 | 公價數 | | | N | | SD05 | |
| 11 | WF5511 | 促銷 | | | N | | SD06 | |
| 12 | WF5512 | 金額 | | | N | | SD07 | |
| 13 | WF5513 | 業務員 | | | A | | SC27 | |
| 14 | WF5514 | 確認日期 | | 8 | N | B2CHK | SC07 | 檢查欄位(B2CHK) |
| 15 | WF5515 | 促銷數 | | | N | | SD04 | |
| 16 | WF5516 | 出貨日期 | | 8 | N | B2CHK | SC08 | 檢查欄位(B2CHK) |
| 17 | WF5517 | 出貨地區庫存點 | | | A | | SC16 | 新增欄位(00A) |
| 18 | WF5518 | 出貨地區客戶日期 | | | A | | SC17 | 新增欄位(00A) |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF5502 (通路)
2. WF5503 (地區)
3. WF5504 (地區)
4. WF5505 (通路)
5. WF5506 (產品代號)
6. WF5516 (出貨日期)
7. WF5508 (訂單編號)

## 7. 索引資料

主要索引以通路、地區、產品代號、出貨日期、訂單編號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 支援B2CHK檢查功能
- 00A修改：需求單號1070387，新增出貨地區庫存點和出貨地區客戶日期欄位
- 包含訂單和出貨的完整客戶銷售資訊
- 支援公價數和促銷數分別統計 