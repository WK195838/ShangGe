# DWPC02WF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | DWPC02WF |
| 檔案類型 | 實體檔案 (Physical File) |
| 檔案用途 | 通路銷售統計表 |
| 紀錄格式 | WF270 |
| 主鍵欄位 | WF2730+WF2702 |
| 排序方式 | 升序 |
| 特殊屬性 | *NOMAX |

## 2. 檔案功能說明

DWPC02WF是通路銷售統計的工作檔案：

1. **主要功能**：儲存通路銷售統計資料
2. **資料內容**：包含通路代號、名稱及12個月的數量和金額統計
3. **系統用途**：支援通路銷售統計表的資料處理
4. **索引設計**：以通路名稱內容輸出+通路名稱為複合主鍵
5. **統計週期**：按月份統計通路銷售數量和金額

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| DWPC02WF | 實體檔案 | 通路銷售統計表（主檔案） |
| RERF | 參考檔案 | 參考欄位定義檔 |

## 4. 紀錄格式

| 格式名稱 | 說明 |
|----------|------|
| WF270 | 通路銷售統計主記錄格式 |

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| WF2701 | 通路代號 | 1 | - | 字元 | 參考MD01 | 通路代號 |
| WF2702 | 通路名稱 | 2 | - | 字元 | 參考MD02/主鍵 | 通路名稱 |
| WF2703 | 通路類型 | 3 | - | 字元 | 參考#C03 | 通路類型分類 |
| WF2704 | 地區代號 | 4 | - | 字元 | 參考#D01 | 銷售地區 |
| WF2705 | 區域代號 | 5 | - | 字元 | 參考#E01 | 銷售區域 |
| WF2706 | 第一月數量 | 6 | 7 | 數值 | 7P 0 | 第一月銷售數量 |
| WF2707 | 第一月金額 | 7 | 10 | 數值 | 10S 0 | 第一月銷售金額 |
| WF2708 | 第二月數量 | 8 | 7 | 數值 | 7P 0 | 第二月銷售數量 |
| WF2709 | 第二月金額 | 9 | 10 | 數值 | 10S 0 | 第二月銷售金額 |
| WF2710 | 第三月數量 | 10 | 7 | 數值 | 7P 0 | 第三月銷售數量 |
| WF2711 | 第三月金額 | 11 | 10 | 數值 | 10S 0 | 第三月銷售金額 |
| WF2712 | 第四月數量 | 12 | 7 | 數值 | 7P 0 | 第四月銷售數量 |
| WF2713 | 第四月金額 | 13 | 10 | 數值 | 10S 0 | 第四月銷售金額 |
| WF2714 | 第五月數量 | 14 | 7 | 數值 | 7P 0 | 第五月銷售數量 |
| WF2715 | 第五月金額 | 15 | 10 | 數值 | 10S 0 | 第五月銷售金額 |
| WF2716 | 第六月數量 | 16 | 7 | 數值 | 7P 0 | 第六月銷售數量 |
| WF2717 | 第六月金額 | 17 | 10 | 數值 | 10S 0 | 第六月銷售金額 |
| WF2718 | 第七月數量 | 18 | 7 | 數值 | 7P 0 | 第七月銷售數量 |
| WF2719 | 第七月金額 | 19 | 10 | 數值 | 10S 0 | 第七月銷售金額 |
| WF2720 | 第八月數量 | 20 | 7 | 數值 | 7P 0 | 第八月銷售數量 |
| WF2721 | 第八月金額 | 21 | 10 | 數值 | 10S 0 | 第八月銷售金額 |
| WF2722 | 第九月數量 | 22 | 7 | 數值 | 7P 0 | 第九月銷售數量 |
| WF2723 | 第九月金額 | 23 | 10 | 數值 | 10S 0 | 第九月銷售金額 |
| WF2724 | 第十月數量 | 24 | 7 | 數值 | 7P 0 | 第十月銷售數量 |
| WF2725 | 第十月金額 | 25 | 10 | 數值 | 10S 0 | 第十月銷售金額 |
| WF2726 | 第十一月數量 | 26 | 7 | 數值 | 7P 0 | 第十一月銷售數量 |
| WF2727 | 第十一月金額 | 27 | 10 | 數值 | 10S 0 | 第十一月銷售金額 |
| WF2728 | 第十二月數量 | 28 | 7 | 數值 | 7P 0 | 第十二月銷售數量 |
| WF2729 | 第十二月金額 | 29 | 10 | 數值 | 10S 0 | 第十二月銷售金額 |
| WF2730 | 通路名稱內容輸出 | 30 | 6 | 字元 | 主鍵 | 通路名稱內容輸出 |
| WF2731 | 成本比率 | 31 | 4 | 數值 | 4S 3 | 成本比率（小數點後3位） |

## 6. 主鍵欄位

本實體檔案的主鍵欄位為：
- WF2730（通路名稱內容輸出）
- WF2702（通路名稱）

### 主鍵特性：
- **WF2730（通路名稱內容輸出）**：第一層分類，輸出內容控制
- **WF2702（通路名稱）**：第二層分類，通路識別

## 7. 索引資料

| 索引名稱 | 索引鍵 | 排序 | 用途說明 |
|----------|--------|------|----------|
| 主索引 | WF2730+WF2702 | 升序 | 通路統計資料查詢 |

### 索引特性：
- **複合索引**：兩個欄位組成的複合主鍵
- **輸出控制**：按輸出內容分類管理
- **通路識別**：提供通路別的資料存取路徑

## 8. 備註

1. **工作檔案性質**：專門用於通路銷售統計的臨時工作檔案
2. **月份統計設計**：
   - 完整12個月的數量和金額統計
   - 每月包含數量（7P 0）和金額（10S 0）兩個欄位
   - 支援年度通路銷售統計分析
3. **參考欄位設計**：
   - 使用REF(RERF)參考檔案定義
   - WF2701參考MD01（通路代號）
   - WF2702參考MD02（通路名稱）
   - WF2703參考#C03（通路類型）
   - WF2704參考#D01（地區）
   - WF2705參考#E01（區域）
4. **統計維度**：
   - 通路維度：通路代號、通路名稱
   - 分類維度：通路類型
   - 地理維度：地區、區域
   - 時間維度：12個月份統計
5. **數值精度**：
   - 數量欄位：7位整數（7P 0）
   - 金額欄位：10位整數（10S 0）
   - 成本比率：4位數含3位小數（4S 3）
6. **特殊屬性**：
   - *NOMAX：檔案大小不受限制
   - 適合大量統計資料處理
7. **業務應用**：
   - 通路銷售統計報表
   - 月份銷售趨勢分析
   - 通路績效評估
   - 地區區域分析
8. **資料結構**：
   - 31個欄位，結構完整
   - 涵蓋通路基本資料和12個月統計
   - 支援多維度分析需求
9. **系統整合**：
   - 與RERF參考檔案整合
   - 支援報表程式DWPC02
   - 提供通路統計分析基礎資料
10. **檔案特色**：
    - 橫向月份展開設計
    - 數量金額配對統計
    - 地理區域層次分析
11. **資料處理**：專門用於通路銷售統計表的資料彙總和分析
12. **通路管理**：
    - 支援通路類型分類管理
    - 提供地區區域階層分析
    - 適用於通路績效評估