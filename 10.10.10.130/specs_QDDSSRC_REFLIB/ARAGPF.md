# ARAGPF 檔案規格書

## 1. 基本資料
- 檔名: ARAGPF
- 類型: PF (Physical File)
- 說明: 銷貨折讓明細檔
- 主鍵: AG02+AG03+AG04
- 建立日期: (待補)
- 最後修改日期: 2000/04/17 (MICHELLE修改)
- 參考檔: RERF
- 索引約束: UNIQUE
- 修改記錄:
  - M001 (2000/04/17 MICHELLE): FOR DUTY營業稅法

## 2. 檔案功能說明
此實體檔案為銷貨折讓明細檔，提供以下功能：
- 記錄銷貨折讓的明細資料
- 儲存銷貨折讓的數量、金額與稅額資訊
- 支援銷貨折讓的完整生命週期管理
- 提供銷貨折讓與發票的對應關係
- 記錄銷貨折讓的產品明細資訊
- 支援應收帳款管理系統的銷貨折讓處理
- 提供銷貨折讓資料的主要儲存結構
- 記錄銷貨折讓的稅務處理資訊
- 支援銷貨折讓的查詢與報表作業
- 支援營業稅法相關的DUTY處理

## 3. 系統檔案清單
- 主要實體檔: ARAGPF (銷貨折讓明細檔)
- 相關邏輯檔: 
  - ARAGLF, ARAGLF01 至 ARAGLF05 (各種索引邏輯檔)
- 參考檔: RERF (系統參考檔)
- 相關檔案: 
  - ARAFPF (價差折讓資料檔)
  - 產品主檔 (MA01)
  - 發票相關檔案

## 4. 紀錄格式
實體檔案記錄格式，包含完整的銷貨折讓明細資料欄位，支援 UNIQUE 約束確保資料唯一性。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| AG01 | 公司別 | 1-2 | 2A | 文字 | 參考 #B01，必填，公司代碼 |
| AG02 | 折讓單號 | 3-14 | 12A | 文字 | 參考 AF02，必填，折讓單號 |
| AG03 | 產品代號 | 15-29 | 15A | 文字 | 參考 MA01，必填，產品識別碼 |
| AG04 | 發票號碼 | 30-37 | 8A | 文字 | 參考 SI02，必填，發票號碼 |
| AG05 | 銷退數量 | 38-42 | 5P0 | 數值 | 銷退數量 |
| AG06 | 折讓單價 | 43-51 | 9P2 | 數值 | 折讓單價，含小數點2位 |
| AG07 | 折讓金額 | 52-60 | 9P0 | 數值 | 折讓金額，以分為單位 |
| AG08 | 折讓稅前總金額 | 61-71 | 11P2 | 數值 | 折讓稅前總金額，含小數點2位 |
| AG09 | 客戶代號 | 72-85 | 14A | 文字 | 參考 #B14，客戶識別碼 |
| AG10 | 單據代號 | 86-95 | 10A | 文字 | 參考 #B15，單據識別碼 |
| AG11 | 折讓日期 | 96-103 | 8S0 | 日期 | 參考 #AXX，折讓日期 |
| AG12 | 銷退數量計量單位 | 104-108 | 5P0 | 數值 | 參考 AG05，銷退數量計量單位 |
| AG13 | 銷退數量計重單位 | 109-113 | 5P0 | 數值 | 參考 SD05，銷退數量計重單位 |
| AG14 | 折讓稅前金額FOB | 114-124 | 11P2 | 數值 | 折讓稅前金額FOB，含小數點2位 |
| AG15 | 折讓稅前金額FHI | 125-135 | 11P2 | 數值 | 折讓稅前金額FHI，含小數點2位 |
| AG16 | 折讓稅前金額DUTY | 136-146 | 11P2 | 數值 | 折讓稅前金額DUTY，含小數點2位 |
| AG17 | 台幣折讓稅前金額FOB | 147-157 | 11P2 | 數值 | 台幣折讓稅前金額FOB，含小數點2位 |
| AG18 | 台幣折讓稅前金額FHI | 158-168 | 11P2 | 數值 | 台幣折讓稅前金額FHI，含小數點2位 |
| AG19 | 台幣折讓稅前金額DUTY | 169-179 | 11P2 | 數值 | 台幣折讓稅前金額DUTY，含小數點2位 |
| AG20 | 台幣折讓總金額 | 180-190 | 11P2 | 數值 | 台幣折讓總金額，含小數點2位 |
| AG21 | 折讓稅額 | 191-201 | 11P2 | 數值 | 參考 AG07，折讓稅額，含小數點2位 |
| AG071 | 折讓金額 | 202-212 | 11P2 | 數值 | 折讓金額，含小數點2位 |
| AGXX | 異動日期 | 213-220 | 8S0 | 日期 | 參考 #AXX，最後異動日期 |
| AGYY | 異動時間 | 221-226 | 6S0 | 時間 | 參考 #AYY，最後異動時間 |
| AGZZ | 異動者 | 227-236 | 10A | 文字 | 參考 #AZZ，最後異動人員 |

## 6. 主鍵欄位
- 主鍵: AG02 + AG03 + AG04
  - AG02: 折讓單號
  - AG03: 產品代號
  - AG04: 發票號碼
- 約束類型: UNIQUE (唯一約束)

## 7. 索引資料
- 主要索引: AG02 + AG03 + AG04 (依折讓單號、產品代號、發票號碼)
- 索引類型: 唯一索引 (UNIQUE)
- 排序特性: 
  - 第一層: 折讓單號 (AG02)
  - 第二層: 產品代號 (AG03)
  - 第三層: 發票號碼 (AG04)

## 8. 備註
- 此實體檔案為銷貨折讓明細的主要儲存結構
- 使用 UNIQUE 約束確保折讓明細記錄的唯一性
- 支援銷貨折讓的完整資訊管理
- 記錄銷貨折讓的數量、金額與稅額資訊
- 與價差折讓資料檔(ARAFPF)密切相關，透過折讓單號關聯
- 與產品主檔密切相關，透過產品代號關聯
- 支援應收帳款管理系統的銷貨折讓處理
- 提供多個邏輯檔案的基礎資料來源
- 記錄銷貨折讓的稅務處理資訊
- 支援銷貨折讓的查詢、報表與統計分析
- 包含完整的異動追蹤欄位(日期、時間、異動者)
- 支援營業稅法相關的DUTY處理功能
- 包含多種幣別的金額欄位(FOB、FHI、DUTY)
- 支援台幣與外幣的金額轉換處理
- AG08 欄位計算公式: AG05*單價總額
- 2000年修改以符合營業稅法要求 