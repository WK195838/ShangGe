# IMIBLF01 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | IMIBLF01 |
| 檔案類型 | 邏輯檔案 (Logical File) |
| 檔案用途 | 產品成本調整資料檔（時間序列排序） |
| 紀錄格式 | IB0 |
| 基礎實體檔案 | IMIBPF |
| 主鍵欄位 | IB01+IB04+IBYY+IB02+IB03 |
| 排序方式 | 升序 |
| 特殊用途 | 調整日期時間序列查詢 |

## 2. 檔案功能說明

IMIBLF01是產品成本調整資料檔的邏輯檔案，專門提供時間序列排序：

1. **主要功能**：提供產品成本調整資料的時間序列存取路徑
2. **基礎檔案**：基於IMIBPF實體檔案建立
3. **系統用途**：支援按調整日期和時間順序的成本調整查詢
4. **索引設計**：使用IB01+IB04+IBYY+IB02+IB03的複合主鍵
5. **存取特性**：按調整單號、調整日期、異動時間的順序排列
6. **專用功能**：專門為時間序列分析和歷史查詢設計

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| IMIBLF01 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（時間序列排序） |
| IMIBPF | 實體檔案 | 產品成本調整資料檔實體檔案（基礎檔案） |
| IMIBLF | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（標準排序） |
| IMIBLF02 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（產品代號排序） |
| IMIBLF03 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（日期排序） |
| IMIBLF1 | 邏輯檔案 | 產品成本調整資料檔邏輯檔案（簡化版） |

## 4. 紀錄格式

| 格式名稱 | 說明 |
|----------|------|
| IB0 | 產品成本調整主記錄格式（參考IMIBPF） |

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

本邏輯檔案使用PFILE(IMIBPF)，所有欄位定義參考基礎實體檔案IMIBPF：

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| IB01 | 調整單號 | 1 | - | - | 主鍵 | 成本調整單號（第一排序鍵） |
| IB04 | 調整日期 | 2 | - | - | 主鍵 | 調整日期（第二排序鍵） |
| IBYY | 異動時間 | 3 | - | - | 主鍵 | 異動時間（第三排序鍵） |
| IB02 | 客戶代號 | 4 | - | - | 主鍵 | 客戶代號（第四排序鍵） |
| IB03 | 產品代號 | 5 | - | - | 主鍵 | 產品代號（第五排序鍵） |
| 其他欄位 | - | - | - | - | - | 繼承IMIBPF的所有欄位定義 |

*註：詳細欄位規格請參考基礎實體檔案IMIBPF的定義*

## 6. 主鍵欄位

本邏輯檔案的主鍵欄位為：
- IB01（調整單號）
- IB04（調整日期）
- IBYY（異動時間）
- IB02（客戶代號）
- IB03（產品代號）

### 主鍵特性：
- **IB01（調整單號）**：第一層分類，按調整單號排序
- **IB04（調整日期）**：第二層分類，調整日期排序
- **IBYY（異動時間）**：第三層分類，異動時間排序
- **IB02（客戶代號）**：第四層分類，客戶代號排序
- **IB03（產品代號）**：第五層分類，產品代號排序

## 7. 索引資料

| 索引名稱 | 索引鍵 | 排序 | 用途說明 |
|----------|--------|------|----------|
| 主索引 | IB01+IB04+IBYY+IB02+IB03 | 升序 | 時間序列成本調整查詢 |

### 索引特性：
- **複合索引**：五個欄位組成的複合主鍵
- **時間序列排序**：調整單號→調整日期→異動時間→客戶代號→產品代號
- **歷史查詢優化**：專為時間序列分析設計的排序方式

## 8. 備註

1. **邏輯檔案特性**：
   - 基於IMIBPF實體檔案的邏輯檔案
   - 使用PFILE(IMIBPF)引用基礎檔案
   - 專門為時間序列查詢設計的排序方式
2. **時間序列設計**：
   - 排序方式：IB01+IB04+IBYY+IB02+IB03
   - 適合按時間順序進行成本調整歷史分析
   - 便於追蹤成本調整的時間軌跡
3. **五層排序架構**：
   - 第一層：IB01（調整單號）- 調整批次分組
   - 第二層：IB04（調整日期）- 日期順序
   - 第三層：IBYY（異動時間）- 時間順序
   - 第四層：IB02（客戶代號）- 客戶分組
   - 第五層：IB03（產品代號）- 產品分組
4. **與其他IMIBLF系列比較**：
   - IMIBLF：標準排序，IB01+IB02+IB03
   - IMIBLF01：時間序列排序，IB01+IB04+IBYY+IB02+IB03（本檔案）
   - IMIBLF02：產品代號優先排序
   - IMIBLF03：日期優先排序
   - IMIBLF1：簡化版邏輯檔案
5. **時間序列應用**：
   - 成本調整歷史追蹤
   - 時間序列分析
   - 調整軌跡查詢
   - 歷史資料檢索
6. **索引設計**：
   - 採用五欄位複合主鍵
   - 時間維度為主要排序依據
   - 支援時間序列相關的資料查詢模式
7. **系統整合**：
   - 與IMIBPF實體檔案緊密整合
   - 與其他IMIBLF系列提供互補的存取路徑
   - 專門支援時間序列成本調整分析
8. **資料存取**：
   - 繼承基礎檔案的所有欄位
   - 提供時間序列的成本調整資料檢視
   - 支援歷史資料相關的業務查詢
9. **業務應用**：
   - 成本調整歷史分析
   - 時間序列報表
   - 調整軌跡追蹤
   - 歷史資料查詢
10. **檔案關係**：
    - 邏輯檔案：IMIBLF01（本檔案）
    - 實體檔案：IMIBPF（基礎檔案）
    - 相關邏輯檔案：IMIBLF系列
11. **存取效能**：
    - 針對時間序列查詢優化
    - 支援高效的歷史資料存取
    - 適合時間序列分析應用
12. **資料完整性**：
    - 依賴基礎實體檔案的資料完整性
    - 透過邏輯檔案提供一致的資料檢視
    - 確保時間序列資料的準確性
13. **維護特性**：
    - 結構複雜但功能強大
    - 變更需同步考慮基礎實體檔案
    - 提供穩定的時間序列資料存取介面
14. **系統價值**：
    - 作為成本調整歷史分析的專用檔案
    - 提供時間序列的成本調整資料檢視
    - 支援歷史資料分析和報表需求
15. **特殊功能**：
    - 專門用於時間序列成本調整分析
    - 支援歷史軌跡追蹤
    - 便於時間序列相關的系統整合
16. **時間維度優化**：
    - 日期和時間雙重排序
    - 適合時間序列分析需求
    - 支援歷史資料的快速檢索
17. **資料結構**：
    - 五層主鍵設計（單號→日期→時間→客戶→產品）
    - 完整繼承實體檔案的欄位結構
    - 時間序列優化的成本調整資料格式
18. **應用範圍**：
    - 成本調整歷史分析
    - 時間序列報表
    - 調整軌跡追蹤
    - 歷史資料查詢
    - 成本變動趨勢分析