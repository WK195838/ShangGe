# IMIRLF14 資料庫檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | IMIRLF14 |
| 檔案類型 | LF (邏輯檔案) |
| 檔案說明 | 庫存異動明細檔 - 參考存取路徑 |
| 參考存取路徑 | IMIRLF13 |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |

## 2. 檔案功能說明

IMIRLF14 是庫存異動明細檔的邏輯檔案，採用參考存取路徑 (REFACCPTH) 技術，直接參考 IMIRLF13 的索引結構。此檔案整合了18種不同的記錄格式，涵蓋採購、銷售、調撥、調整等各種庫存異動作業，提供完整的庫存異動歷史記錄查詢功能。

## 3. 系統檔案清單

整合18種記錄格式，包含採購、銷售、調撥、調整、報廢、組拆等業務流程。

## 4. 記錄格式

採用標準化欄位結構，包含異動類別、產品代號、數量、成本等欄位。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

標準化欄位定義，支援多種業務流程的異動記錄。

## 6. 主鍵欄位

使用參考存取路徑 IMIRLF13 的索引結構。

## 7. 索引資料

參考存取路徑: IMIRLF13，月份篩選條件: IR051 < '0'

## 8. 備註

採用參考存取路徑技術，整合18種記錄格式，提供完整的庫存異動查詢功能。
