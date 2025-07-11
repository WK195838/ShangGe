# REWF14 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF14
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 通路產品達成率 *nomax
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF14為通路產品達成率檔，用於記錄各通路產品的銷售達成情況分析，包含目標數量、實際銷售、累計達成率等關鍵績效指標。檔案設計支援通路與地區的雙維度分析，並區分當期、累計、上期、去年等多時間區間的達成率比較，提供完整的通路產品績效管理。採用*nomax設計以支援多期間的達成率資料管理。

## 3. 系統檔案清單
```
檔案名稱: REWF14
記錄格式: WF140
記錄長度: 包含14個欄位
屬性: MAXMBRS(*NOMAX)
```

## 4. 紀錄格式
### Record Format: WF140

## 5. 欄位規格表

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| WF1401 | 通路 | - | - | 字元 | REFFLD(#C01) | 通路代碼 |
| WF1402 | 產品分類 | - | - | 字元 | REFFLD(MA08) | 產品分類代碼 |
| WF1403 | 產品名稱 | - | - | 字元 | REFFLD(MA01) | 產品名稱 |
| WF1404 | 目標數量 | - | - | 數值 | REFFLD(SK10) | 銷售目標數量 |
| WF1405 | 目標金額 | - | - | 數值 | REFFLD(SK22) | 銷售目標金額 |
| WF1406 | 實際數量 | - | 7 | 壓縮數字 | P 0 | 實際銷售數量 |
| WF1407 | 實際金額 | - | 9 | 壓縮數字 | P 0 | 實際銷售金額 |
| WF1408 | 累計銷售量 | - | 7 | 壓縮數字 | P 0 | 累計銷售數量 |
| WF1409 | 累計銷售金額 | - | 9 | 壓縮數字 | P 0 | 累計銷售金額 |
| WF1410 | 上期累計銷售量 | - | 7 | 壓縮數字 | P 0 | 上期累計銷售數量 |
| WF1411 | 上期累計銷售金額 | - | 9 | 壓縮數字 | P 0 | 上期累計銷售金額 |
| WF1412 | 去年累計銷售量 | - | 7 | 壓縮數字 | P 0 | 去年累計銷售數量 |
| WF1413 | 去年累計銷售金額 | - | 9 | 壓縮數字 | P 0 | 去年累計銷售金額 |
| WF1414 | 業務 | - | - | 字元 | REFFLD(#C02) | 業務代碼 |

## 6. 主鍵欄位
- WF1401 (通路)
- WF1414 (業務)
- WF1402 (產品分類)
- WF1403 (產品名稱)

## 7. 索引資料
主要索引：WF1401+WF1414+WF1402+WF1403
此索引支援按通路、業務、產品分類、產品的層次化查詢。

## 8. 備註
- 採用*NOMAX設計，支援多期間達成率資料管理
- 提供目標與實際的完整比較分析
- 支援當期、累計、上期、去年多維度比較
- 數值欄位採用壓縮數字格式(P)提升儲存效率
- 與通路管理、產品主檔、銷售目標檔密切關聯
- 提供通路績效管理與產品策略分析
- 支援達成率計算與趨勢分析
- 可與REWF13地區產品達成率進行對比分析 