# REWF79 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF79 |
| 檔案名稱 | 收貨未確認明細表 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存收貨未確認明細表資料，記錄收貨但尚未確認的明細資訊，包含收貨流水帳、收貨日期、供應商編號、序號、出貨流水帳、產品代號、數量等未確認收貨的管理資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF79 | PF | 收貨未確認明細表主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF790

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF7901 | 收貨流水帳 | 1 | | A | | SN04 | |
| 2 | WF7902 | 收貨日期 | | 8 | N | B2CHK | SN05 | 檢查欄位(B2CHK) |
| 3 | WF7903 | 供應商編號 | | | A | | SN02 | |
| 4 | WF7904 | 序號 | | 2 | N | | | |
| 5 | WF7905 | 出貨流水帳 | | | A | | SN03 | |
| 6 | WF7906 | 產品代號 | | | A | | SO03 | |
| 7 | WF7907 | 數量Ь單量 | | | A | | SO06 | |
| 8 | WF7908 | 數量／公價 | | | A | | SO07 | |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF7901 (收貨流水帳)
2. WF7902 (收貨日期)
3. WF7903 (供應商編號)
4. WF7906 (產品代號)

## 7. 索引資料

主要索引以收貨流水帳、收貨日期、供應商編號、產品代號為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示KEY=（未完整顯示）
- 支援B2CHK檢查功能
- 提供收貨未確認狀態的管理追蹤
- 包含收貨和出貨流水帳的對應關係
- 整合數量的單量和公價計算 