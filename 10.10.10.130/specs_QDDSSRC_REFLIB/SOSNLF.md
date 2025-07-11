# SOSNLF 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSNLF
- **檔案類型**: LF (邏輯檔案)
- **基底檔案**: SOSNPF (產品收回主檔)
- **檔案說明**: 產品收回主檔邏輯檔 - 基本存取路徑
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此邏輯檔案基於產品收回主檔 (SOSNPF) 建立，採用參考存取路徑 (REFACCPTH) 設計，提供標準的產品收回資料查詢介面。

### 主要功能
- 產品收回基本資料查詢
- 標準存取路徑提供
- 系統整合介面

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSNPF | PF | 產品收回主檔 (基底檔案) |
| SOSNLF | LF | 產品收回主檔邏輯檔案 |

## 4. 紀錄格式

### 4.1 記錄格式 SN0
```
PFILE(SOSNPF)
REFACCPTH(SOSNPF)
```

#### 關鍵欄位
與基底檔案 SOSNPF 相同，依實體檔案主鍵定義：
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SN02 | 收回單號 | A | - | ASC | 主要排序鍵 |

#### 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 來源欄位 | 型態 | 長度 | 屬性 | 檢核說明 |
|----------|----------|----------|------|------|------|----------|
| SN01 | 客戶編號 | SN01 | A | - | PFILE | 客戶基本資料 |
| SN02 | 收回單號 | SN02 | A | - | Key,PFILE | 收回單唯一識別 |
| SN03 | 出貨商品項目代號 | SN03 | A | - | PFILE | 商品項目代號 |
| SN04 | 退貨商品項目代號 | SN04 | A | - | PFILE | 退貨項目代號 |
| SN05 | 退回日期 | SN05 | N | 8,0 | PFILE | 產品退回日期 |
| SN06 | 收回入庫日 | SN06 | N | 8,0 | PFILE | 入庫處理日期 |
| SN07 | 業務人員 | SN07 | A | - | PFILE | 負責業務人員 |
| SN08 | 業務備註欄位 | SN08 | A | - | PFILE | 業務說明 |
| SN09 | 檢驗狀態 | SN09 | A | 1 | PFILE | 檢驗結果狀態 |
| SN10 | 過帳狀態 | SN10 | A | 1 | PFILE | 過帳處理狀態 |
| SN11 | 客戶地址 | SN11 | A | - | PFILE | 客戶地址 |
| SN12 | 退回溫層 | SN12 | A | - | PFILE | 溫度層級 |
| SN13 | 退回FOB-TOT | SN13 | N | - | PFILE | FOB總金額 |
| SN14 | 退回FHI-TOT | SN14 | N | - | PFILE | FHI總金額 |
| SN15 | 退回DUTY-TOT | SN15 | N | - | PFILE | DUTY總金額 |
| SNXX | 異動人員 | SNXX | A | - | PFILE | 異動人員代號 |
| SNYY | 異動時間 | SNYY | N | - | PFILE | 異動時間戳記 |
| SNZZ | 異動者 | SNZZ | A | - | PFILE | 異動操作者 |

## 5. 主鍵欄位
- **SN0 記錄格式**: SN02 (收回單號)

## 6. 索引資料
| 排序方式 | 索引類型 | 說明 |
|----------|----------|------|
| REFACCPTH | 參考存取路徑 | 參考實體檔案存取路徑 |

## 7. 使用說明

### 7.1 檔案用途
- 產品收回基本資料查詢
- 標準存取路徑提供
- 系統整合介面
- 程式開發標準化存取

### 7.2 程式存取方式
```rpg
// 查詢收回資料
SETLL (收回單號) SOSNLF;
READ SOSNLF;
// 順序讀取所有記錄
SETLL (*LOVAL) SOSNLF;
READ SOSNLF;
```

### 7.3 存取路徑特性
- 採用 REFACCPTH(SOSNPF) 設計
- 繼承實體檔案的存取路徑
- 提供標準化的查詢介面

## 8. 備註
- 此檔案為標準邏輯檔案，採用參考存取路徑設計
- 直接對應實體檔案 SOSNPF 的所有欄位和索引
- 適用於系統整合和標準化存取需求
- 狀態說明：
  - SN09 檢驗狀態：'V'=已檢驗
  - SN10 過帳狀態：'V'=已過帳, 'T'=過帳錯誤, 'N'=未處理過帳
- 提供與實體檔案相同的功能，但允許更靈活的存取控制
- 主要用於產品收回資料的標準化查詢和系統整合 