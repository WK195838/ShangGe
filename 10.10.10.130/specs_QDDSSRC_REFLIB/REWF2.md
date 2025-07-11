# REWF2 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF2
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 品牌銷售分佈彙總表 *nomax
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF2為品牌銷售分佈彙總表檔，用於彙總分析品牌在各客戶的銷售分佈情況。檔案設計支援當月與去年同期的比較分析，並提供實際與預測銷售的完整記錄。包含品牌、客戶、客戶簡稱三層維度，以及訂購、出貨、待貨、金額等多項銷售指標。採用*nomax設計以支援多期間的品牌分析資料保存。

## 3. 系統檔案清單
```
檔案名稱: REWF2
記錄格式: WF2
記錄長度: 包含18個欄位
屬性: MAXMBRS(*NOMAX)
```

## 4. 紀錄格式
### Record Format: WF2

## 5. 欄位規格表

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| WF201 | 品牌 | - | 2 | 字元 | - | 品牌代碼 |
| WF202 | 客戶 | - | 5 | 字元 | - | 客戶代碼 |
| WF203 | 客戶簡稱 | - | 4 | 字元 | - | 客戶簡稱 |
| WF204 | 訂購數 | - | 6 | 數值 | S 0 | 當期訂購數量 |
| WF205 | 出貨數 | - | 6 | 數值 | S 0 | 當期出貨數量 |
| WF206 | 待貨數 | - | 6 | 數值 | S 0 | 當期待出貨數量 |
| WF207 | 金額 | - | 10 | 數值 | S 0 | 當期銷售金額 |
| WF208 | 去年訂購數 | - | 6 | 數值 | S 0 | 去年同期訂購數 |
| WF209 | 去年出貨數 | - | 6 | 數值 | S 0 | 去年同期出貨數 |
| WF210 | 待貨數回饋 | - | 6 | 數值 | S 0 | 待貨回饋數量 |
| WF211 | 去年金額 | - | 10 | 數值 | S 0 | 去年同期金額 |
| WF212 | 預測訂購數 | - | 6 | 數值 | S 0 | 預測訂購數量 |
| WF213 | 預測出貨數 | - | 6 | 數值 | S 0 | 預測出貨數量 |
| WF214 | 預測待貨數 | - | 6 | 數值 | S 0 | 預測待貨數量 |
| WF215 | 訂購平均單價 | - | 10 | 數值 | S 4 | 訂購平均單價(含4位小數) |
| WF216 | 出貨平均單價 | - | 10 | 數值 | S 4 | 出貨平均單價(含4位小數) |
| WF217 | 待貨平均單價 | - | 10 | 數值 | S 4 | 待貨平均單價(含4位小數) |
| WF218 | 幣別 | - | 20 | 字元 | - | 貨幣種類 |

## 6. 主鍵欄位
- WF201 (品牌)
- WF202 (客戶)
- WF203 (客戶簡稱)

## 7. 索引資料
主要索引：WF201+WF202+WF203
此索引支援按品牌、客戶、客戶簡稱的層次化查詢。

## 8. 備註
- 採用*NOMAX設計，支援多期間品牌分析資料管理
- 提供當期與去年同期的完整比較分析
- 包含實際與預測銷售的雙軌記錄
- 所有數值欄位採用有號數字格式(S)
- 平均單價欄位保留4位小數精度
- 支援多幣別品牌分析
- 與品牌管理、客戶主檔密切關聯
- 適用於品牌策略分析與市場預測
- 提供品牌績效評估的完整數據基礎
- 可進行品牌市場佔有率分析 