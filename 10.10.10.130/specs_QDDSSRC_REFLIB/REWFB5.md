# REWFB5 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | REWFB5 |
| 檔案類型 | 實體檔 (PF) |
| 檔案說明 | 客戶銷售統計表 |
| 主索引鍵 | WFB501+WFB502 |
| 參照檔案 | RERF |
| 建立日期 | (依實際建立日期填入) |
| 維護人員 | (依實際維護人員填入) |

## 2. 檔案功能說明

此實體檔案用於管理客戶銷售統計資料，記錄專櫃與幣別的月份銷售數量與金額統計，支援年度銷售分析與績效評估。

### 主要功能
- 管理客戶月份銷售統計
- 記錄專櫃銷售績效
- 支援年度銷售分析
- 提供銷售趨勢統計

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 | 關聯 |
|----------|----------|------|------|
| REWFB5 | PF | 客戶銷售統計表 | 主檔案 |
| RERF | PF | 參照檔案 | REF參照 |

## 4. 記錄格式

### 記錄格式名稱：WFB50

| 格式說明 | 記錄長度 | 參照檔案 |
|----------|----------|----------|
| 客戶銷售統計記錄格式 | (依欄位定義計算) | RERF |

## 5. 欄位規格

### 5.1 基本識別欄位
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| WFB501 | 專櫃代號 | 1 | R | 文字 | REFFLD(ST01) | 專櫃代號 |
| WFB502 | 幣別 | 2 | R | 文字 | REFFLD(ST14) | 幣別代碼 |

### 5.2 第一季銷售統計欄位
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| WFB505 | 第一月數量 | 3 | 7P 0 | 數值 | | 第一月銷售數量 |
| WFB506 | 第一月金額 | 4 | 8S 0 | 數值 | | 第一月銷售金額 |
| WFB507 | 第二月數量 | 5 | 7P 0 | 數值 | | 第二月銷售數量 |
| WFB508 | 第二月金額 | 6 | 8S 0 | 數值 | | 第二月銷售金額 |
| WFB509 | 第三月數量 | 7 | 7P 0 | 數值 | | 第三月銷售數量 |
| WFB510 | 第三月金額 | 8 | 8S 0 | 數值 | | 第三月銷售金額 |

### 5.3 第二季銷售統計欄位
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| WFB511 | 第四月數量 | 9 | 7P 0 | 數值 | | 第四月銷售數量 |
| WFB512 | 第四月金額 | 10 | 8S 0 | 數值 | | 第四月銷售金額 |
| WFB513 | 第五月數量 | 11 | 7P 0 | 數值 | | 第五月銷售數量 |
| WFB514 | 第五月金額 | 12 | 8S 0 | 數值 | | 第五月銷售金額 |
| WFB515 | 第六月數量 | 13 | 7P 0 | 數值 | | 第六月銷售數量 |
| WFB516 | 第六月金額 | 14 | 8S 0 | 數值 | | 第六月銷售金額 |

### 5.4 第三季銷售統計欄位
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| WFB517 | 第七月數量 | 15 | 7P 0 | 數值 | | 第七月銷售數量 |
| WFB518 | 第七月金額 | 16 | 8S 0 | 數值 | | 第七月銷售金額 |
| WFB519 | 第八月數量 | 17 | 7P 0 | 數值 | | 第八月銷售數量 |
| WFB520 | 第八月金額 | 18 | 8S 0 | 數值 | | 第八月銷售金額 |
| WFB521 | 第九月數量 | 19 | 7P 0 | 數值 | | 第九月銷售數量 |
| WFB522 | 第九月金額 | 20 | 8S 0 | 數值 | | 第九月銷售金額 |

### 5.5 第四季銷售統計欄位
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| WFB523 | 第十月數量 | 21 | 7P 0 | 數值 | | 第十月銷售數量 |
| WFB524 | 第十月金額 | 22 | 8S 0 | 數值 | | 第十月銷售金額 |
| WFB525 | 第十一月數量 | 23 | 7P 0 | 數值 | | 第十一月銷售數量 |
| WFB526 | 第十一月金額 | 24 | 8S 0 | 數值 | | 第十一月銷售金額 |
| WFB527 | 第十二月數量 | 25 | 7P 0 | 數值 | | 第十二月銷售數量 |
| WFB528 | 第十二月金額 | 26 | 8S 0 | 數值 | | 第十二月銷售金額 |

## 6. 主鍵欄位

### 複合主鍵設計
| 順序 | 欄位代號 | 欄位名稱 | 說明 |
|------|----------|----------|------|
| 1 | WFB501 | 專櫃代號 | 專櫃識別 |
| 2 | WFB502 | 幣別 | 幣別識別 |

## 7. 索引資料

### 檔案特性
- REF(RERF)：欄位定義參照RERF檔案
- REFFLD：多個欄位參照特定欄位定義
- 複合主鍵索引

### 索引設計
- **主索引**：專櫃代號+幣別

## 8. 備註

### 特殊說明
- 此檔案為客戶銷售統計管理檔
- 使用專櫃+幣別雙維度主鍵
- 支援12個月完整銷售統計
- 提供數量與金額雙重統計

### 統計設計機制
檔案設計支援完整年度統計：
- **月份統計**：12個月完整統計
- **數量統計**：各月份銷售數量統計
- **金額統計**：各月份銷售金額統計
- **專櫃統計**：專櫃別績效統計

### 檔案用途
- 用於客戶銷售分析
- 支援專櫃績效評估
- 提供年度銷售統計
- 管理多幣別銷售

### 參照檔案說明
使用 REF(RERF) 參照：
- WFB501 參照 ST01 (專櫃代號)
- WFB502 參照 ST14 (幣別)
- 確保與主系統資料一致性
- 支援標準化資料格式

### 維護注意事項
- 專櫃代號需與專櫃主檔一致
- 幣別代號需與幣別主檔一致
- 數量與金額統計需確保準確性
- 月份統計需依序維護

### 系統應用
- 用於銷售分析系統
- 支援績效管理
- 提供統計報表基礎
- 配合客戶管理系統

### 相關作業
- 銷售統計作業
- 專櫃績效分析作業
- 年度銷售報表作業
- 客戶銷售趨勢分析作業

### 技術特性
- 複合主鍵設計
- 月份序列統計
- 數量金額分離
- 多幣別支援

### 業務流程整合
- 與銷售管理流程整合
- 支援專櫃管理
- 配合績效評估系統
- 提供決策支援基礎

### 銷售統計功能
- **月份統計**：各月份銷售數據統計
- **季度統計**：季度銷售績效統計
- **年度統計**：年度銷售總計統計
- **趨勢分析**：銷售趨勢變化分析

### 專櫃管理功能
- **專櫃績效**：專櫃銷售績效管理
- **專櫃比較**：專櫃間績效比較
- **專櫃排名**：專櫃銷售排名管理
- **專櫃成長**：專櫃成長率分析

### 多幣別統計功能
- **幣別統計**：各幣別銷售統計
- **匯率影響**：匯率變動影響分析
- **本位幣統計**：本位幣銷售統計
- **幣別比重**：各幣別銷售比重

### 績效分析功能
- **銷售成長**：銷售成長率分析
- **季節分析**：季節性銷售分析
- **達成率分析**：目標達成率分析
- **市場佔有**：市場佔有率分析

### 報表功能支援
- **月報表**：月份銷售統計報表
- **季報表**：季度銷售統計報表
- **年報表**：年度銷售統計報表
- **比較報表**：同期比較分析報表

### 決策支援功能
- **銷售預測**：銷售趨勢預測分析
- **庫存計劃**：庫存需求計劃支援
- **市場策略**：市場策略制定支援
- **資源配置**：資源配置優化支援

### 資料品質管控
- **資料一致性**：確保統計資料一致性
- **資料完整性**：確保統計資料完整性
- **資料準確性**：確保統計資料準確性
- **資料時效性**：確保統計資料時效性

### 系統整合特性
- **ERP整合**：與企業資源規劃整合
- **BI整合**：與商業智慧系統整合
- **CRM整合**：與客戶關係管理整合
- **財務整合**：與財務管理系統整合

### 數據分析應用
- **統計分析**：銷售統計數據分析
- **預測分析**：銷售預測模型分析
- **對比分析**：同期對比趨勢分析
- **相關分析**：銷售相關因素分析

### 管理應用功能
- **管理報表**：管理階層決策報表
- **營運分析**：營運績效分析報表
- **策略規劃**：策略規劃基礎資料
- **預算管理**：預算制定參考資料 