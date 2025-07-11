# POPEPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | POPEPF |
| 檔案類型 | 實體檔案 (PF) |
| 檔案用途 | 產品進貨單明細檔 |
| 作業系統 | AS/400 |
| 建立日期 | - |
| 最後修改日期 | - |

## 2. 檔案功能說明

POPEPF 為產品進貨單明細檔的核心實體檔案，負責儲存進貨單的明細資訊。此檔案記錄包含單證編號、採購單編號、產品代碼、進貨數量、價格條件等詳細的進貨明細資料，是進貨管理系統的重要明細檔案。

## 3. 系統檔案清單

- **實體檔案**: POPEPF (本檔案)
- **參考檔案**: RERF (欄位參考檔)
- **相關主檔**: POPDPF (產品進貨單主檔)

## 4. 記錄格式

### 記錄格式 PE0
- **記錄識別**: PE0
- **記錄類型**: 實體檔記錄格式
- **索引方式**: UNIQUE (唯一索引)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| PE01 | 公司別 | 1 | R | 文數字 | 參考 RERF | - |
| PE02 | 單證編號 | 2 | R | 文數字 | 參考 RERF | 第一主鍵 |
| PE03 | 採購單編號 | 3 | R | 文數字 | 參考 RERF | 第二主鍵 |
| PE04 | 產品代碼 | 4 | R | 文數字 | 參考 RERF | 第三主鍵 |
| PE05 | 進貨數量 | 5 | 8 | 數字 | 日期格式 | B2CHKA 檢核 |
| PE06 | 到貨數量 | 6 | R | 數字 | 參考 RERF | - |
| PE07 | F.O.B. | 7 | R | 文數字 | 參考 RERF | - |
| PE08 | FREIGHT | 8 | R | 文數字 | 參考 RERF | - |
| PE09 | HANDLE | 9 | R | 文數字 | 參考 RERF | - |
| PE10 | 進貨價格單位 | 10 | R | 文數字 | 參考 RERF | - |
| PEXX | 建立日期 | 11 | 8 | 數字 | 日期格式 | B2CHKA 檢核 |
| PEYY | 建立時間 | 12 | R | 數字 | 參考 RERF | - |
| PEZZ | 建立者 | 13 | R | 文字 | 參考 RERF | - |

## 6. 主鍵欄位

| 順序 | 欄位代號 | 欄位名稱 | 說明 |
|------|----------|----------|------|
| 1 | PE02 | 單證編號 | 第一主鍵 |
| 2 | PE03 | 採購單編號 | 第二主鍵 |
| 3 | PE04 | 產品代碼 | 第三主鍵 |

## 7. 索引資料

### 存取路徑設定
- **排序方式**: 升序
- **重複鍵值**: 不允許 (UNIQUE)
- **索引類型**: 唯一索引

### 索引鍵值
- 主要索引: PE02+PE03+PE04
- 索引名稱: KEY=PE02-PE04

## 8. 備註

1. **檔案特性**: 
   - 實體檔案
   - 唯一索引設定
   - 參考 RERF 欄位定義檔

2. **重要欄位說明**:
   - PE02: 單證編號，連結進貨單主檔
   - PE03: 採購單編號，連結採購單主檔
   - PE04: 產品代碼，連結產品主檔
   - PE05: 進貨數量，記錄實際進貨數量
   - PE06: 到貨數量，記錄實際到貨數量
   - PE07-PE09: 運費相關欄位 (F.O.B., FREIGHT, HANDLE)

3. **檢核設定**:
   - B2CHKA: 針對日期欄位 (PE05, PEXX) 進行格式檢核
   - 確保日期資料的正確性與一致性

4. **主鍵組合意義**:
   - 三欄位組合確保明細記錄的唯一性
   - PE02: 識別特定進貨單
   - PE03: 識別對應的採購單
   - PE04: 識別特定產品項目

5. **系統關聯**:
   - 與 POPDPF (進貨單主檔) 為主從關係
   - 連結採購單系統 (POPBPF, POPCPF)
   - 支援進貨作業完整流程

6. **使用注意事項**:
   - 主鍵組合確保進貨明細的唯一性
   - 數量欄位需要適當的單位換算處理
   - 運費欄位支援進貨成本計算
   - 建立日期記錄進貨明細的建檔時間
   - 與採購單明細的數量核對機制 