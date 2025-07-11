# SOSPLF01 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSPLF01
- **檔案類型**: LF (邏輯檔案)
- **檔案說明**: 原始/轉帳單據對照檔 - 轉帳單號排序邏輯檔
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)
- **檔案屬性**: PFILE(SOSPPF)

## 2. 檔案功能說明
此邏輯檔案基於SOSPPF實體檔案建立，主要提供以轉帳單號和原始單號組合排序的查詢功能，用於單據對照管理。

### 主要功能
- 按轉帳單號排序查詢
- 原始單號次要排序
- 單據對照關係追蹤
- 轉帳作業管理

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSPLF01 | LF | 原始/轉帳單據對照檔轉帳單號排序邏輯檔 |
| SOSPPF | PF | 原始/轉帳單據對照檔 (實體檔案) |

## 4. 紀錄格式

### 4.1 記錄格式 SP0
```
PFILE(SOSPPF)
KEY: SP02 + SP01
```

#### 關鍵欄位
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SP02 | 轉帳單號 | A | - | ASC | 主要排序鍵 |
| 2 | SP01 | 原始單號 | A | - | ASC | 次要排序鍵 |

#### 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 型態 | 長度 | 小數 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| SP01 | 原始單號 | A | - | - | R | 原始單據編號，次要排序鍵 |
| SP02 | 轉帳單號 | A | - | - | R | 轉帳單據編號，主要排序鍵 |
| SP03 | 原始發票編號 | A | - | - | R | 原始發票編號 |
| SP04 | 轉帳發票編號 | A | - | - | R | 轉帳發票編號 |
| SP05 | 沖銷記帳 | A | 1 | - | R | 沖銷記帳標記，'Y'=需要沖銷記帳，'N'=無需沖銷記帳 |
| SPXX | 異動人員 | A | 8 | 0 | R | 異動人員代號 |
| SPYY | 異動時間 | N | - | - | R | 異動時間戳記 |
| SPZZ | 異動者 | A | - | - | R | 異動操作者 |

## 5. 主鍵欄位
- **主鍵**: SP02 + SP01 (轉帳單號 + 原始單號)
- **排序**: 複合索引，升序排列

## 6. 索引資料
| 索引名稱 | 欄位組合 | 索引類型 | 說明 |
|----------|----------|----------|------|
| Primary | SP02 + SP01 | 複合主鍵索引 | 轉帳單號與原始單號組合索引 |

## 7. 使用說明

### 7.1 檔案用途
- 轉帳單號導向查詢
- 單據對照關係管理
- 轉帳作業追蹤
- 沖銷記帳處理

### 7.2 程式存取方式
```rpg
// 按轉帳單號查詢
SETLL (轉帳單號) SOSPLF01;
READE (轉帳單號) SOSPLF01;
// 精確查詢
CHAIN (轉帳單號:原始單號) SOSPLF01;
```

### 7.3 檔案維護
- 配合轉帳作業維護
- 單據對照關係檢核
- 沖銷記帳狀態管理

## 8. 備註
- 此檔案基於SOSPPF實體檔案建立
- 提供轉帳單號為主的查詢功能
- 支援單據對照關係追蹤
- 轉帳單號為主要查詢鍵
- 原始單號為次要查詢鍵
- 適用於轉帳作業的單據管理
- 支援沖銷記帳標記功能
- 與會計系統配合處理轉帳作業 