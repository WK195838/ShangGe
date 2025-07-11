# PA#4PF 檔案規格書

## 1. 基本資料
- **檔案名稱**: PA#4PF
- **檔案描述**: 部門成本中心對照資料檔
- **檔案類型**: PF (Physical File)
- **記錄格式**: #40
- **建立日期**: [依實際建立日期填入]
- **最後修改日期**: [依實際修改日期填入]

## 2. 檔案功能說明
本檔案用於儲存部門與成本中心的對應關係資料，建立部門成本管理的基礎對照表。

## 3. 系統檔案清單
| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | PA#4PF | PF | 部門成本中心對照資料檔主檔 |
| 2 | PA#4LF | LF | 部門成本中心對照資料檔邏輯檔 |

## 4. 記錄格式
**記錄格式名稱**: #40

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|----------|
| #401 | 部門代號 | 1 | 5 | A | REF(ME01) | 參照部門檔案 |
| #402 | 成本代號 | 6 | 4 | A | REF(ME02) | 參照成本檔案 |
| #403 | 成本中心 | 10 | 6 | A | REF(#A0/#A01 GLFLIB/PT#APF) | 參照成本中心檔案 |
| #4XX | 建立日期 | 16 | 8 | 0 | REF(#AXX) | 建立日期 |
| #4YY | 建立時間 | 24 | 6 | 0 | REF(#AYY) | 建立時間 |
| #4ZZ | 建立者 | 30 | 10 | A | REF(#AZZ) | 建立者代碼 |

## 6. 主鍵欄位
- **複合主鍵**: #401 + #402 (部門代號 + 成本代號)

## 7. 索引資料
- **唯一鍵**: #401 + #402 (部門代號 + 成本代號)
- **檔案特性**: UNIQUE

## 8. 備註
- 本檔案參考 RERF 檔案的欄位定義
- 檔案具有唯一性約束
- #4XX 欄位標示為 B2CHKA，表示可能需要特殊檢查
- #401 參照 ME01 欄位 (部門檔案)
- #402 參照 ME02 欄位 (成本檔案)
- #403 參照外部檔案 GLFLIB/PT#APF 的成本中心資料
- 建立部門與成本中心的對應關係 