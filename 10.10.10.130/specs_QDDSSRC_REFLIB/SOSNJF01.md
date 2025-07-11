# SOSNJF01 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSNJF01
- **檔案類型**: JF (聯結檔案)
- **基底檔案**: SOSNPF (產品收回主檔), PA#IPF (產品主檔)
- **檔案說明**: 產品收回聯結檔 - 自動作業聯結檔案
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此聯結檔案將產品收回主檔 (SOSNPF) 與產品主檔 (PA#IPF) 進行聯結，提供完整的產品收回與產品基本資料整合查詢，支援自動作業處理。

### 主要功能
- 產品收回與產品資料整合查詢
- 自動作業處理支援
- 產品收回詳細資訊分析

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSNPF | PF | 產品收回主檔 (主要檔案) |
| PA#IPF | PF | 產品主檔 (次要檔案) |
| SOSNJF01 | JF | 產品收回聯結檔案 |

## 4. 紀錄格式

### 4.1 記錄格式 SN0
```
JFILE(SOSNPF PA#IPF)
JFLD(SN02 #I01)
KEY: SN02
```

#### 聯結規格
| 主檔案 | 次檔案 | 聯結欄位 | 聯結類型 | 說明 |
|--------|--------|----------|----------|------|
| SOSNPF | PA#IPF | SN02 = #I01 | INNER | 收回單號與產品編號聯結 |

#### 關鍵欄位
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SN02 | 收回單號 | A | - | ASC | 主要排序鍵 |

#### 欄位代號、名稱、位置、長度、屬性、檢核說明

##### 產品收回主檔 (SOSNPF) 欄位
| 欄位代號 | 欄位名稱 | 來源欄位 | 型態 | 長度 | 屬性 | 檢核說明 |
|----------|----------|----------|------|------|------|----------|
| SN01 | 客戶編號 | SN01 | A | - | R | 客戶基本資料 |
| SN02 | 收回單號 | SN02 | A | - | Key,R | 收回單唯一識別 |
| SN03 | 出貨商品項目代號 | SN03 | A | - | R | 商品項目代號 |
| SN04 | 退貨商品項目代號 | SN04 | A | - | R | 退貨項目代號 |
| SN05 | 退回日期 | SN05 | N | 8,0 | R | 產品退回日期 |
| SN06 | 收回入庫日 | SN06 | N | 8,0 | R | 入庫處理日期 |
| SN07 | 業務人員 | SN07 | A | - | R | 負責業務人員 |
| SN08 | 業務備註欄位 | SN08 | A | - | R | 業務說明 |
| SN09 | 檢驗狀態 | SN09 | A | 1 | R | 檢驗結果狀態 |
| SN10 | 過帳狀態 | SN10 | A | 1 | R | 過帳處理狀態 |
| SN11 | 客戶地址 | SN11 | A | - | R | 客戶地址 |
| SN12 | 退回溫層 | SN12 | A | - | R | 溫度層級 |
| SN13 | 退回FOB-TOT | SN13 | N | - | R | FOB總金額 |
| SN14 | 退回FHI-TOT | SN14 | N | - | R | FHI總金額 |
| SN15 | 退回DUTY-TOT | SN15 | N | - | R | DUTY總金額 |
| SNXX | 異動人員 | SNXX | A | - | R | 異動人員代號 |
| SNYY | 異動時間 | SNYY | N | - | R | 異動時間戳記 |
| SNZZ | 異動者 | SNZZ | A | - | R | 異動操作者 |

##### 產品主檔 (PA#IPF) 欄位
| 欄位代號 | 欄位名稱 | 來源欄位 | 型態 | 長度 | 屬性 | 檢核說明 |
|----------|----------|----------|------|------|------|----------|
| #I01 | 部門 | #I01 | A | - | R | 產品部門分類 |
| #I02 | 確認業務 | #I02 | A | - | R | 確認業務類型 |
| #I03 | 確認區間 | #I03 | A | - | R | 確認區間設定 |
| #IXX | 異動人員 | #IXX | A | - | R | 異動人員代號 |
| #IYY | 異動時間 | #IYY | N | - | R | 異動時間戳記 |
| #IZZ | 異動者 | #IZZ | A | - | R | 異動操作者 |

## 5. 主鍵欄位
- **SN0 記錄格式**: SN02 (收回單號)

## 6. 索引資料
| 排序方式 | 索引類型 | 說明 |
|----------|----------|------|
| SN02 | 單一索引 | 收回單號排序 |

## 7. 使用說明

### 7.1 檔案用途
- 產品收回與產品資料整合查詢
- 自動作業處理支援
- 產品收回詳細資訊分析
- 產品退回處理流程管理

### 7.2 程式存取方式
```rpg
// 查詢收回單與產品資料
SETLL (收回單號) SOSNJF01;
READ SOSNJF01;
// 批次處理收回資料
SETLL (*LOVAL) SOSNJF01;
READ SOSNJF01;
```

### 7.3 聯結條件
- 主檔案：SOSNPF (產品收回主檔)
- 次檔案：PA#IPF (產品主檔)
- 聯結欄位：SN02 = #I01 (收回單號 = 產品編號)
- 聯結屬性：JDFTVAL (預設值聯結)

## 8. 備註
- 此檔案採用 JDFTVAL 聯結屬性，提供預設值處理
- 聯結產品收回與產品基本資料，提供完整資訊視圖
- 支援自動作業處理，適用於批次作業
- 狀態說明：
  - SN09 檢驗狀態：'V'=已檢驗
  - SN10 過帳狀態：'V'=已過帳, 'T'=過帳錯誤, 'N'=未處理過帳
- 包含完整的異動追蹤機制 (人員/時間/操作者)
- 適用於產品收回流程的完整管理和分析 