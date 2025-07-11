# SOSGLF03 檔案規格書

## 1. 基本資料
- **檔案名稱**: SOSGLF03
- **檔案類型**: LF (邏輯檔案)
- **基底檔案**: SOSGPF (銷貨退回主檔)
- **檔案說明**: 銷貨退回主檔邏輯檔案 - 原發票追蹤查詢
- **建立日期**: (依系統記錄)
- **最後異動日期**: (依系統記錄)

## 2. 檔案功能說明
此邏輯檔案提供以原發票號為主的排序索引，支援銷貨退回按原發票追蹤的查詢需求。

### 主要功能
- 原發票退貨追蹤
- 發票退貨關聯查詢
- 退貨原因分析

## 3. 系統檔案清單
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSGPF | PF | 銷貨退回主檔 (基底檔案) |
| SOSGLF03 | LF | 銷貨退回主檔邏輯檔案 |

## 4. 紀錄格式

### 4.1 邏輯檔案設定
```
PFILE(SOSGPF)      // 基底實體檔案
```

### 4.2 關鍵欄位 (Key Fields)
| 順序 | 欄位代號 | 欄位名稱 | 型態 | 長度 | 排序 | 說明 |
|------|----------|----------|------|------|------|------|
| 1 | SG09 | 原發票號 | A | 15 | ASC | 主要排序鍵 |

### 4.3 選擇條件 (SELECT/OMIT)
無特殊選擇條件設定

## 5. 主鍵欄位
- **主要鍵值**: SG09 (原發票號)
- **排序方式**: 原發票號升序
- **索引類型**: 單一索引

## 6. 索引資料
- **排序方式**: SG09 (原發票號)
- **索引類型**: 單一索引，發票追蹤專用
- **特殊屬性**: 無特殊排序屬性

## 7. 使用說明

### 7.1 檔案用途
- 銷貨退回原發票追蹤
- 發票退貨追蹤
- 退貨原因分析

### 7.2 程式存取方式
```rpg
// 依原發票號查詢
SETLL (原發票號) SOSGLF03;
READ SOSGLF03;
// 直接讀取發票退貨記錄
CHAIN (原發票號) SOSGLF03;
```

## 8. 備註
- 此邏輯檔案專注於發票退貨的關聯管理
- 提供簡潔的發票追蹤功能
- 支援退貨與原發票的對應關係查詢
- 專門用於發票退貨關聯查詢 