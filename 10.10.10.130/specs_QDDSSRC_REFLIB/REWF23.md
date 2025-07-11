# REWF23 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF23
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 期間專櫃達成率報表 *nomax
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF23為期間專櫃達成率報表檔，用於記錄特定期間內專櫃在各產品的達成率分析。與REWF22相比，本檔案專注於期間達成率與累計達成率的對比分析，提供更靈活的期間績效評估。採用*nomax設計以支援多期間的專櫃達成率資料管理。

## 3. 系統檔案清單
```
檔案名稱: REWF23
記錄格式: WF230
記錄長度: 包含9個欄位
屬性: MAXMBRS(*NOMAX)
```

## 4. 紀錄格式
### Record Format: WF230

## 5. 欄位規格表

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| WF2301 | 專櫃名稱 | - | - | 字元 | REFFLD(SC04) | 專櫃名稱 |
| WF2302 | 產品分類 | - | - | 字元 | REFFLD(MA08) | 產品分類代碼 |
| WF2303 | 產品名稱 | - | - | 字元 | REFFLD(MA01) | 產品名稱 |
| WF2304 | 期間累計銷售量 | - | 7 | 壓縮數字 | P 0 | 期間累計銷售數量 |
| WF2305 | 期間累計銷售金額 | - | 9 | 壓縮數字 | P 0 | 期間累計銷售金額 |
| WF2306 | 期間累計銷售達成率 | - | 11 | 壓縮數字 | P 2 | 期間累計銷售達成率(含2位小數) |
| WF2307 | 累計銷售量 | - | 7 | 壓縮數字 | P 0 | 總累計銷售數量 |
| WF2308 | 累計銷售金額 | - | 9 | 壓縮數字 | P 0 | 總累計銷售金額 |
| WF2309 | 累計銷售達成率 | - | 11 | 壓縮數字 | P 2 | 總累計銷售達成率(含2位小數) |

## 6. 主鍵欄位
- WF2301 (專櫃名稱)
- WF2302 (產品分類)
- WF2303 (產品名稱)

## 7. 索引資料
主要索引：WF2301+WF2302+WF2303
此索引支援按專櫃、產品分類、產品的層次化查詢。

## 8. 備註
- 採用*NOMAX設計，支援多期間專櫃達成率資料管理
- 提供期間與總累計的雙重達成率分析
- 達成率欄位保留2位小數精度
- 數值欄位採用壓縮數字格式(P)提升儲存效率
- 與REWF22專櫃達成率報表形成互補分析
- 支援靈活的期間績效評估
- 與專櫃管理、產品主檔密切關聯
- 提供專櫃期間策略分析的數據基礎
- 適用於專櫃階段性績效追蹤
- 可進行期間與總體績效的對比分析 