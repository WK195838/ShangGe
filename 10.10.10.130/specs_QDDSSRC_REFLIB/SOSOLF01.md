# SOSOLF01 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSOLF01
- **檔案類型**: LF (邏輯檔案)
- **檔案說明**: 產品收回明細檔 - 收回單號商品類別排序邏輯檔
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)
- **檔案屬性**: PFILE(SOSOPF)

## 2. 檔案功能說明
此邏輯檔案基於SOSOPF實體檔案建立，提供以收回單號、商品類別、商品代號組合排序的查詢功能。

### 主要功能
- 按收回單號分組查詢明細
- 商品類別分類排序
- 商品代號細分排序
- 收回明細結構化瀏覽

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSOLF01 | LF | 產品收回明細檔收回單號排序邏輯檔 |
| SOSOPF | PF | 產品收回明細檔 (實體檔案) |

## 4. 紀錄格式

### 4.1 記錄格式 SO0
```
PFILE(SOSOPF)
KEY: SO02 + SO11 + SO03
```

#### 關鍵欄位
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SO02 | 收回單號 | A | - | ASC | 主要排序鍵 |
| 2 | SO11 | 商品類別 | A | - | ASC | 次要排序鍵 |
| 3 | SO03 | 商品代號 | A | - | ASC | 第三排序鍵 |

#### 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 型態 | 長度 | 小數 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| SO01 | 客戶編號 | A | - | - | R | 客戶基本資料參考 |
| SO02 | 收回單號 | A | - | - | R | 收回單唯一識別碼，主要排序鍵 |
| SO03 | 商品代號 | A | - | - | R | 商品項目代號，第三排序鍵 |
| SO04 | 退回數量盒裝合計 | N | - | - | R | 退回數量統計 |
| SO05 | 確認數量 | N | - | - | R | 確認退回數量 |
| SO06 | 退回數量瓶裝量計 | N | - | - | R | 瓶裝數量統計 |
| SO07 | 退回數量瓶裝重計 | N | - | - | R | 瓶裝重量統計 |
| SO08 | 退回日期 | N | 8 | 0 | R | 退回處理日期 |
| SO09 | 出貨商品項目代號 | A | - | - | R | 原出貨商品項目 |
| SO10 | 退貨商品項目代號 | A | - | - | R | 退回商品項目 |
| SO11 | 商品類別 | A | - | - | R | 商品分類代號，次要排序鍵 |
| SO12 | 溫層 | A | - | - | R | 產品溫度層級 |
| SO13 | 應付FOB-TOT | N | - | - | R | FOB價格總計 |
| SO14 | 應付FHI-TOT | N | - | - | R | FHI價格總計 |
| SO15 | 應付DUTY-TOT | N | - | - | R | 關稅總計 |
| SO16 | 退回FOB-TOT | N | - | - | R | 退回FOB價格總計 |
| SO17 | 退回FHI-TOT | N | - | - | R | 退回FHI價格總計 |
| SO18 | 退回DUTY-TOT | N | - | - | R | 退回關稅總計 |
| SO19-SO27 | 備註欄位 | - | - | - | A | 備註、數值、旗標等擴充欄位 |
| SO99 | 記帳單位 | A | 2 | - | A | 記帳單位代號 |
| SO98 | 記帳類別 | A | 1 | - | A | 記帳分類代號 |
| SOXX | 異動人員 | A | 8 | 0 | R | 異動人員代號 |
| SOYY | 異動時間 | N | - | - | R | 異動時間戳記 |
| SOZZ | 異動者 | A | - | - | R | 異動操作者 |

## 5. 主鍵欄位
- **主鍵**: SO02 + SO11 + SO03 (收回單號 + 商品類別 + 商品代號)
- **排序**: 三層複合索引，升序排列

## 6. 索引資料
| 索引名稱 | 欄位組合 | 索引類型 | 說明 |
|----------|----------|----------|------|
| Primary | SO02 + SO11 + SO03 | 複合主鍵索引 | 收回單號、商品類別、商品代號組合索引 |

## 7. 使用說明

### 7.1 檔案用途
- 按收回單號分組查詢明細
- 商品類別統計分析
- 收回明細結構化瀏覽
- 商品分類退回報表

### 7.2 程式存取方式
```rpg
// 按收回單號查詢所有明細
SETLL (收回單號) SOSOLF01;
READE (收回單號) SOSOLF01;
// 按收回單號和商品類別查詢
SETLL (收回單號:商品類別) SOSOLF01;
READE (收回單號:商品類別) SOSOLF01;
// 精確查詢
CHAIN (收回單號:商品類別:商品代號) SOSOLF01;
```

### 7.3 檔案維護
- 配合商品主檔維護作業
- 支援商品分類報表產生
- 收回明細結構化查詢

## 8. 備註
- 此檔案基於SOSOPF實體檔案建立
- 提供三層排序的結構化查詢功能
- 收回單號為主要分組鍵
- 商品類別為次要分組鍵
- 商品代號為最終排序鍵
- 適用於需要按商品分類分析的收回作業
- 支援分層統計與分析需求
- 與產品主檔配合提供完整商品資訊 