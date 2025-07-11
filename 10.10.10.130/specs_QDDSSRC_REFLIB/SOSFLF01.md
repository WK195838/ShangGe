# SOSFLF01 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSFLF01
- **檔案類型**: LF (邏輯檔案)
- **基底檔案**: SOSFPF (送貨單明細檔)
- **檔案說明**: 送貨單明細檔邏輯檔案 - 訂單產品查詢
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此邏輯檔案提供以訂購單編號、產品類型編號、產品編號為主的排序索引，支援送貨單明細按訂單產品組合的查詢需求。

### 主要功能
- 訂單產品明細查詢
- 產品類型分類管理
- 訂單執行狀態追蹤

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSFPF | PF | 送貨單明細檔 (基底檔案) |
| SOSFLF01 | LF | 送貨單明細檔邏輯檔案 |

## 4. 紀錄格式

### 4.1 邏輯檔案設定
```
PFILE(SOSFPF)      // 基底實體檔案
```

### 4.2 關鍵欄位 (Key Fields)
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SF02 | 訂購單編號 | A | 10 | ASC | 主要排序鍵 |
| 2 | SF16 | 產品類型編號 | A | 5 | ASC | 次要排序鍵 |
| 3 | SF03 | 產品編號 | A | 15 | ASC | 第三排序鍵 |

### 4.3 選擇條件 (SELECT/OMIT)
無特殊選擇條件設定

## 5. 主鍵欄位
- **主要鍵值**: SF02 + SF16 + SF03
- **排序方式**: 訂購單編號、產品類型編號、產品編號升序
- **索引類型**: 複合索引

## 6. 索引資料
- **排序方式**: SF02 + SF16 + SF03
- **索引類型**: 復合索引，支援訂單產品查詢
- **特殊屬性**: 無特殊排序屬性

## 7. 使用說明

### 7.1 檔案用途
- 送貨單明細按訂單產品查詢
- 訂單明細追蹤
- 產品配送分析

### 7.2 程式存取方式
```rpg
// 依訂購單編號查詢
SETLL (訂購單編號) SOSFLF01;
READ SOSFLF01;
// 依訂購單編號和產品類型查詢
CHAIN (訂購單編號:產品類型編號) SOSFLF01;
```

## 8. 備註
- 此邏輯檔案專注於訂單產品明細管理
- 提供簡潔高效的查詢結構
- 支援產品配送狀態追蹤
- 提供訂單導向的產品明細查詢功能 