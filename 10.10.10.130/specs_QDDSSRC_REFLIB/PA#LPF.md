# PA#LPF 檔案規格書

## 1. 基本資料
- **檔案名稱**: PA#LPF
- **檔案描述**: 銷售大區域資料檔
- **檔案類型**: PF (Physical File)
- **記錄格式**: #L0
- **建立日期**: [依實際建立日期填入]
- **最後修改日期**: [依實際修改日期填入]

## 2. 檔案功能說明
本檔案用於儲存銷售大區域的基本資料，包含區域代號、描述等資訊。

## 3. 系統檔案清單
| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | PA#LPF | PF | 銷售大區域資料檔主檔 |
| 2 | PA#LLF | LF | 銷售大區域資料檔邏輯檔 |

## 4. 記錄格式
**記錄格式名稱**: #L0

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|----------|
| #L01 | 大區域代號 | 1 | 2 | A | REF(#D01) | 參照地區代號欄位 |
| #L02 | 大區域描述 | 3 | 22 | O | REF(#D02) | 參照地區描述欄位 |
| #LXX | 建立日期 | 25 | 8 | 0 | REF(#AXX) | 建立日期 |
| #LYY | 建立時間 | 33 | 6 | 0 | REF(#AYY) | 建立時間 |
| #LZZ | 建立者 | 39 | 10 | A | REF(#AZZ) | 建立者代碼 |

## 6. 主鍵欄位
- **主鍵**: #L01 (大區域代號)

## 7. 索引資料
- **唯一鍵**: #L01 (大區域代號)
- **檔案特性**: UNIQUE

## 8. 備註
- 本檔案參考 RERF 檔案的欄位定義
- 檔案具有唯一性約束
- #LXX 欄位標示為 B2CHKA，表示可能需要特殊檢查
- #L01 和 #L02 分別參照 #D01 和 #D02 欄位定義 