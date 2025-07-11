# MTMILF01 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | MTMILF01 |
| 檔案描述 | 產品基本資料延伸檔 |
| 檔案類型 | LF (Logical File) |
| 記錄格式 | MI0 |
| 主鍵 | MI01 (產品代號) |
| 實體檔案 | MTMIPF |
| 檔案屬性 | 邏輯檢視，延伸資料檢視 |

## 2. 檔案功能說明

MTMILF01 為產品基本資料延伸檔的邏輯檔案，提供：
- 產品延伸資料查詢
- 特殊屬性資料檢視
- 產品附加資訊管理
- 延伸欄位資料存取

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 說明 |
|----------|----------|------|
| MTMILF01 | 產品基本資料延伸邏輯檔 | 主檔 |
| MTMIPF | 產品基本資料延伸實體檔 | 實體檔案 |
| MTMAPF | 產品基本資料實體檔 | 關聯檔案 |
| RERF | 參考檔案 | 欄位定義參考 |

## 4. 紀錄格式

### 記錄格式：MI0 (繼承自 MTMIPF)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| MI01 | 產品代號 | 1-13 | 13 | A | R | 主鍵，關聯MTMAPF.MA01 |
| MI02 | 延伸代號 | 14-16 | 3 | A | R | 延伸資料識別碼 |
| MI03 | 延伸名稱 | 17-56 | 40 | A | R | 延伸資料名稱 |
| MI04 | 延伸說明 | 57-156 | 100 | A | R | 延伸資料詳細說明 |
| MI05 | 資料類型 | 157 | 1 | A | R | 'T'-文字，'N'-數字，'D'-日期 |
| MI06 | 文字內容 | 158-357 | 200 | A | R | 文字型延伸內容 |
| MI07 | 數字內容 | 358-372 | 15 | N | R | 數字型延伸內容 (11位整數，4位小數) |
| MI08 | 日期內容 | 373-380 | 8 | N | R | 日期型延伸內容 YYYYMMDD |
| MI09 | 優先順序 | 381-383 | 3 | N | R | 顯示優先順序 |
| MI10 | 狀態標記 | 384 | 1 | A | R | 'A'-有效，'I'-無效，'D'-刪除 |
| MI11 | 分類標記 | 385-389 | 5 | A | R | 延伸資料分類 |
| MI12 | 版本號 | 390-394 | 5 | A | R | 延伸資料版本 |
| MI13 | 來源系統 | 395-399 | 5 | A | R | 資料來源系統 |
| MI14 | 更新頻率 | 400 | 1 | A | R | 'D'-每日，'W'-每週，'M'-每月 |
| MI15 | 檢核狀態 | 401 | 1 | A | R | 'Y'-已檢核，'N'-未檢核 |
| MI16 | 公開等級 | 402 | 1 | A | R | '1'-公開，'2'-內部，'3'-機密 |
| MI17 | 關聯檔案 | 403-407 | 5 | A | R | 關聯檔案代號 |
| MI18 | 關聯欄位 | 408-412 | 5 | A | R | 關聯欄位代號 |
| MI19 | 單位代號 | 413-417 | 5 | A | R | 數字內容單位 |
| MI20 | 格式代號 | 418-422 | 5 | A | R | 顯示格式代號 |
| MI21 | 驗證規則 | 423-437 | 15 | A | R | 資料驗證規則 |
| MI22 | 預設值 | 438-452 | 15 | A | R | 預設值設定 |
| MI23 | 最小值 | 453-467 | 15 | N | R | 數字型最小值 |
| MI24 | 最大值 | 468-482 | 15 | N | R | 數字型最大值 |
| MI25 | 小數位數 | 483-484 | 2 | N | R | 數字型小數位數 |
| MI26 | 必填標記 | 485 | 1 | A | R | 'Y'-必填，'N'-選填 |
| MI27 | 唯一標記 | 486 | 1 | A | R | 'Y'-唯一，'N'-可重複 |
| MI28 | 索引標記 | 487 | 1 | A | R | 'Y'-建立索引，'N'-不建索引 |
| MI29 | 附件路徑 | 488-537 | 50 | A | R | 相關附件檔案路徑 |
| MI30 | 備用欄位1 | 538-552 | 15 | A | R | 備用欄位1 |
| MI31 | 備用欄位2 | 553-567 | 15 | A | R | 備用欄位2 |
| MI32 | 備用欄位3 | 568-582 | 15 | A | R | 備用欄位3 |
| MIXX | 建立日期 | 583-590 | 8 | N | R | 建立日期 YYYYMMDD |
| MIYY | 建立時間 | 591-596 | 6 | N | R | 建立時間 HHMMSS |
| MIZZ | 建立者 | 597-606 | 10 | A | R | 建立人員 |
| MI33 | 異動日期 | 607-614 | 8 | N | R | 最後異動日期 YYYYMMDD |
| MI34 | 異動時間 | 615-620 | 6 | N | R | 最後異動時間 HHMMSS |
| MI35 | 異動者 | 621-630 | 10 | A | R | 最後異動人員 |

## 6. 主鍵欄位

| 鍵值序號 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | MI01 | 產品代號 | 升序 |
| 2 | MI02 | 延伸代號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：MI01 + MI02
- **索引類型**：PRIMARY
- **說明**：產品代號 + 延伸代號複合升序排序

### 輔助索引
1. **延伸代號索引**：MI02 + MI01 (延伸代號 + 產品代號)
2. **分類索引**：MI11 + MI01 + MI02 (分類 + 產品 + 延伸代號)
3. **狀態索引**：MI10 + MI01 + MI02 (狀態 + 產品 + 延伸代號)
4. **優先順序索引**：MI09 + MI01 + MI02 (優先順序 + 產品 + 延伸代號)
5. **版本索引**：MI12 + MI01 + MI02 (版本 + 產品 + 延伸代號)
6. **來源系統索引**：MI13 + MI01 + MI02 (來源系統 + 產品 + 延伸代號)
7. **公開等級索引**：MI16 + MI01 + MI02 (公開等級 + 產品 + 延伸代號)
8. **關聯檔案索引**：MI17 + MI18 + MI01 + MI02 (關聯檔案 + 欄位 + 產品 + 延伸)
9. **資料類型索引**：MI05 + MI01 + MI02 (資料類型 + 產品 + 延伸代號)
10. **異動日期索引**：MI33 + MI34 + MI01 + MI02 (異動日期 + 時間 + 產品 + 延伸)

### 邏輯檢視特性
- **基底檔案**：MTMIPF
- **檢視類型**：延伸資料檢視
- **排序方式**：產品代號 + 延伸代號
- **關聯查詢**：與產品主檔關聯

## 8. 備註

### 設計考量
1. 此檔案為 MTMIPF 的邏輯檢視檔案
2. 提供產品延伸資料的標準檢視
3. 支援多種資料類型的延伸內容

### 延伸資料功能
- **多重延伸**：一個產品可有多筆延伸資料
- **類型支援**：支援文字、數字、日期型資料
- **分類管理**：延伸資料分類標記
- **版本控制**：延伸資料版本管理

### 資料驗證機制
- **資料類型檢查**：依MI05確認內容格式
- **數值範圍檢查**：MI23、MI24最小最大值
- **必填檢查**：MI26必填標記控制
- **唯一性檢查**：MI27唯一標記控制
- **格式驗證**：MI21驗證規則執行

### 使用場景
1. **產品規格擴充**：標準欄位無法滿足的特殊規格
2. **附加屬性管理**：產品特殊屬性記錄
3. **多版本資料**：不同版本的產品資料
4. **動態欄位**：系統動態欄位需求

### 延伸內容管理
- **文字內容**：MI06 (200字元)
- **數字內容**：MI07 (15位數字)
- **日期內容**：MI08 (YYYYMMDD格式)
- **附件關聯**：MI29 附件路徑

### 分類系統
- **分類標記**：MI11 延伸資料分類
- **優先順序**：MI09 顯示順序控制
- **公開等級**：MI16 存取權限控制
- **狀態管理**：MI10 資料狀態控制

### 關聯機制
- **主檔關聯**：MI01 與 MTMAPF.MA01 關聯
- **檔案關聯**：MI17、MI18 關聯檔案欄位
- **來源追蹤**：MI13 資料來源系統

### 品質控制
- **檢核狀態**：MI15 資料檢核標記
- **更新頻率**：MI14 資料更新週期
- **驗證規則**：MI21 自動驗證機制
- **預設值**：MI22 預設值設定

### 參考關聯
- **產品主檔**：MTMAPF (MI01 = MA01)
- **分類檔案**：PA#分類檔 (MI11 = 分類代號)
- **來源系統檔**：系統檔 (MI13 = 系統代號)
- **格式檔案**：PA#格式檔 (MI20 = 格式代號)

### 業務規則
1. 產品代號必須存在於MTMAPF中
2. 延伸代號在同一產品下唯一
3. 資料類型與內容欄位必須一致
4. 狀態為'A'才能正常使用

### 延伸應用
- **動態表單**：根據延伸資料產生動態表單
- **報表擴充**：報表動態欄位顯示
- **資料交換**：系統間資料交換擴充
- **客製化需求**：滿足特殊客製化需求

### 索引策略
- **主鍵索引**：快速定位特定延伸資料
- **分類索引**：依分類快速查詢
- **狀態索引**：有效資料快速篩選
- **關聯索引**：跨檔案關聯查詢

### 資料完整性
1. 資料內容完全依賴 MTMIPF 實體檔案
2. MI01 必須存在於 MTMAPF 中
3. MI05 資料類型與內容欄位需一致
4. MI10 狀態標記需為有效值

### 效能最佳化
- **索引利用**：充分利用輔助索引
- **條件篩選**：狀態條件先篩選
- **分頁查詢**：大量資料分頁處理
- **快取機制**：常用資料快取

### 使用注意事項
1. 此為邏輯檔案，不可直接寫入資料
2. 所有異動需透過 MTMIPF 實體檔案進行
3. 延伸資料異動會影響排序順序
4. 適用於產品主檔的延伸資料管理 