﻿# RERF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | RERF |
| 檔案類型 | 參考檔案 (Reference File) |
| 檔案用途 | 系統欄位定義參考檔 |
| 紀錄格式 | RERFR |
| 資料庫 | REFLIB |
| 檔案特性 | 系統參考檔案 |
| 建立日期 | - |
| 最後修改日期 | - |

## 2. 檔案功能說明

RERF 是整個系統最重要的參考檔案，為所有系統檔案提供欄位定義和屬性參考。

## 3. 系統檔案清單

### 主要參考檔案
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| RERF | 參考檔案 | 系統欄位定義參考檔（本檔案） |

## 4. 紀錄格式

### 記錄格式：RERFR
- **記錄類型**：參考記錄
- **用途**：提供系統所有欄位的定義規格
- **特性**：包含完整的欄位屬性定義

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

### 5.1 系統參數檔案欄位定義 (#___)

RERF 包含所有系統檔案的欄位定義，主要包括：
- 進貨系統欄位 (POP___)
- 銷貨系統欄位 (SOS___)
- 庫存系統欄位 (IMI___)
- 應收帳款系統欄位 (ARA___)
- 主檔系統欄位 (MTM___)
- 參數設定系統欄位 (PA#___)

## 6. 主鍵欄位

RERF 為參考檔案，不具有實體記錄，因此無主鍵欄位。所有欄位定義均為其他檔案提供參考規格。

## 7. 索引資料

RERF 為參考檔案，不具有索引結構。

## 8. 備註

### 8.1 檔案特性
- **系統核心**：RERF 是整個系統的核心參考檔案，所有檔案的欄位定義都依賴此檔案
- **統一標準**：確保系統中相同性質的欄位具有一致的定義和格式
- **維護重要性**：任何對 RERF 的修改都會影響整個系統，需要特別謹慎

### 8.2 欄位屬性說明
- **R**：參考其他欄位定義
- **O**：輸出專用欄位
- **K**：主鍵欄位
- **B2CHKA**：日期檢查
- **B2MODA**：年月檢查

### 8.3 系統關聯
- 所有實體檔案都使用 REF(RERF) 來定義欄位屬性
- 邏輯檔案透過實體檔案間接使用 RERF 的定義
- 螢幕檔案使用 REFFLD 來參考 RERF 中的欄位定義
