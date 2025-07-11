# REWF60 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF60 |
| 檔案名稱 | 發票作廢排行榜 |
| 檔案類型 | PF (實體檔案) |
| 檔案屬性 | *NOMAX |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存發票作廢排行榜資料，記錄發票作廢的統計排行資訊，包含作廢流水號、業務員、客戶代號、作廢發票數量、總體發票數量等資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF60 | PF | 發票作廢排行榜主檔 |

## 4. 紀錄格式

### 主紀錄格式：WF600

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF6001 | 作廢流水流水號 | 1 | 5 | N | 0 | | |
| 2 | WF6002 | 業務員 | | | A | | SI31 | |
| 3 | WF6003 | 客戶代號 | | | A | | SI08 | |
| 4 | WF6004 | 作廢發票數量 | | 4 | N | 0 | | |
| 5 | WF6005 | 總體發票數量 | | 4 | N | 0 | | |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF6001 (作廢流水流水號) - DESCEND 降序
2. WF6004 (作廢發票數量)
3. WF6005 (總體發票數量)

## 7. 索引資料

主要索引以作廢流水流水號降序、作廢發票數量、總體發票數量為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案屬性為 *NOMAX
- 檔案註解中顯示KEY=WF6001+WF6002+WF6003
- 主鍵中WF6001使用DESCEND降序排列
- 用於統計和分析發票作廢情況
- 支援業務員發票作廢率分析 