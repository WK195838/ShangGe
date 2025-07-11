# MTMFLF01 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | MTMFLF01 |
| 檔案描述 | 禮盒結構資料檔 (邏輯檔) |
| 檔案類型 | LF (Logical File) |
| 記錄格式 | MF0 |
| 主鍵 | MF01 + MF02 (禮盒代號 + 組成產品代號) |
| 實體檔案 | MTMFPF |
| 檔案屬性 | 邏輯檢視，特殊排序 |

## 2. 檔案功能說明

MTMFLF01 為 MTMFPF 禮盒結構資料檔的特殊邏輯檔案，提供：
- 禮盒結構專用檢視
- 組裝明細管理
- 成本計算支援
- 庫存管理專用檢視

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 說明 |
|----------|----------|------|
| MTMFLF01 | 禮盒結構資料邏輯檔01 | 主檔 |
| MTMFPF | 禮盒結構資料實體檔 | 實體檔案 |
| MTMFLF | 禮盒結構資料邏輯檔 | 基本邏輯檔 |
| RERF | 參考檔案 | 欄位定義參考 |

## 4. 紀錄格式

### 記錄格式：MF0 (繼承自 MTMFPF)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| MF01 | 禮盒代號 | 1-9 | 9 | A | R | 主鍵，禮盒產品代號 |
| MF02 | 組成產品代號 | 10-18 | 9 | A | R | 主鍵，組成產品代號 |
| MF03 | 組成數量 | 19-23 | 5 | N | R | 組成產品數量 |
| MF04 | 組成單位 | 24-25 | 2 | A | R | 組成產品單位 |
| MF05 | 組成說明 | 26-45 | 20 | A | R | 組成說明文字 |
| MF06 | 使用狀態 | 46 | 1 | A | R | 'A'-有效，'I'-停用 |
| MF07 | 組成順序 | 47-49 | 3 | N | R | 組合順序 |
| MF08 | 必要性 | 50 | 1 | A | R | 'Y'-必要，'N'-可選 |
| MF09 | 組成成本 | 51-59 | 9 | N | R | 組成產品成本 |
| MF10 | 供應商 | 60-67 | 8 | A | R | 組成產品供應商 |
| MFXX | 建立日期 | 68-75 | 8 | N | R | 格式：YYYYMMDD |
| MFYY | 建立時間 | 76-81 | 6 | N | R | 格式：HHMMSS |
| MFZZ | 建立者 | 82-91 | 10 | A | R | 操作人員 |

## 6. 主鍵欄位

| 鍵值序號 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | MF01 | 禮盒代號 | 升序 |
| 2 | MF02 | 組成產品代號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：禮盒組成複合索引
- **索引欄位**：MF01 + MF02
- **索引類型**：PRIMARY
- **說明**：禮盒代號 + 組成產品代號複合升序排序

### 輔助索引
1. **組成順序索引**：MF01 + MF07 (禮盒 + 組成順序)
2. **產品索引**：MF02 (組成產品代號)
3. **狀態索引**：MF06 (使用狀態)
4. **必要性索引**：MF01 + MF08 (禮盒 + 必要性)
5. **供應商索引**：MF10 (供應商代號)

### 邏輯檢視特性
- **基底檔案**：MTMFPF
- **檢視類型**：特殊排序檢視
- **排序方式**：禮盒 + 組成順序
- **分組顯示**：依禮盒分組

## 8. 備註

### 設計考量
1. 此檔案為 MTMFPF 的特殊排序邏輯檢視檔案
2. 提供禮盒組成結構管理功能
3. 支援禮盒成本計算與庫存管理

### 特殊功能
- **禮盒分組**：按禮盒代號分組排序
- **組成管理**：依組成順序排序顯示
- **成本計算**：支援禮盒成本分析
- **庫存控制**：組成產品庫存管理

### 參考關聯
- **實體檔案**：MTMFPF (禮盒結構資料)
- **禮盒產品檔**：MTMAPF (MF01 = MA01)
- **組成產品檔**：MTMAPF (MF02 = MA01)
- **供應商檔案**：MTMBPF (MF10 = MB01)
- **單位檔案**：PA#單位檔 (MF04 = 單位代號)

### 業務規則
1. 顯示順序：禮盒代號 + 組成順序
2. 禮盒與組成產品需對應有效產品
3. 組成數量需大於零
4. 必要組成不可刪除

### 資料完整性
1. 資料內容完全依賴 MTMFPF 實體檔案
2. MF01 需對應 MTMAPF 中的有效禮盒產品
3. MF02 需對應 MTMAPF 中的有效組成產品
4. MF10 需對應 MTMBPF 中的有效供應商

### 使用注意事項
1. 此為邏輯檔案，不可直接寫入資料
2. 所有異動需透過 MTMFPF 實體檔案進行
3. 禮盒結構變更影響成本計算
4. 適用於禮盒管理與成本分析 