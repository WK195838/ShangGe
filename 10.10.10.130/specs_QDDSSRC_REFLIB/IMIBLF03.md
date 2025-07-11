# IMIBLF03 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | IMIBLF03 |
| 檔案類型 | 邏輯檔案 (Logical File) |
| 檔案用途 | 產品成本調整資料檔（日期客戶排序） |
| 紀錄格式 | IB0 |
| 基礎實體檔案 | IMIBPF |
| 主鍵欄位 | IB04+IB02 |
| 排序方式 | 升序 |
| 特殊用途 | 日期導向的成本調整查詢 |

## 2. 檔案功能說明

IMIBLF03是產品成本調整資料檔的邏輯檔案，專門提供日期客戶排序：

1. **主要功能**：提供產品成本調整資料的日期客戶存取路徑
2. **基礎檔案**：基於IMIBPF實體檔案建立
3. **系統用途**：支援按調整日期和客戶代號順序的成本調整查詢
4. **索引設計**：使用IB04+IB02的複合主鍵
5. **存取特性**：按調整日期、客戶代號的順序排列
6. **專用功能**：專門為日期導向的成本調整分析設計

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| IMIBLF03 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（日期客戶排序） |
| IMIBPF | 實體檔案 | 產品成本調整資料檔實體檔案（基礎檔案） |
| IMIBLF | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（標準排序） |
| IMIBLF01 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（時間序列排序） |
| IMIBLF02 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（客戶產品排序） |
| IMIBLF1 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（簡化版） |

## 4. 紀錄格式

| 格式名稱 | 說明 |
|----------|------|
| IB0 | 產品成本調整主記錄格式（參考IMIBPF） |

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

本邏輯檔案使用PFILE(IMIBPF)，所有欄位定義參考基礎實體檔案IMIBPF：

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| IB04 | 調整日期 | 1 | - | - | 主鍵 | 調整日期（第一排序鍵） |
| IB02 | 客戶代號 | 2 | - | - | 主鍵 | 客戶代號（第二排序鍵） |
| 其他欄位 | - | - | - | - | - | 繼承IMIBPF的所有欄位定義 |

*註：詳細欄位規格請參考基礎實體檔案IMIBPF的定義*

## 6. 主鍵欄位

本邏輯檔案的主鍵欄位為：
- IB04（調整日期）
- IB02（客戶代號）

### 主鍵特性：
- **IB04（調整日期）**：第一層分類，按調整日期排序
- **IB02（客戶代號）**：第二層分類，客戶代號排序

## 7. 索引資料

| 索引名稱 | 索引鍵 | 排序 | 用途說明 |
|----------|--------|------|----------|
| 主索引 | IB04+IB02 | 升序 | 日期客戶成本調整查詢 |

### 索引特性：
- **複合索引**：兩個欄位組成的複合主鍵
- **日期導向排序**：調整日期→客戶代號
- **時間序列分析**：適合按日期進行成本調整分析

## 8. 備註

1. **邏輯檔案特性**：
   - 基於IMIBPF實體檔案的邏輯檔案
   - 使用PFILE(IMIBPF)引用基礎檔案
   - 專門為日期導向查詢設計的排序方式
2. **日期導向設計**：
   - 排序方式：IB04+IB02（調整日期+客戶代號）
   - 適合按日期進行成本調整分析
   - 便於日期別的成本調整追蹤
3. **與其他IMIBLF系列比較**：
   - IMIBLF：標準排序，IB01+IB02+IB03
   - IMIBLF01：時間序列排序，IB01+IB04+IBYY+IB02+IB03
   - IMIBLF02：客戶產品排序，IB02+IB04
   - IMIBLF03：日期客戶排序，IB04+IB02（本檔案）
   - IMIBLF1：簡化版邏輯檔案
4. **日期導向應用**：
   - 日期別成本調整分析
   - 日期範圍成本調整查詢
   - 調整日期歷史追蹤
   - 時間序列成本分析
5. **系統整合**：
   - 與IMIBPF實體檔案緊密整合
   - 與其他IMIBLF系列提供互補的存取路徑
   - 專門支援日期導向的成本調整分析
6. **資料存取**：
   - 繼承基礎檔案的所有欄位
   - 提供日期導向的成本調整資料檢視
   - 支援時間序列相關的業務查詢
7. **業務應用**：
   - 日期別成本調整報表
   - 時間序列成本分析
   - 調整日期歷史查詢
   - 日期範圍成本統計
8. **檔案關係**：
   - 邏輯檔案：IMIBLF03（本檔案）
   - 實體檔案：IMIBPF（基礎檔案）
   - 相關邏輯檔案：IMIBLF系列
9. **存取效能**：
   - 針對日期導向查詢優化
   - 支援高效的日期範圍資料存取
   - 適合時間序列分析應用
10. **資料完整性**：
    - 依賴基礎實體檔案的資料完整性
    - 透過邏輯檔案提供一致的資料檢視
    - 確保日期調整資料的準確性
11. **維護特性**：
    - 結構簡潔但功能明確
    - 變更需同步考慮基礎實體檔案
    - 提供穩定的日期導向資料存取介面
12. **系統價值**：
    - 作為日期別成本調整分析的專用檔案
    - 提供日期導向的成本調整資料檢視
    - 支援時間序列分析和報表需求
13. **特殊功能**：
    - 專門用於日期導向成本調整分析
    - 支援時間序列的成本調整追蹤
    - 便於日期相關的系統整合
14. **日期維度優化**：
    - 調整日期優先排序
    - 適合時間序列分析需求
    - 支援日期範圍資料的快速檢索
15. **資料結構**：
    - 雙層主鍵設計（日期→客戶）
    - 完整繼承實體檔案的欄位結構
    - 日期導向優化的成本調整資料格式
16. **應用範圍**：
    - 日期別成本調整分析
    - 時間序列成本報表
    - 調整日期歷史追蹤
    - 日期範圍成本查詢
    - 成本調整趨勢分析
17. **時間序列支援**：
    - 日期為第一排序鍵，適合時間序列查詢
    - 支援日期範圍的成本調整分析
    - 便於時間軸上的成本變動追蹤
18. **效能考量**：
    - 調整日期為第一排序鍵，適合日期別查詢
    - 客戶代號為第二排序鍵，便於客戶分組
    - 提供高效的日期導向資料存取
19. **與IMIBLF02的差異**：
    - IMIBLF02：客戶代號+調整日期（客戶導向）
    - IMIBLF03：調整日期+客戶代號（日期導向，本檔案）
    - 兩者提供不同的查詢優化路徑
20. **系統設計考量**：
    - 日期優先排序適合時間序列報表
    - 客戶次要排序便於同日期內的客戶分組
    - 與其他IMIBLF系列形成完整的存取路徑體系