# SOSNLF2 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSNLF2
- **檔案類型**: LF (邏輯檔案) - JOIN檔案
- **檔案說明**: 收回資料檔 - 產品收回聯結檔案
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)
- **檔案屬性**: DYNSLT, JFILE(SOSNPF SOSOPF MTMAPF)

## 2. 檔案功能說明
此聯結檔案整合產品收回主檔(SOSNPF)、產品收回明細檔(SOSOPF)及產品主檔(MTMAPF)，提供完整的產品收回資訊查詢。

### 主要功能
- 產品收回主檔與明細檔聯結
- 整合產品基本資料
- 排除過帳錯誤記錄
- 排除客戶編號為'K'的記錄
- 動態選擇條件支援

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSNLF2 | LF | 收回資料檔聯結檔案 |
| SOSNPF | PF | 產品收回主檔 (主要檔案) |
| SOSOPF | PF | 產品收回明細檔 (聯結檔案) |
| MTMAPF | PF | 產品主檔 (聯結檔案) |

## 4. 紀錄格式

### 4.1 記錄格式 SN0
```
DYNSLT
JFILE(SOSNPF SOSOPF MTMAPF)
JOIN(SOSNPF SOSOPF): JFLD(SN02 SO02)
JOIN(SOSOPF MTMAPF): JFLD(SO03 MA01)
SELECT: SN10 COMP(NE 'T'), SN01A COMP(NE 'K')
```

#### 聯結條件
| 聯結順序 | 主檔案 | 聯結檔案 | 聯結欄位 | 說明 |
|----------|--------|----------|----------|------|
| 1 | SOSNPF | SOSOPF | SN02=SO02 | 收回單號聯結 |
| 2 | SOSOPF | MTMAPF | SO03=MA01 | 商品代號聯結 |

#### 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 型態 | 長度 | 小數 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| **產品收回主檔欄位(SOSNPF)** |
| SN01 | 客戶編號 | A | - | - | R | 客戶基本資料參考 |
| SN01A | 客戶編號第一碼 | A | 1 | - | I | 計算欄位，SST(SN01 1 1) |
| SN02 | 收回單號 | A | - | - | R | 收回單唯一識別碼 |
| SN02A | 部門代號 | A | 2 | - | I | 計算欄位，SST(SN02 3 2) |
| SN03 | 出貨商品項目代號 | A | - | - | R | 原出貨商品項目 |
| SN06 | 收回入庫日 | N | 8 | 0 | R | 公司入庫處理日期 |
| SN10 | 過帳狀態 | A | 1 | - | R | 過帳處理狀態代碼，COMP(NE 'T') |
| SN16 | 應收退回 | N | 2 | - | A | 應收退回分類 |
| **產品收回明細檔欄位(SOSOPF)** |
| SO02 | 收回單號 | A | - | - | R | 收回單號(聯結鍵) |
| SO03 | 商品代號 | A | - | - | R | 商品項目代號(聯結鍵) |
| SO04 | 退回數量盒裝合計 | N | - | - | R | 退回數量統計 |
| SO05 | 確認數量 | N | - | - | R | 確認退回數量 |
| SO06 | 退回數量瓶裝量計 | N | - | - | R | 瓶裝數量統計 |
| SO07 | 退回數量瓶裝重計 | N | - | - | R | 瓶裝重量統計 |
| **產品主檔欄位(MTMAPF)** |
| MA01 | 產品代號 | A | - | - | R | 產品基本代號(聯結鍵) |
| MA07 | 產品名稱 | A | - | - | R | 產品中文名稱 |
| MA11 | 產品規格 | A | - | - | R | 產品規格說明 |
| MA15 | 產品分類 | A | - | - | R | 產品分類代號 |
| MA54 | 產品單位 | A | - | - | R | 計量單位 |

## 5. 主鍵欄位
- **無明確主鍵**：聯結檔案依聯結條件組合
- **存取方式**：動態選擇條件

## 6. 索引資料
| 索引名稱 | 欄位組合 | 索引類型 | 說明 |
|----------|----------|----------|------|
| Join Index | SN02, SO03, MA01 | 聯結索引 | 三檔聯結索引 |

## 7. 使用說明

### 7.1 檔案用途
- 產品收回完整資訊查詢
- 收回商品與產品基本資料整合
- 退回商品分析報表
- 收回明細與產品規格對照

### 7.2 程式存取方式
```rpg
// 順序讀取聯結記錄
READ SOSNLF2;
// 條件查詢
IF SN10 <> 'T' AND SN01A <> 'K';
  // 處理有效記錄
ENDIF;
```

### 7.3 選擇條件
- 過帳狀態不等於'T'(過帳錯誤)
- 客戶編號第一碼不等於'K'
- 動態選擇條件支援

## 8. 備註
- 此檔案為三檔聯結的邏輯檔案
- 使用DYNSLT動態選擇功能
- 自動排除過帳錯誤記錄，確保資料正確性
- 排除特定客戶('K'開頭)，專注一般客戶
- 整合產品基本資料，提供完整收回資訊
- M001修改記錄：新增應收退回分類欄位
- 適用於需要產品詳細資訊的收回分析作業
- 支援複雜的收回資料查詢需求 