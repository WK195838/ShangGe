# REWF371 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF371 |
| 檔案名稱 | 產品銷售分佈彙總表 |
| 檔案類型 | PF (實體檔案) |
| 檔案屬性 | *NOMAX |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |

## 2. 檔案功能說明

此檔案為 REWF37 的擴充版本，用於儲存產品銷售分佈彙總資料，額外包含地區、通路、業務員等維度分析。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF371 | PF | 產品銷售分佈彙總表擴充檔 |

## 4. 紀錄格式

### 主紀錄格式：WF370

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | WF3701 | 產品代號 | 1 | | A | | SD03 | |
| 2 | WF3702 | 週月 | | | A | | SD01 | |
| 3 | WF3703 | 訂單 | | 6 | N | | | |
| 4 | WF3704 | 公價 | | 6 | N | | | |
| 5 | WF3705 | 促銷 | | 6 | N | | | |
| 6 | WF3706 | 金額 | | 10 | N | | | |
| 7 | WF3707 | 同期訂單 | | 6 | N | | | |
| 8 | WF3708 | 同期公價 | | 6 | N | | | |
| 9 | WF3709 | 促銷差異 | | 6 | N | | | |
| 10 | WF3710 | 同期金額 | | 10 | N | | | |
| 11 | WF3711 | 產品出廠編號 | | 4 | A | | | |
| 12 | WF3712 | 產品出廠名稱 | | 6 | A | | | |
| 13 | WF3713 | 地區代號 | | | A | | SC04 | 新增欄位 |
| 14 | WF3714 | 流水代號 | | | A | | SC05 | 新增欄位 |
| 15 | WF3715 | 業務員代號 | | | A | | SC27 | 新增欄位 |

## 6. 主鍵欄位

複合主鍵，組成順序：
1. WF3713 (地區代號)
2. WF3714 (流水代號)
3. WF3711 (產品出廠編號)
4. WF3712 (產品出廠名稱)
5. WF3701 (產品代號)
6. WF3702 (週月)

## 7. 索引資料

主要索引以地區代號、流水代號、產品出廠編號、產品出廠名稱、產品代號、週月為排序

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案屬性為 *NOMAX
- 為 REWF37 的擴充版本，新增地區、通路、業務員維度
- 包含當期和同期比較資料
- 檔案中有部分欄位標示為 @@ 表示新增或修改 