# REWF863 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案代號 | REWF863 |
| 檔案名稱 | 試飲訂單明細分析表 |
| 檔案類型 | PF (實體檔案) |
| 系統別 | 匯東系統 |
| 參考檔案 | RERF |
| 程式修改 | 00A需求單號: 1070094 - 107/01/31 DEREK新增現值數字產出成本 |
|  | 00D需求單號: 1070124 - 107/02/13 STEVEN新增單月流水&試飲原因 |

## 2. 檔案功能說明

此檔案用於儲存試飲訂單明細分析表資料，為REWF86系列的另一個實體檔案，提供試飲訂單的詳細分析功能，包含試飲客戶代號與規格、流水代號、業務員與姓名、單月流水、試飲原因、確認出貨日期、通路流水、產品代號與規格、訂貨公價數量、總金額、出貨金額營業額、客戶規格等完整的試飲訂單分析資料。

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | REWF863 | PF | 試飲訂單明細分析表主檔 |

## 4. 紀錄格式

### 主紀錄格式：SC0

## 5. 欄位規格

| 序號 | 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|------|----------|----------|------|------|------|------|----------|------|
| 1 | SC04 | 試飲客戶代號 | 1 | | A | | | |
| 2 | SC05 | 流水代號 | | | A | | | |
| 3 | ME04N | 試飲客戶規格 | | | A | | ME04 | |
| 4 | SC27 | 業務員 | | | A | | | |
| 5 | MC02N | 業務員姓名 | | | A | | MC02 | |
| 6 | SC06 | 單月流水 | | | A | | | 00D新增 |
| 7 | SC10 | 試飲原因 | | | A | | | 00D新增 |
| 8 | SC39 | 現確認日期 | | 8 | N | 0 | | |
| 9 | SC08 | 出貨日期 | | 8 | N | 0 | | |
| 10 | SC02 | 通路流水 | | | A | | | |
| 11 | SD03 | 產品代號 | | | A | | | |
| 12 | MA03N | 產品規格 | | | A | | MA03 | |
| 13 | SD04 | 訂貨數量 | | | A | | | |
| 14 | SD05 | 公價數量 | | | A | | | |
| 15 | SD22W | 總金額 | | 11 | N | 2 | | 00A新增，2位小數 |
| 16 | SC16 | 出貨金額 | | | A | | | |
| 17 | SC17 | 出貨營業額 | | | A | | | |
| 18 | ME04W | 客戶規格 | | | A | | ME04 | |

## 6. 主鍵欄位

未指定主鍵欄位（檔案中無K關鍵字設定）

## 7. 索引資料

無特定索引設定

## 8. 備註

- 此檔案參考 RERF 檔案欄位定義
- 檔案註解中顯示KEY=（未完整顯示）
- 程式修改記錄：
  - 00A需求單號: 1070094 - DEREK新增現值數字產出成本
  - 00D需求單號: 1070124 - STEVEN新增單月流水&試飲原因
- 為REWF86系列試飲訂單分析的輔助檔案
- 與REWF862類似結構但無主鍵設定
- 提供試飲訂單的另一種儲存方式
- 包含完整的客戶、產品、業務員資訊
- 支援試飲活動的多元化分析需求
- 總金額欄位支援2位小數精度 