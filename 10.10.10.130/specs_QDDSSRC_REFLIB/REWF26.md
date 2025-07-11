# REWF26 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF26
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 客戶毛利金額排行榜 *nomax
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF26為客戶毛利金額排行榜檔，用於記錄客戶與專櫃的毛利排行資訊。檔案設計包含銷售金額、毛利金額、毛利率、毛利率排名等關鍵績效指標，並預設按毛利金額降序排列，提供客戶毛利績效分析。採用*nomax設計以支援多期間的排行資料管理。此檔案為客戶盈利能力評估的重要工具。

## 3. 系統檔案清單
```
檔案名稱: REWF26
記錄格式: WF260
記錄長度: 包含6個欄位
屬性: MAXMBRS(*NOMAX)
```

## 4. 紀錄格式
### Record Format: WF260

## 5. 欄位規格表

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
- WF2604 (毛利金額) DESCEND
- WF2602 (專櫃名稱)

## 7. 索引資料
主要索引：WF2601+WF2604 DESCEND+WF2602
此索引支援按客戶別、毛利金額降序、專櫃名稱的層次化查詢。

## 8. 備註
- 採用*NOMAX設計，支援多期間客戶毛利排行資料管理
- 預設按毛利金額降序排列(DESCEND)
- 提供完整的客戶盈利能力分析
- 毛利金額保留2位小數精度
- 毛利率保留1位小數精度
- 包含毛利率排名功能
- 數值欄位採用壓縮數字格式(P)提升儲存效率
- 與客戶管理、專櫃管理密切關聯
- 支援客戶價值評估與專櫃績效分析
- 適用於客戶策略制定與專櫃資源配置
- 提供毛利導向的客戶排行管理 