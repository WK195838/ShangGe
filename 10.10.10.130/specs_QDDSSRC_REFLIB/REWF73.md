# REWF73 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF73 |
| 檔案名稱 | 供應商到貨狀況表 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存供應商到貨狀況表資料，記錄供應商產品到貨的詳細狀況，包含供應商、產品編號、各種數量統計（到貨量、開貨量、退貨量、庫存量等）、單價、完稅單位等完整到貨管理資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF73 | PF | 供應商到貨狀況表主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF730

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF7301 | 供應商 | 1 | | A | | MA12 | |
| 2 | WF7302 | 產品編號 | | | A | | MA01 | |
| 3 | WF7316 | 產品出廠編號 | | 6 | A | | | |
| 4 | WF7303 | 出貨／採購數據量 | | 6 | N | 0 | | |
| 5 | WF7304 | 供應商開貨量 | | 6 | N | 0 | | |
| 6 | WF7305 | 開貨庫存庫存量 | | 6 | N | 0 | | |
| 7 | WF7306 | 開貨／庫存庫存量 | | 6 | N | 0 | | |
| 8 | WF7307 | 交易／採購數據量 | | 6 | N | 0 | | |
| 9 | WF7308 | 數據量單價數 | | 8 | N | 2 | | 2位小數 |
| 10 | WF7309 | 數據量／庫存庫存量 | | 6 | N | 0 | | |
| 11 | WF7310 | 完稅單位 | | 11 | N | 2 | | 2位小數 |
| 12 | WF7311 | 預估數據量 | | 6 | N | 0 | | |
| 13 | WF7312 | 預估數據量庫存庫存量 | | 6 | N | 0 | | |
| 14 | WF7313 | 預估數據量／庫存庫存量 | | 6 | N | 0 | | |
| 15 | WF7314 | 採購量 | | | A | | MA15 | |
| 16 | WF7315 | 供應商／ | | | A | | MA16 | |
| 17 | WF7317 | 庫存數量 | | 6 | N | 0 | | |
| 18 | WF7318 | 庫存採購量 | | 5 | N | 2 | | 2位小數 |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF7301 (供應商)
2. WF7302 (產品編號)

## 7. 索引資料

主要索引以供應商、產品編號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示KEY=WF7301-7302
- 包含詳細的庫存變動追蹤註解
- 支援多種庫存量統計（採購、開貨、退貨、預估等）
- 價格欄位均支援2位小數精度
- 提供供應商到貨狀況的完整管理功能
- 註解中詳細說明各庫存變動的用途 