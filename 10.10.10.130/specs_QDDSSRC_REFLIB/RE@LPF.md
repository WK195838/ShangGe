# RE@LPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | RE@LPF |
| 檔案類型 | 實體檔 (PF) |
| 檔案說明 | 組拆單號採番檔 |
| 主索引鍵 | @L01+@L02+@L03 |
| 參照檔案 | RERF |
| 建立日期 | (依實際建立日期填入) |
| 維護人員 | (依實際維護人員填入) |

## 2. 檔案功能說明

此實體檔案用於管理組拆單號的採番作業，提供公司別、年度、季年度等分類的組拆單號管理機制。

### 主要功能
- 儲存組拆單號的採番資料
- 管理不同公司、年度的組拆單號分配
- 提供組拆單號的自動編號功能
- 支援多維度的組拆單號分類管理

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 | 關聯 |
|----------|----------|------|------|
| RE@LPF | PF | 組拆單號採番檔 | 主檔案 |
| RERF | PF | 參照檔案 | REF參照 |

## 4. 記錄格式

### 記錄格式名稱：@L0

| 格式說明 | 記錄長度 | 參照檔案 |
|----------|----------|----------|
| 組拆單號採番記錄格式 | (依欄位定義計算) | RERF |

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| @L01 | 公司編號 | 1 | R | 文字 | KEY | 主鍵欄位，參照RERF |
| @L02 | 年度 | 2 | R | 文字 | KEY | 主鍵欄位，參照RERF |
| @L03 | 季年度編號 | 3 | R | 數值 | 2 0, KEY | 主鍵欄位，參照RERF |
| @L04 | 號碼 | 4 | R | 文字 | | 採番號碼，參照RERF |

## 6. 主鍵欄位

| 欄位代號 | 欄位名稱 | 排序 | 說明 |
|----------|----------|------|------|
| @L01 | 公司編號 | 升序 | 複合主鍵第一部分 |
| @L02 | 年度 | 升序 | 複合主鍵第二部分 |
| @L03 | 季年度編號 | 升序 | 複合主鍵第三部分 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：@L01+@L02+@L03
- **索引類型**：唯一索引 (UNIQUE)
- **唯一性**：是

### 檔案特性
- UNIQUE：確保公司編號+年度+季年度編號唯一性
- REF(RERF)：欄位定義參照RERF檔案

## 8. 備註

### 特殊說明
- 此檔案為組拆單號的採番管理檔
- 使用 UNIQUE 關鍵字確保記錄唯一性
- 複合主鍵由公司編號、年度、季年度編號組成
- 使用 REF(RERF) 參照外部檔案定義

### 採番機制
檔案設計支援三維度採番：
- **公司編號**：區分不同公司
- **年度**：區分不同年份
- **季年度編號**：區分季別或特定時期

### 檔案用途
- 用於產品組拆單號的自動編號管理
- 支援多公司、多年度的組拆單號分配
- 提供產品組裝拆解作業的單號控制
- 維護組拆單號的唯一性與連續性

### 參照檔案說明
使用 REF(RERF) 參照：
- 欄位定義統一參照RERF檔案
- 確保欄位規格的一致性
- 便於集中維護欄位定義

### 維護注意事項
- 公司編號+年度+季年度編號組成複合主鍵，不可重複
- 號碼欄位需確保採番的連續性
- 新年度開始需建立新的採番記錄
- 避免同時間多人存取造成號碼重複

### 系統應用
- 用於產品組拆單建立時的自動編號
- 支援多維度的組拆單號管理機制
- 提供生產管理作業的單號控制
- 適用於多公司的環境

### 相關作業
- 產品組拆單建立作業
- 單號採番維護作業
- 年度結轉作業
- 生產管理作業

### 技術特性
- 使用外部參照(REF)確保資料一致性
- 三重複合主鍵提供分類控制
- 支援多時間維度的號碼管理
- 採用唯一約束避免重複編號

### 業務流程整合
- 與生產管理流程整合
- 支援產品組裝拆解作業
- 配合庫存管理系統
- 提供組拆歷史追溯功能

### 組拆管理特性
- 支援產品組裝作業管理
- 支援產品拆解作業管理
- 配合BOM物料管理
- 提供組拆成本計算

### 庫存控制整合
- 配合庫存異動管理
- 支援組拆前後存量控制
- 提供物料需求計算
- 配合生產排程系統 