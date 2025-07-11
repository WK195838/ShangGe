# SOVPPF 檔案規格書

## 1. 基本資料

| 欄位 | 內容 |
|------|------|
| 檔案名稱 | SOVPPF |
| 檔案描述 | 媒體申報工作延伸檔 |
| 檔案類型 | 實體檔案 (PF) |
| 記錄格式 | VP0 |
| 關鍵字 | VP91+VP92+VP04+VP02+VP03 |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |
| 存取方式 | 索引存取 |

## 2. 檔案功能說明

媒體申報工作延伸檔是媒體申報系統的延伸檔案，記錄媒體申報相關的補充資訊與控制資料。本檔案與媒體申報主檔配合使用，提供媒體申報作業的完整資料管理功能，支援稅務申報的準確性與完整性。

## 3. 系統檔案清單

| 相關檔案 | 檔案名稱 | 說明 |
|----------|----------|------|
| 主檔案 | SOVPPF | 媒體申報工作延伸檔 |
| 工作檔 | SOVQPF | 媒體申報工作檔 |
| 人工檔 | SOVRPF | 媒體申報人工輸入檔 |
| 申報檔 | SOVTPF | 媒體申報檔 |

## 4. 紀錄格式

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| VP91 | 期數編號 | 1-2 | 2 | 文字 | 主鍵1 | 申報期數識別 |
| VP92 | 類型處理 | 3-3 | 1 | 文字 | 主鍵2 | 申報類型處理碼 |
| VP01 | 來源 | 4-5 | 2 | 文字 | - | S0/R0/F0/AP/PC等來源類型 |
| VP02 | 供應商統編 | 6-17 | 12 | 文字 | 主鍵3 | 供應商統一編號 |
| VP03 | 發票統編 | 18-31 | 14 | 文字 | 主鍵4 | 發票統一編號 |
| VP04 | 發票年月 | 32-37 | 6,0 | 數值 | 主鍵5 | 發票年月(YYYYMM) |
| VP07 | 統一編號或證件 | 38-46 | 9,0 | 數值 | - | 統一編號或身分證字號 |
| VP08 | 營業稅編號 | 47-47 | 1 | 文字 | - | 營業稅編號標記 |
| VP09 | 營業稅額 | 48-56 | 9,0 | 數值 | - | 營業稅額 |
| VP97 | 建立日期 | 57-64 | 8,0 | 數值 | - | 記錄建立日期 |
| VP98 | 建立時間 | 65-70 | 6,0 | 數值 | - | 記錄建立時間 |
| VP99 | 建立者 | 71-80 | 10 | 文字 | - | 記錄建立者 |

## 5. 主鍵欄位

- **主鍵**：VP91+VP92+VP04+VP02+VP03 (期數編號+類型處理+發票年月+供應商統編+發票統編)
- **索引類型**：UNIQUE
- **排序方式**：遞增排序

## 6. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| PRIMARY | VP91+VP92+VP04+VP02+VP03 | UNIQUE | 主索引，媒體申報複合鍵 |

## 7. 使用說明

1. **媒體申報延伸**：提供媒體申報作業的延伸資料管理
2. **來源類型管理**：支援多種資料來源類型(S0/R0/F0/AP/PC)
3. **期數控制**：按申報期數進行資料分組管理
4. **稅額記錄**：記錄營業稅額與相關稅務資訊
5. **稽核追蹤**：保留完整的建立軌跡資訊

## 8. 備註

- 使用UNIQUE屬性確保申報資料的唯一性
- 複合主鍵設計支援多維度的申報資料管理
- 來源欄位支援系統間(S0)、入帳間(R0)、檔案間(F0)、應付(AP)、采購(PC)等多種來源
- 與媒體申報系統其他檔案整合，提供完整的申報資料處理
- 所有稅額欄位採用數值格式，確保計算準確性 