# REWF76 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF76 |
| 檔案名稱 | 收款明細表 |
| 檔案類型 | PF (實體檔案) |
| 參考說明 | SOSIPF |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存收款明細表資料，記錄收款的詳細資訊，包含流水號、業務員、發票客戶代號、發票客戶名稱、收款日期、出貨日期、發票編號、辦事處等完整的收款管理資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF76 | PF | 收款明細表（參考SOSIPF） |

## 4. 紀錄格式

### 主紀錄格式：WF760

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF7601 | 流水號 | 1 | | A | | SI01 | |
| 2 | WF7602 | 業務員 | | | A | | SI31 | |
| 3 | WF7603 | 發票客戶代號名稱 | | | A | | SI12 | |
| 4 | WF7604 | 發票客戶名稱／名稱 | | | A | | SI13 | |
| 5 | WF7605 | 收款日期 | | 8 | N | B2CHK | SI06 | 檢查欄位(B2CHK) |
| 6 | WF7606 | 出貨日期 | | 8 | N | B2CHK | SI21 | 檢查欄位(B2CHK) |
| 7 | WF7607 | 發票編號 | | | A | | SI02 | |
| 8 | WF7608 | 辦事處 | | | A | | SI25 | |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF7601 (流水號)
2. WF7602 (業務員)
3. WF7603 (發票客戶代號名稱)
4. WF7604 (發票客戶名稱／名稱)
5. WF7605 (收款日期)
6. WF7606 (出貨日期)
7. WF7607 (發票編號)

## 7. 索引資料

主要索引以流水號、業務員、發票客戶代號名稱、發票客戶名稱、收款日期、出貨日期、發票編號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示參考SOSIPF和KEY=WF7601-WF7606
- 支援B2CHK檢查功能
- 提供收款明細的完整記錄和追蹤
- 包含收款日期和出貨日期的雙重時間追蹤
- 整合客戶代號和客戶名稱的完整資訊 