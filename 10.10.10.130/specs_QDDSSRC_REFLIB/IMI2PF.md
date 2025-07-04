# IMI2PF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | IMI2PF |
| 檔案名稱 | 年終庫存檔－康齡 |
| 檔案類型 | PF (實體檔案) |
| 資料庫 | REFLIB |
| 記錄格式 | IY0 |
| 主鍵 | IY15+IY01+IY02+IY03 |
| 參照檔案 | RERF |
| 建立日期 | - |
| 最後異動日期 | - |

## 2. 檔案功能說明

本檔案為康齡公司年終庫存檔，記錄年終盤點時的庫存數量資料，包含期初庫存、進貨數量、出貨數量、保留數量、可用數量等資訊。

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| IMI2PF | PF | 年終庫存檔實體檔案 |
| IMI2LF01 | LF | 年終庫存檔邏輯檔案 |

## 4. 紀錄格式

**記錄格式名稱：** IY0

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|----------|
| IY01 | 產品編號 | - | - | R | Key | 參照RERF |
| IY02 | 產品項目代號 | - | - | R | Key | 參照RERF |
| IY03 | 產品類別代號 | - | - | R | Key | 參照RERF |
| IY04 | 產品名稱 | - | - | R | - | 參照RERF |
| IY05 | 產品規格 | - | - | R | - | 參照RERF |
| IY06 | 期初數量 | - | - | R | - | 參照RERF |
| IY07 | 進貨數量 | - | - | R | - | 參照RERF |
| IY08 | 出貨數量 | - | - | R | - | 參照RERF |
| IY09 | 保留數量 | - | - | R | - | 參照RERF |
| IY10 | 可用數量 | - | - | R | - | 參照RERF |
| IY15 | 年終年月 | - | 6 | R | Key | 年終年月 |
| IYXX | 建立日期 | - | 8 | R | - | 建立日期 |
| IYYY | 建立時間 | - | - | R | - | 建立時間 |
| IYZZ | 建立者 | - | - | R | - | 建立者 |

## 6. 主鍵欄位

**主鍵組成：** IY15 + IY01 + IY02 + IY03
- IY15：年終年月
- IY01：產品編號
- IY02：產品項目代號
- IY03：產品類別代號

## 7. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| 主索引 | IY15+IY01+IY02+IY03 | UNIQUE | 唯一索引 |

## 8. 備註

1. 本檔案專為康齡公司設計
2. UNIQUE屬性確保每個產品在同一年終年月只有一筆記錄
3. 參照RERF檔案取得欄位定義
4. 記錄年終盤點的庫存狀況
5. 支援庫存數量的各項統計分析 