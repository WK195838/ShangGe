# MTMGLF1 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | MTMGLF1 |
| 檔案描述 | 專櫃ＰＬＵ檔 (邏輯檔) |
| 檔案類型 | LF (Logical File) |
| 記錄格式 | MG0 |
| 主鍵 | MG01 + MG02 (專櫃代號 + PLU代號) |
| 實體檔案 | MTMGPF |
| 檔案屬性 | 邏輯檢視，特殊排序 |

## 2. 檔案功能說明

MTMGLF1 為 MTMGPF 專櫃PLU檔的特殊邏輯檔案，提供：
- 專櫃PLU特殊排序檢視
- 專櫃管理專用檢視
- PLU分析支援
- 業績統計功能

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 說明 |
|----------|----------|------|
| MTMGLF1 | 專櫃PLU邏輯檔1 | 主檔 |
| MTMGPF | 專櫃PLU實體檔 | 實體檔案 |
| MTMGLF | 專櫃PLU邏輯檔 | 基本邏輯檔 |
| RERF | 參考檔案 | 欄位定義參考 |

## 4. 紀錄格式

### 記錄格式：MG0 (繼承自 MTMGPF)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| MG01 | 專櫃代號 | 1-5 | 5 | A | R | 主鍵，專櫃識別碼 |
| MG02 | PLU代號 | 6-14 | 9 | A | R | 主鍵，PLU識別碼 |
| MG03 | 產品代號 | 15-23 | 9 | A | R | 對應產品代號 |
| MG04 | PLU名稱 | 24-43 | 20 | A | R | PLU中文名稱 |
| MG05 | 英文名稱 | 44-63 | 20 | A | R | PLU英文名稱 |
| MG06 | PLU簡稱 | 64-73 | 10 | A | R | PLU簡稱 |
| MG07 | PLU價格 | 74-82 | 9 | N | R | PLU銷售價格 |
| MG08 | 成本 | 83-91 | 9 | N | R | PLU成本價格 |
| MG09 | 使用狀態 | 92 | 1 | A | R | 'A'-有效，'I'-停用 |
| MG10 | 部門代號 | 93-97 | 5 | A | R | 所屬部門 |
| MG11 | 分類代號 | 98-102 | 5 | A | R | 產品分類 |
| MG12 | 庫存數量 | 103-111 | 9 | N | R | 目前庫存 |
| MG13 | 安全庫存 | 112-120 | 9 | N | R | 安全庫存量 |
| MG14 | 促銷狀態 | 121 | 1 | A | R | 'Y'-促銷中，'N'-一般 |
| MG15 | 促銷價格 | 122-130 | 9 | N | R | 促銷價格 |
| MGXX | 建立日期 | 131-138 | 8 | N | R | 格式：YYYYMMDD |
| MGYY | 建立時間 | 139-144 | 6 | N | R | 格式：HHMMSS |
| MGZZ | 建立者 | 145-154 | 10 | A | R | 操作人員 |

## 6. 主鍵欄位

| 鍵值序號 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | MG01 | 專櫃代號 | 升序 |
| 2 | MG02 | PLU代號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：特殊排序索引
- **索引欄位**：MG01 + MG02
- **索引類型**：PRIMARY
- **說明**：專櫃代號 + PLU代號複合升序排序

### 輔助索引
1. **產品索引**：MG03 (產品代號)
2. **部門索引**：MG10 + MG01 + MG02
3. **分類索引**：MG11 + MG01 + MG02
4. **狀態索引**：MG09 (使用狀態)
5. **促銷索引**：MG14 + MG01 + MG02
6. **價格索引**：MG07 (PLU價格)

### 邏輯檢視特性
- **基底檔案**：MTMGPF
- **檢視類型**：特殊排序檢視
- **排序方式**：專櫃 + PLU特殊排序
- **分組顯示**：依專櫃分組

## 8. 備註

### 設計考量
1. 此檔案為 MTMGPF 的特殊排序邏輯檢視檔案
2. 提供專櫃PLU管理功能
3. 支援專櫃業績分析需求

### 特殊功能
- **專櫃分組**：按專櫃代號分組排序
- **PLU管理**：專櫃PLU專門管理
- **價格控制**：PLU價格管理
- **庫存監控**：PLU庫存監控

### 參考關聯
- **實體檔案**：MTMGPF (專櫃PLU資料)
- **產品檔案**：MTMAPF (MG03 = MA01)
- **專櫃檔案**：專櫃檔案 (MG01 = 專櫃代號)
- **部門檔案**：PA#ALF8 (MG10 = #A01)
- **分類檔案**：PA#分類檔 (MG11 = 分類代號)

### 業務規則
1. 顯示順序：專櫃代號 + PLU特殊排序
2. 產品關係需維持完整性
3. 價格調整需符合業務規則
4. 庫存數量需配合實際狀況

### 資料完整性
1. 資料內容完全依賴 MTMGPF 實體檔案
2. MG03 需對應 MTMAPF 中的有效產品
3. MG10 需對應有效的部門代號
4. 價格和成本需符合業務邏輯

### 使用注意事項
1. 此為邏輯檔案，不可直接寫入資料
2. 所有異動需透過 MTMGPF 實體檔案進行
3. 專櫃調整會影響PLU分組
4. 適用於專櫃管理與業績分析 