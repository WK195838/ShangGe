# MTMHLF2 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | MTMHLF2 |
| 檔案描述 | 產品基本資料檔 KN |
| 檔案類型 | LF (Logical File) |
| 記錄格式 | MH0 |
| 主鍵 | MH22 + MH01 (條碼 + 產品代號) |
| 實體檔案 | MTMHPF |
| 檔案屬性 | 邏輯檢視，條碼排序 |

## 2. 檔案功能說明

MTMHLF2 為產品基本資料檔的 KN 版本邏輯檔案，提供：
- 依條碼排序的產品檢視
- 條碼查詢專用檢視
- 條碼管理功能
- POS 系統支援

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 說明 |
|----------|----------|------|
| MTMHLF2 | 產品基本資料邏輯檔 KN 2 | 主檔 |
| MTMHPF | 產品基本資料實體檔 KN | 實體檔案 |
| MTMHLF | 產品基本資料邏輯檔 KN | 基本邏輯檔 |
| RERF | 參考檔案 | 欄位定義參考 |

## 4. 紀錄格式

### 記錄格式：MH0 (繼承自 MTMHPF)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| MH01 | 產品代號 | 1-13 | 13 | A | R | 主鍵2，產品識別碼 |
| MH02 | 產品名稱 | 14-53 | 40 | A | R | 產品中文名稱 |
| MH03 | 英文名稱 | 54-93 | 40 | A | R | 產品英文名稱 |
| MH04 | 產品簡稱 | 94-113 | 20 | A | R | 產品簡稱 |
| MH05 | 產品狀態 | 114 | 1 | A | R | 'A'-正常，'D'-停產，'N'-新品 |
| MH06 | 品牌代號 | 115-119 | 5 | A | R | 品牌識別碼 |
| MH07 | 分類代號 | 120-124 | 5 | A | R | 產品分類 |
| MH08 | 規格說明 | 125-164 | 40 | A | R | 產品規格描述 |
| MH09 | 單位 | 165-169 | 5 | A | R | 基本單位 |
| MH10 | 標準成本 | 170-184 | 15 | N | R | 標準成本 (4位小數) |
| MH11 | 售價 | 185-199 | 15 | N | R | 建議售價 (2位小數) |
| MH12 | 最低售價 | 200-214 | 15 | N | R | 最低售價 (2位小數) |
| MH13 | 重量 | 215-229 | 15 | N | R | 產品重量 (3位小數) |
| MH14 | 體積 | 230-244 | 15 | N | R | 產品體積 (3位小數) |
| MH15 | 保存期限 | 245-247 | 3 | N | R | 保存期限 (天) |
| MH16 | 供應商 | 248-254 | 7 | A | R | 主要供應商代號 |
| MH17 | 採購員 | 255-259 | 5 | A | R | 負責採購員代號 |
| MH18 | 安全庫存 | 260-274 | 15 | N | R | 安全庫存量 (2位小數) |
| MH19 | 最高庫存 | 275-289 | 15 | N | R | 最高庫存量 (2位小數) |
| MH20 | 最低庫存 | 290-304 | 15 | N | R | 最低庫存量 (2位小數) |
| MH21 | 訂購批量 | 305-319 | 15 | N | R | 經濟訂購批量 (2位小數) |
| MH22 | 條碼 | 320-332 | 13 | A | R | 主鍵1，產品條碼 |
| MH23 | 稅率 | 333-347 | 15 | N | R | 適用稅率 (5位小數) |
| MH24 | 版本標記 | 348-352 | 5 | A | R | 固定值：'KN' |
| MH25 | KN特殊碼 | 353-357 | 5 | A | R | KN版本特殊代碼 |
| MH26 | 對應標準碼 | 358-370 | 13 | A | R | 對應標準版產品代號 |
| MH27 | 轉換比率 | 371-385 | 15 | N | R | 與標準版轉換比率 |
| MH28 | 條碼類型 | 386-390 | 5 | A | R | 條碼類型 |
| MH29 | 條碼狀態 | 391 | 1 | A | R | 'A'-有效，'I'-無效 |
| MHXX | 建立日期 | 392-399 | 8 | N | R | 格式：YYYYMMDD |
| MHYY | 建立時間 | 400-405 | 6 | N | R | 格式：HHMMSS |
| MHZZ | 建立者 | 406-415 | 10 | A | R | 操作人員 |

## 6. 主鍵欄位

| 鍵值序號 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | MH22 | 條碼 | 升序 |
| 2 | MH01 | 產品代號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：MH22 + MH01
- **索引類型**：PRIMARY
- **說明**：條碼 + 產品代號複合升序排序

### 輔助索引
1. **產品代號索引**：MH01 + MH22 (產品代號 + 條碼)
2. **品牌分類索引**：MH06 + MH07 + MH22 + MH01 (品牌 + 分類 + 條碼 + 產品)
3. **產品狀態索引**：MH05 + MH22 + MH01 (產品狀態 + 條碼 + 產品)
4. **供應商索引**：MH16 + MH22 + MH01 (供應商 + 條碼 + 產品)
5. **條碼類型索引**：MH28 + MH22 + MH01 (條碼類型 + 條碼 + 產品)
6. **條碼狀態索引**：MH29 + MH22 + MH01 (條碼狀態 + 條碼 + 產品)
7. **KN特殊索引**：MH25 + MH22 + MH01 (KN特殊碼 + 條碼 + 產品)
8. **成本售價索引**：MH10 + MH11 + MH22 + MH01 (成本 + 售價 + 條碼 + 產品)

### 邏輯檢視特性
- **基底檔案**：MTMHPF
- **檢視類型**：條碼排序檢視
- **排序方式**：條碼 + 產品代號
- **專用功能**：條碼查詢和管理

## 8. 備註

### 設計考量
1. 此檔案為 MTMHPF 的邏輯檢視檔案
2. 提供依條碼排序的產品檢視
3. 適合條碼查詢和 POS 系統使用

### 特殊功能
- **條碼查詢**：快速條碼查詢功能
- **POS 支援**：支援 POS 系統條碼掃描
- **條碼管理**：條碼狀態管理
- **排序優化**：條碼優先排序

### 條碼排序優勢
- **快速查詢**：條碼查詢效能優化
- **掃描支援**：支援條碼掃描設備
- **順序管理**：條碼順序管理
- **重複檢查**：條碼重複檢查

### 使用場景
1. **POS 系統**：POS 銷售系統條碼查詢
2. **庫存盤點**：條碼掃描盤點作業
3. **條碼管理**：條碼建立和維護
4. **快速查詢**：條碼快速產品查詢

### 條碼管理功能
- **條碼類型**：支援多種條碼類型
- **狀態管理**：條碼有效性管理
- **重複檢查**：防止條碼重複
- **批次處理**：條碼批次作業

### 排序邏輯
- **第一層排序**：條碼 (MH22) 升序
- **第二層排序**：產品代號 (MH01) 升序
- **特殊處理**：空條碼排在最後

### 參考關聯
- **實體檔案**：MTMHPF (產品基本資料檔 KN)
- **標準版檔案**：MTMALF2 (對應標準版檔案)
- **品牌檔案**：PA#ALF1 (MH06 = #A01)
- **分類檔案**：PA#分類檔 (MH07 = 分類代號)
- **供應商檔案**：MTMBPF (MH16 = MB01)
- **採購員檔案**：MTMCPF (MH17 = MC01)

### 業務規則
1. 顯示順序：條碼 + 產品代號
2. 條碼不可重複
3. 版本標記固定為 'KN'
4. 條碼狀態需有效

### 條碼標準
- **條碼長度**：最大13位
- **條碼格式**：支援多種國際標準
- **檢查碼**：自動計算檢查碼
- **列印格式**：標準條碼列印格式

### POS 系統整合
- **掃描支援**：支援各種條碼掃描器
- **即時查詢**：即時產品資訊查詢
- **價格取得**：自動取得產品價格
- **庫存檢查**：即時庫存狀況檢查

### 資料完整性
1. 資料內容完全依賴 MTMHPF 實體檔案
2. MH22 條碼必須唯一且有效
3. MH24 版本標記必須為 'KN'
4. MH29 條碼狀態需為有效值

### 使用注意事項
1. 此為邏輯檔案，不可直接寫入資料
2. 所有異動需透過 MTMHPF 實體檔案進行
3. 條碼變更會影響排序順序
4. 適用於條碼管理和 POS 系統整合 