# REWF26L1 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF26L1
- **檔案型態**: 邏輯檔案 (LF)
- **檔案說明**: 客戶毛利金額排行榜 *nomax
- **實體檔案**: REWF26

## 2. 檔案功能說明
REWF26L1為REWF26客戶毛利金額排行榜的邏輯檔案，以毛利率降序排列提供客戶毛利績效排行分析。此邏輯檔案專門為按毛利率排序的查詢需求而設計，配合實體檔案REWF26提供完整的客戶毛利排行功能。

## 3. 系統檔案清單
```
檔案名稱: REWF26L1
記錄格式: WF260
基礎檔案: REWF26 (PFILE)
屬性: MAXMBRS(*NOMAX)
```

## 4. 紀錄格式
### Record Format: WF260 (引用REWF26)

## 5. 欄位規格表
引用REWF26實體檔案的所有欄位：

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| WF2601 | 客戶別 | - | - | 字元 | REFFLD(#B01) | 客戶代碼 |
| WF2602 | 專櫃名稱 | - | - | 字元 | REFFLD(SC04) | 專櫃名稱 |
| WF2603 | 銷售金額 | - | 9 | 壓縮數字 | P 0 | 銷售金額 |
| WF2604 | 毛利金額 | - | 11 | 壓縮數字 | P 2 | 毛利金額(含2位小數) |
| WF2605 | 毛利率 | - | 3 | 壓縮數字 | P 1 | 毛利率(含1位小數) |
| WF2606 | 毛利率排名 | - | 4 | 短整數 | S 0 | 毛利率排名 |

## 6. 主鍵欄位
- WF2601 (客戶別)
- WF2605 (毛利率) DESCEND
- WF2602 (專櫃名稱)

## 7. 索引資料
主要索引：WF2601+WF2605 DESCEND+WF2602
此邏輯檔案按客戶別、毛利率降序、專櫃名稱排列，提供按毛利率的客戶排行查詢。

## 8. 備註
- 邏輯檔案，基於REWF26實體檔案
- 專門提供按毛利率降序的客戶排行功能
- 採用DESCEND降序排列，高毛利率客戶優先顯示
- 配合實體檔案提供完整的毛利排行查詢功能
- 與REWF26實體檔案同步更新
- 提供高效的毛利率導向客戶排行查詢
- 適用於客戶價值評估與盈利能力分析
- 支援客戶策略制定與資源配置決策 