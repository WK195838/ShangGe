# SOSILF96 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSILF96
- **檔案類型**: LF (邏輯檔案)
- **基底檔案**: SOSIPF (發票主檔)
- **檔案說明**: 發票主檔邏輯檔案 - 視窗查詢零應收發票專用
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此邏輯檔案提供客戶編號、發票號碼的基本排序，並設有OMIT條件與SELECT條件，專門用於視窗介面的零應收金額發票查詢，適用於已結清或無應收餘額的發票管理。

### 主要功能
- 視窗介面零應收發票查詢
- 應收金額為零的發票篩選
- 發票號碼範圍限制
- 已結清發票管理

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSIPF | PF | 發票主檔 (基底檔案) |
| SOSILF96 | LF | 發票主檔邏輯檔案 |

## 4. 紀錄格式

### 4.1 邏輯檔案設定
```
PFILE(SOSIPF)      // 基底實體檔案
```

### 4.2 關鍵欄位 (Key Fields)
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SI01 | 客戶編號 | A | 10 | ASC | 主要排序鍵 |
| 2 | SI02 | 發票號碼 | A | 10 | ASC | 次要排序鍵 |

### 4.3 選擇條件 (SELECT/OMIT)
#### OMIT條件 (排除以下情況)
| 條件類型 | 欄位代號 | 條件 | 值 | 說明 |
|----------|----------|------|----|----|
| OMIT | SI02 | RANGE | '**        ' to '**99999999' | 排除特殊發票號碼範圍 |
| OMIT | SI30 | COMP | EQ 0 | 排除應收金額為零的發票 |

#### SELECT條件
| 條件類型 | 欄位代號 | 條件 | 值 | 說明 |
|----------|----------|------|----|----|
| SELECT | SI18 | COMP | EQ ' ' | 狀態正常 |
| SELECT | SI19 | COMP | EQ ' ' | 非重開發票 |

### 4.4 篩選邏輯說明
#### 排除條件詳解
| 排除類型 | 說明 |
|----------|------|
| 特殊號碼 | 排除以'**'開頭的發票號碼 |
| 零應收金額 | 排除SI30=0的發票 |

#### 保留條件 (AND邏輯)
| 條件 | 說明 |
|------|------|
| SI18=' ' | 狀態正常的發票 |
| SI19=' ' | 原始發票 (非重開) |

### 4.5 應收金額管理特色
此檔案專門查詢有應收餘額的正常發票，排除已結清的發票

## 5. 主鍵欄位
- **主要鍵值**: SI01 + SI02
- **排序方式**: 客戶編號、發票號碼升序
- **索引類型**: 複合索引，客戶導向

## 6. 索引資料
- **排序方式**: SI01 + SI02
- **索引類型**: 復合索引，支援應收金額視窗查詢
- **特殊屬性**: 應收金額篩選，非零金額專用

## 7. 使用說明

### 7.1 檔案用途
- 視窗介面應收發票查詢
- 有應收餘額發票清單顯示
- 客戶未收款發票瀏覽
- 催收作業支援

### 7.2 程式存取方式
```rpg
// 視窗客戶應收發票查詢
SETLL (客戶編號) SOSILF96;
READ SOSILF96;
// 視窗應收發票清單顯示
DOW NOT %EOF(SOSILF96) AND SI01 = 客戶編號;
  // 顯示有應收餘額的發票
  READ SOSILF96;
ENDDO;
```

### 7.3 應收管理特色
- **金額篩選**: 只顯示有應收餘額的發票 (SI30≠0)
- **狀態保證**: 只顯示正常狀態的原始發票
- **範圍限制**: 排除系統內部發票號碼
- **催收支援**: 適合應收帳款催收作業

### 7.4 與其他檔案比較
| 項目 | SOSILF91 | SOSILF96 |
|------|----------|----------|
| 排序方式 | 地址+日期降序 | 客戶+發票號碼 |
| 應收條件 | SI30≠0 | 排除SI30=0 |
| 主要用途 | 地址應收管理 | 視窗應收查詢 |

### 7.5 應收帳款應用
- **餘額管理**: 專門管理有應收餘額的發票
- **視窗友善**: 適合視窗介面操作
- **催收作業**: 支援客戶應收帳款催收

## 8. 備註
- 此邏輯檔案專為視窗介面應收管理設計
- 透過OMIT條件排除零應收金額，確保查詢結果都有應收餘額
- 適用於應收帳款管理與催收作業
- 與應收相關的其他邏輯檔案形成完整的應收管理體系 