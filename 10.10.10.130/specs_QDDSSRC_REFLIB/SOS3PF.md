# SOS3PF 檔案規格書

## 1. 基本資料

| 欄位 | 內容 |
|------|------|
| 檔案名稱 | SOS3PF |
| 檔案描述 | 促銷活動代碼檔 |
| 檔案類型 | 實體檔案 (PF) |
| 記錄格式 | S30 |
| 關鍵字 | S301 |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |
| 存取方式 | 索引存取 |

## 2. 檔案功能說明

促銷活動代碼檔是促銷管理系統的基礎主檔，記錄各種促銷活動的代碼與識別資訊。本檔案採用簡化設計，主要管理促銷活動的基本代碼，為促銷相關業務提供標準化的活動識別基礎。

## 3. 系統檔案清單

| 相關檔案 | 檔案名稱 | 說明 |
|----------|----------|------|
| 主檔案 | SOS3PF | 促銷活動代碼檔 |

## 4. 紀錄格式

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| S301 | 促銷活動代碼 | 1-12 | 12 | 文字 | 主鍵 | 促銷活動識別代碼 |

## 5. 主鍵欄位

- **主鍵**：S301 (促銷活動代碼)
- **索引類型**：UNIQUE
- **排序方式**：遞增排序

## 6. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| PRIMARY | S301 | UNIQUE | 主索引，促銷活動代碼 |

## 7. 使用說明

1. **活動代碼管理**：維護促銷活動的標準代碼
2. **基礎資料設定**：提供促銷系統的基礎代碼設定
3. **資料查詢**：支援按活動代碼快速查詢
4. **系統整合**：與其他促銷相關檔案整合使用
5. **代碼標準化**：確保促銷活動代碼的一致性

## 8. 備註

- 採用極簡設計，僅包含促銷活動代碼欄位
- 活動代碼採用12位文字格式，支援多樣化編碼規則
- 使用UNIQUE屬性確保活動代碼的唯一性
- 作為促銷管理系統的基礎主檔
- 可配合其他業務檔案建立完整的促銷活動管理體系 