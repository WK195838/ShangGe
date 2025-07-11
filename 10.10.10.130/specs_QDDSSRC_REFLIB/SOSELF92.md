# SOSELF92 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSELF92
- **檔案類型**: LF (邏輯檔案)
- **基底檔案**: SOSEPF (送貨單主檔)
- **檔案說明**: 送貨單主檔邏輯檔案 - WDS020A 程式專用
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此邏輯檔案專門為 WDS020A 程式提供服務，處理待驗收且已配送確認的送貨單，提供多重排序索引支援。

### 主要功能
- WDS020A 程式專用查詢
- 特定狀態組合篩選
- 特殊業務需求支援

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSEPF | PF | 送貨單主檔 (基底檔案) |
| SOSELF92 | LF | 送貨單主檔邏輯檔案 |

## 4. 紀錄格式

### 4.1 邏輯檔案設定
```
PFILE(SOSEPF)      // 基底實體檔案
```

### 4.2 關鍵欄位 (Key Fields)
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SE06 | 送貨日期 | N | 8,0 | ASC | 主要排序鍵 |
| 2 | SE02 | 送貨單號 | A | 10 | ASC | 次要排序鍵 |
| 3 | SE07 | 出貨訊息統計 | A | 8 | ASC | 第三排序鍵 |

### 4.3 選擇條件 (SELECT/OMIT)
| 類型 | 欄位代號 | 條件 | 值 | 說明 |
|------|----------|------|----|----|
| OMIT | SE09 | COMP(EQ) | '*' | 排除送貨檢驗狀態為待驗收 |
| OMIT | SE36 | COMP(EQ) | 'T' | 排除核准狀態為配送鍊狀態 |
| SELECT | SE31 | COMP(EQ) | ' ' | 選擇發貨狀態為空白 |
| SELECT | SE31 | COMP(EQ) | 'C' | 或選擇發貨狀態為取消 |

## 5. 主鍵欄位
- **主要鍵值**: SE06 (送貨日期) + SE02 (送貨單號) + SE07 (出貨訊息統計)
- **排序方式**: 送貨日期、送貨單號、出貨訊息統計升序
- **索引類型**: 複合索引

## 6. 索引資料
- **排序方式**: SE06 + SE02 + SE07
- **索引類型**: 復合索引，WDS020A 專用
- **特殊屬性**: 無特殊排序屬性

## 7. 使用說明

### 7.1 檔案用途
- WDS020A 程式專用送貨單查詢
- 特定狀態組合篩選
- 特殊業務流程支援

### 7.2 程式存取方式
```rpg
// 依送貨日期查詢
SETLL (送貨日期) SOSELF92;
READ SOSELF92;
// 依送貨日期和送貨單號查詢
CHAIN (送貨日期:送貨單號) SOSELF92;
```

### 7.3 業務邏輯說明
此檔案專門處理以下狀態組合的送貨單：
- **SE09 ≠ '*'**: 送貨檢驗狀態非待驗收
- **SE36 ≠ 'T'**: 核准狀態非配送鍊狀態
- **SE31 = ' ' 或 'C'**: 發貨狀態為空白或取消

### 7.4 適用場景
- 已完成驗收但尚未發貨的送貨單
- 已取消發貨的送貨單
- WDS020A 程式的特定業務需求

## 8. 備註
- 此邏輯檔案專門服務 WDS020A 程式
- 提供特定狀態篩選功能
- 支援特殊業務流程需求
- 專門為特定程式設計的邏輯檔案 