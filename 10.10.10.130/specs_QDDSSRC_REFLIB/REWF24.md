# REWF24 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF24
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 專櫃產品銷售排行榜一 *nomax
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF24為專櫃產品銷售排行榜一檔，用於記錄專櫃產品的銷售排行資訊。檔案設計包含銷售數量、銷售重量、重量率、銷售金額、銷售毛利等關鍵績效指標，支援專櫃產品績效排行分析。採用*nomax設計以支援多期間的排行資料管理。

## 3. 系統檔案清單
```
檔案名稱: REWF24
記錄格式: WF240
記錄長度: 包含8個欄位
屬性: MAXMBRS(*NOMAX)
```

## 4. 紀錄格式
### Record Format: WF240

## 5. 欄位規格表

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| WF2401 | 專櫃名稱 | - | - | 字元 | REFFLD(SC04) | 專櫃名稱 |
| WF2402 | 產品分類 | - | - | 字元 | REFFLD(MA08) | 產品分類代碼 |
| WF2403 | 產品名稱 | - | - | 字元 | REFFLD(MA01) | 產品名稱 |
| WF2404 | 銷售量 | - | 7 | 壓縮數字 | P 0 | 銷售數量 |
| WF2405 | 銷售重量 | - | 11 | 壓縮數字 | P 2 | 銷售重量(含2位小數) |
| WF2406 | 銷售重量率 | - | 6 | 壓縮數字 | P 2 | 銷售重量率(含2位小數) |
| WF2407 | 銷售金額 | - | 11 | 壓縮數字 | P 2 | 銷售金額(含2位小數) |
| WF2408 | 銷售毛利 | - | 11 | 壓縮數字 | P 2 | 銷售毛利(含2位小數) |

## 6. 主鍵欄位
- WF2401 (專櫃名稱)
- WF2402 (產品分類)
- WF2403 (產品名稱)

## 7. 索引資料
主要索引：WF2401+WF2402+WF2403
此索引支援按專櫃、產品分類、產品的層次化查詢。

## 8. 備註
- 採用*NOMAX設計，支援多期間專櫃排行資料管理
- 提供完整的銷售績效排行分析
- 金額相關欄位保留2位小數精度
- 數值欄位採用壓縮數字格式(P)提升儲存效率
- 配合REWF24L1邏輯檔案提供排序功能
- 與專櫃管理、產品主檔密切關聯
- 支援專櫃產品績效排行分析
- 提供銷售重量與重量率分析
- 適用於專櫃產品策略制定
- 可與REWF25專櫃產品銷售排行榜二進行對比分析 