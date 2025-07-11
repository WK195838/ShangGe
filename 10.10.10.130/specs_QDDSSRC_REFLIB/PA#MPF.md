# PA#MPF 檔案規格書

## 1. 基本資料
- **檔案名稱**: PA#MPF
- **檔案描述**: 銷售大區域地區資料檔
- **檔案類型**: PF (Physical File)
- **記錄格式**: #M0
- **建立日期**: [依實際建立日期填入]
- **最後修改日期**: [依實際修改日期填入]

## 2. 檔案功能說明
本檔案用於儲存銷售大區域與地區的對應關係資料，建立區域階層結構。

## 3. 系統檔案清單
| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | PA#MPF | PF | 銷售大區域地區資料檔主檔 |
| 2 | PA#MLF | LF | 銷售大區域地區資料檔邏輯檔 |

## 4. 記錄格式
**記錄格式名稱**: #M0

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|----------|
| #M01 | 大區域代號 | 1 | 2 | A | REF(#D01) | 參照地區代號欄位 |
| #M02 | 地區代號 | 3 | 2 | A | REF(#D01) | 參照地區代號欄位 |
| #M03 | 地區描述 | 5 | 22 | O | REF(#D02) | 參照地區描述欄位 |
| #MXX | 建立日期 | 27 | 8 | 0 | REF(#AXX) | 建立日期 |
| #MYY | 建立時間 | 35 | 6 | 0 | REF(#AYY) | 建立時間 |
| #MZZ | 建立者 | 41 | 10 | A | REF(#AZZ) | 建立者代碼 |

## 6. 主鍵欄位
- **複合主鍵**: #M01 + #M02 (大區域代號 + 地區代號)

## 7. 索引資料
- **唯一鍵**: #M01 + #M02 (大區域代號 + 地區代號)
- **檔案特性**: UNIQUE

## 8. 備註
- 本檔案參考 RERF 檔案的欄位定義
- 檔案具有唯一性約束
- #MXX 欄位標示為 B2CHKA，表示可能需要特殊檢查
- 建立大區域與地區的階層關係對應表 