# POPLPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | POPLPF |
| 檔案類型 | 實體檔 (PF) |
| 檔案說明 | 採購歷史明細檔 |
| 主索引鍵 | PC02+PC03 |
| 參照檔案 | RERF |
| 建立日期 | (依實際建立日期填入) |
| 維護人員 | (依實際維護人員填入) |

## 2. 檔案功能說明

此實體檔案用於儲存採購單明細的歷史資料，包含採購編號、產品項次及相關採購明細資訊。

### 主要功能
- 儲存採購明細的歷史資料
- 記錄產品採購的詳細軌跡
- 提供採購明細的長期保存記錄

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 | 關聯 |
|----------|----------|------|------|
| POPLPF | PF | 採購歷史明細檔實體檔 | 主檔案 |
| RERF | PF | 參照檔案 | 欄位定義參照 |

## 4. 記錄格式

### 記錄格式名稱：PC0

| 格式說明 | 記錄長度 | 參照檔案 |
|----------|----------|----------|
| 採購歷史明細檔記錄格式 | (依欄位定義計算) | RERF |

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| PC01 | 廠商編號 | 1 | R | 文字 | REF(RERF) | 參照廠商主檔 |
| PC02 | 採購編號 | - | R | 文字 | REF(RERF), KEY | 主鍵欄位 |
| PC03 | 產品項次 | - | R | 文字 | REF(RERF), KEY | 主鍵欄位 |
| PC04 | 採購日期 | - | 8 | 日期 | REF(RERF) | 採購日期 |
| PC05 | 供應商代號 | - | R | 文字 | REF(RERF) | 供應商資訊 |
| PC06 | 採購數量 | - | R | 數值 | REF(RERF) | 採購數量 |
| PC07 | 重量 | - | R | 數值 | REF(RERF) | 商品重量 |
| PC08 | 單費 | - | R | 數值 | REF(RERF) | 單費計算 |
| PC09 | 採購單價 | - | R | 數值 | REF(RERF) | 單價資訊 |
| PC10 | 總價費用 | - | R | 數值 | REF(RERF) | 總價計算 |
| PC11 | 預計數量 | - | R | 數值 | REF(RERF) | 預計數量 |
| PC12 | 結案備註 | - | R | 文字 | REF(RERF) | 'V' OR ' ' |
| PCXX | 建檔日期 | - | 8 | 日期 | REF(RERF) | 記錄建立日期 |
| PCYY | 建檔時間 | - | R | 時間 | REF(RERF) | 記錄建立時間 |
| PCZZ | 建檔者 | - | R | 文字 | REF(RERF) | 記錄建立人員 |

## 6. 主鍵欄位

| 欄位代號 | 欄位名稱 | 排序 | 說明 |
|----------|----------|------|------|
| PC02 | 採購編號 | 升序 | 複合主鍵第一部分 |
| PC03 | 產品項次 | 升序 | 複合主鍵第二部分 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：PC02+PC03
- **索引類型**：唯一索引 (UNIQUE)
- **唯一性**：是

### 檔案特性
- UNIQUE：確保採購編號+產品項次唯一性
- REF(RERF)：參照 RERF 檔案的欄位定義

## 8. 備註

### 特殊說明
- 此檔案為採購明細的歷史資料檔
- 使用 UNIQUE 關鍵字確保記錄唯一性
- 所有欄位定義參照 RERF 檔案
- 複合主鍵由採購編號、產品項次組成
- 包含完整的採購明細資訊：數量、重量、價格等

### 欄位特殊值
- PC12（結案備註）：'V' 表示已結案，' ' 表示未結案

### 相關檔案
- POPKPF（採購單歷史主檔）
- POPCPF（採購明細檔實體檔）
- POPBPF（採購單主檔實體檔）

### 維護注意事項
- 採購編號+產品項次組成複合主鍵，不可重複
- 數量與金額欄位需檢查資料合理性
- 重量欄位需符合商品特性
- 結案備註需正確設定以控制業務流程 