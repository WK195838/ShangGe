# REWF63 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF63 |
| 檔案名稱 | 發票主檔＋明細檔 |
| 檔案類型 | PF (實體檔案) |
| 檔案屬性 | *NOMAX |
| 參考說明 | si01+si08+sj03+si21 |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案用於儲存發票主檔＋明細檔資料，整合發票主要資訊和明細項目，包含發票日期、通路編號、流水號、發票編號、產品代號、數量、單價、金額、營業稅、銷退資訊等完整發票資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF63 | PF | 發票主檔＋明細檔（參考SOSIPF） |

## 4. 紀錄格式

### 主紀錄格式：WF630

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | SI21 | 發票日期 | 1 | 8 | N | B2CHK | | 檢查欄位(B2CHK) |
| 2 | SI10 | 通路編號 | | | A | | | |
| 3 | SJ01 | 流水號 | | | A | | | |
| 4 | SJ02 | 發票編號 | | | A | | | |
| 5 | SJ03 | 產品代號 | | | A | | | |
| 6 | SJ04 | 數量 | | | N | | | |
| 7 | SJ05 | 單價 | | | N | | | |
| 8 | SJ06 | 金額 | | | N | | | |
| 9 | SJ07 | 營業稅 | | | N | | | |
| 10 | SJ08 | 銷退數量／庫存數量 | | | N | | | |
| 11 | SJ09 | 銷退金額 | | | N | | | |
| 12 | SJ10 | 產品來源 | | | A | | | |
| 13 | SJ11 | 客戶代號／折讓編號 | | | A | | | |
| 14 | SJ12 | 流水代號／折讓編號 | | | A | | | |
| 15 | SJ13 | 公價數量 | | | N | | | |
| 16 | SJ14 | 銷退數量／訂單數 | | | N | | | |
| 17 | SJ15 | 銷退數量／公價數 | | | N | | | |
| 18 | SJXX | 異動日期 | | 8 | N | B2CHK | | 檢查欄位(B2CHK) |
| 19 | SJYY | 異動時段 | | | A | | | |
| 20 | SJZZ | 異動者 | | | A | | | |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. SJ01 (流水號)
2. SJ11 (客戶代號／折讓編號)
3. SJ03 (產品代號)
4. SI21 (發票日期) - DESCEND 降序
5. SJ02 (發票編號) - DESCEND 降序

## 7. 索引資料

主要索引以流水號、客戶代號、產品代號、發票日期降序、發票編號降序為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案屬性為 *NOMAX
- 檔案註解中顯示參考SOSIPF和KEY=SI02
- 參考說明：si01+si08+sj03+si21
- 支援B2CHK檢查功能
- 發票日期和發票編號使用DESCEND降序排列
- 整合發票主檔和明細檔的完整資料 