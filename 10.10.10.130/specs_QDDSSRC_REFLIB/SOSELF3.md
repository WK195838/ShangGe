# SOSELF3 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSELF3
- **檔案類型**: LF (邏輯檔案)
- **基底檔案**: SOSEPF (送貨單主檔)
- **檔案說明**: 普銷送貨單主檔邏輯檔案 - 普銷業務專用
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此邏輯檔案專門用於普銷送貨單管理，提供完整的欄位定義與以送貨日期遞減排序的索引，支援普銷業務的詳細查詢與管理。

### 主要功能
- 普銷送貨單專業管理
- 普銷業務分析
- 普銷配送分析

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSEPF | PF | 送貨單主檔 (基底檔案) |
| SOSELF3 | LF | 普銷送貨單主檔邏輯檔案 |

## 4. 紀錄格式

### 4.1 邏輯檔案設定
```
PFILE(SOSEPF)      // 基底實體檔案
```

### 4.2 關鍵欄位 (Key Fields)
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SE06 | 送貨日期 | N | 8,0 | DESC | 降序排列 |
| 2 | SE02 | 送貨單號 | A | 10 | ASC | 次要排序鍵 |

### 4.3 計算欄位
| 欄位代號 | 計算公式 | 說明 |
|----------|----------|------|
| SE07L | SST(SE07 1 1) | 出貨訊息統計第一碼 |

### 4.4 選擇條件 (SELECT/OMIT)
| 類型 | 欄位代號 | 條件 | 值 | 說明 |
|------|----------|------|----|----|
| OMIT | SE07L | COMP(NE) | 'V' | 排除出貨訊息統計第一碼非 'V' (非普銷) |

### 4.5 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 型態 | 長度 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|
| SE01 | 客戶編號 | A | 10 | - | 客戶基本資料 |
| SE02 | 送貨單號 | A | 10 | Key | 送貨單唯一識別 |
| SE03 | 部門 | A | 5 | - | 業務部門 |
| SE06 | 送貨日期 | N | 8,0 | Key,DESC | 送貨執行日期 |
| SE07 | 出貨訊息統計 | A | 8 | - | 出貨狀態統計 |
| SE07L | 出貨訊息統計第一碼 | A | 1 | Computed | SST(SE07 1 1) |
| SE09 | 送貨檢驗狀態 | A | 1 | - | '*'=待驗收,'V'=已送貨確認,'C'=取消,' '=已驗收 |
| SE34 | 地區 | A | 5 | - | 配送地區代號 |
| SE35 | 通路 | A | 5 | - | 銷售通路代號 |
| SE38 | 轄區編號 | A | 1 | - | 'D'=高屏,'B'=北部,'Z'=桃園 |

## 5. 主鍵欄位
- **主要鍵值**: SE06 (送貨日期) + SE02 (送貨單號)
- **排序方式**: 送貨日期降序，送貨單號升序
- **索引類型**: 複合索引，普銷業務專用

## 6. 索引資料
- **排序方式**: SE06(遞減) + SE02
- **索引類型**: 復合索引，普銷業務專用
- **特殊屬性**: 送貨日期遞減排序

## 7. 使用說明

### 7.1 檔案用途
- 普銷送貨單專業管理
- 普銷業務管理
- 普銷配送分析相關程式

### 7.2 程式存取方式
```rpg
// 讀取最新普銷送貨記錄
SETLL (*HIVAL) SOSELF3;
READP SOSELF3;
// 依特定日期範圍讀取
SETLL (結束日期) SOSELF3;
READP SOSELF3;
```

## 8. 備註
- 此邏輯檔案專門服務普銷業務需求
- 提供完整的普銷送貨管理功能
- 支援普銷業務的精確分析與管理
- 專門處理普銷業務 (SE07L = 'V')
- 包含計算欄位 SE07L，提供普銷業務篩選功能 