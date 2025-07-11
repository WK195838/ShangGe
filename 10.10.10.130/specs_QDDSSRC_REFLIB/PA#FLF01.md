# PA#FLF01 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | PA#FLF01 |
| 檔案描述 | 物流點代碼∣∣客戶－試飲收回 |
| 檔案類型 | LF (Logical File) |
| 記錄格式 | #F0 |
| 主鍵 | #F01 + #F02 (物流點代號 + 客戶代號) |
| 實體檔案 | PA#FPF |
| 檔案屬性 | 邏輯檢視，條件：試飲收回業務 |

## 2. 檔案功能說明

PA#FLF01 為物流點代碼與客戶關聯檔的試飲收回專用邏輯檔案，提供：
- 試飲收回客戶檢視
- 物流收回管理
- 試飲業務分析
- 收回效率統計

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 說明 |
|----------|----------|------|
| PA#FLF01 | 物流點試飲收回邏輯檔 | 主檔 |
| PA#FPF | 物流點代碼客戶實體檔 | 實體檔案 |
| PA#FLF | 物流點代碼客戶邏輯檔 | 基本邏輯檔 |
| RERF | 參考檔案 | 欄位定義參考 |

## 4. 紀錄格式

### 記錄格式：#F0 (繼承自 PA#FPF，條件篩選)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| #F01 | 物流點代號 | 1-5 | 5 | A | R | 主鍵，物流點識別碼 |
| #F02 | 客戶代號 | 6-12 | 7 | A | R | 主鍵，客戶識別碼 |
| #F03 | 業務類型 | 13-17 | 5 | A | R | 固定值：'TASTE' |
| #F04 | 客戶名稱 | 18-35 | 18 | A | R | 客戶中文名稱 |
| #F05 | 地區代號 | 36-40 | 5 | A | R | 客戶所屬地區 |
| #F06 | 區域代號 | 41-45 | 5 | A | R | 客戶所屬區域 |
| #F07 | 業務員 | 46-50 | 5 | A | R | 負責業務員代號 |
| #F08 | 關聯狀態 | 51 | 1 | A | R | 'A'-有效，'I'-停用 |
| #F09 | 優先順序 | 52-54 | 3 | N | R | 收回優先順序 |
| #F10 | 收回方式 | 55 | 1 | A | R | 'D'-直送，'C'-集中，'S'-分批 |
| #F11 | 收回頻率 | 56-58 | 3 | N | R | 收回頻率 (天) |
| #F12 | 最大容量 | 59-67 | 9 | N | R | 最大收回容量 |
| #F13 | 收回成本 | 68-76 | 9 | N | R | 單次收回成本 |
| #F14 | 聯絡電話 | 77-91 | 15 | A | R | 收回聯絡電話 |
| #F15 | 特殊說明 | 92-131 | 40 | A | R | 收回特殊說明 |
| #FXX | 建立日期 | 132-139 | 8 | N | R | 格式：YYYYMMDD |
| #FYY | 建立時間 | 140-145 | 6 | N | R | 格式：HHMMSS |
| #FZZ | 建立者 | 146-155 | 10 | A | R | 操作人員 |

## 6. 主鍵欄位

| 鍵值序號 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | #F01 | 物流點代號 | 升序 |
| 2 | #F02 | 客戶代號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：物流點客戶索引
- **索引欄位**：#F01 + #F02
- **索引類型**：PRIMARY
- **說明**：物流點代號 + 客戶代號複合升序排序

### 輔助索引
1. **收回方式索引**：#F10 + #F09 + #F01 + #F02
2. **優先順序索引**：#F09 + #F01 + #F02
3. **地區索引**：#F05 + #F01 + #F02
4. **業務員索引**：#F07 + #F01 + #F02
5. **頻率索引**：#F11 + #F01 + #F02
6. **容量索引**：#F12 + #F01 + #F02
7. **成本索引**：#F13 + #F01 + #F02

### 邏輯檢視特性
- **基底檔案**：PA#FPF
- **檢視類型**：試飲收回專用檢視
- **排序方式**：優先順序 + 物流點 + 客戶
- **分組顯示**：依收回方式分組
- **過濾條件**：#F03 = 'TASTE'

## 8. 備註

### 設計考量
1. 此檔案為 PA#FPF 的試飲收回專用邏輯檢視檔案
2. 提供試飲業務收回管理功能
3. 支援物流收回效率分析

### 特殊功能
- **收回規劃**：按優先順序規劃收回路線
- **方式管理**：支援多種收回方式
- **成本控制**：收回成本分析管理
- **效率統計**：收回效率統計分析

### 收回方式說明
- **D級 (直送)**：直接到客戶處收回
- **C級 (集中)**：集中收回方式
- **S級 (分批)**：分批收回方式

### 優先順序邏輯
- **數值越小**: 優先度越高
- **001-100**: 高優先度客戶
- **101-500**: 中優先度客戶
- **501-999**: 低優先度客戶

### 參考關聯
- **實體檔案**：PA#FPF (#F03 = 'TASTE')
- **物流點檔案**：PA#物流點檔 (#F01 = 物流點代號)
- **客戶檔案**：MTMDPF (#F02 = MD01)
- **業務員檔案**：MTMCPF (#F07 = MC01)
- **地區檔案**：PA#DPF (#F05 = #D01)

### 業務規則
1. 顯示順序：優先順序 + 物流點 + 客戶
2. 僅顯示試飲收回業務 (#F03 = 'TASTE')
3. 優先順序需定期評估調整
4. 收回頻率需配合業務需求

### 資料完整性
1. 資料內容完全依賴 PA#FPF 實體檔案
2. 僅顯示 #F03 = 'TASTE' 的記錄
3. #F01 需對應有效的物流點代號
4. #F02 需對應 MTMDPF 中的有效客戶

### 使用注意事項
1. 此為邏輯檔案，不可直接寫入資料
2. 所有異動需透過 PA#FPF 實體檔案進行
3. 新增試飲收回關聯時需設定 #F03 = 'TASTE'
4. 適用於試飲業務收回管理與物流規劃 