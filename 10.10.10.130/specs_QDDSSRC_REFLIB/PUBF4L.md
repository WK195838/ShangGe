# PUBF4L 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | PUBF4L |
| 檔案類型 | 邏輯檔 (LF) |
| 檔案說明 | F4輔助檔案邏輯檔 (F4 HELP FILE) |
| 主索引鍵 | FPPGM+FPSCR+FPROW |
| 實體檔案 | PUBF4F |
| 建立日期 | (依實際建立日期填入) |
| 維護人員 | (依實際維護人員填入) |

## 2. 檔案功能說明

此邏輯檔案提供F4輔助檔案的不同檢視方式，以程式名稱、畫面名稱、欄位位置列進行排序。

### 主要功能
- 提供F4輔助檔案的替代檢視介面
- 依據程式名稱、畫面名稱、位置列進行排序存取
- 支援按欄位位置查詢F4功能設定

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 | 關聯 |
|----------|----------|------|------|
| PUBF4L | LF | F4輔助檔案邏輯檔 | 主檔案 |
| PUBF4F | PF | F4輔助檔案實體檔 | 實體檔案參照 |

## 4. 記錄格式

### 記錄格式名稱：F4REC

| 格式名稱 | 格式說明 | 參照檔案 | 重新命名 |
|----------|----------|----------|----------|
| F4REC | F4輔助記錄格式 | PUBF4F | 無重新命名 |

## 5. 欄位規格

### 欄位定義

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| FPPGM | 程式名稱 | 1 | 10 | 文字 | KEY | 主鍵欄位 |
| FPSCR | 畫面名稱 | 2 | 6 | 文字 | KEY | 主鍵欄位 |
| FPROW | 欄位位置列 | 3 | 3 | 數值 | 0, KEY | 主鍵欄位 |
| SEQ | F4序號 | - | 3 | 數值 | 0 | 非主鍵欄位 |
| FPCOLS | 欄位位置行起 | - | 3 | 數值 | 0 | 非主鍵欄位 |
| FPCOLE | 欄位位置行迄 | - | 3 | 數值 | 0 | 非主鍵欄位 |
| FCPGM | 呼叫程式名稱 | - | 10 | 文字 | | 非主鍵欄位 |
| CPARM | 呼叫參數 | - | 10 | 文字 | | 非主鍵欄位 |
| TEXT | 說明資料 | - | 20 | 文字 | O | 非主鍵欄位 |

## 6. 主鍵欄位

| 順序 | 欄位代號 | 欄位名稱 | 排序 |
|------|----------|----------|------|
| 1 | FPPGM | 程式名稱 | 升序 |
| 2 | FPSCR | 畫面名稱 | 升序 |
| 3 | FPROW | 欄位位置列 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：FPPGM+FPSCR+FPROW
- **索引類型**：複合索引，全部升序排列
- **唯一性**：依實體檔案設定

### 索引用途
- 依程式名稱優先檢視F4設定
- 依畫面名稱細分同程式的F4功能
- 依欄位位置列排序螢幕位置資料

## 8. 備註

### 特殊說明
- 此邏輯檔案參照 PUBF4F 實體檔案
- 使用與實體檔案不同的主鍵排序
- 以FPROW(欄位位置列)取代SEQ(F4序號)作為第三個主鍵
- 檔案結構設計用於按位置查詢F4功能

### 與實體檔案的差異
實體檔案 PUBF4F 主鍵：FPPGM+FPSCR+SEQ
邏輯檔案 PUBF4L 主鍵：FPPGM+FPSCR+FPROW

### 檔案用途
- 用於按螢幕位置查詢F4功能設定
- 支援依位置列排序的F4資料檢視
- 提供不同於實體檔案的存取路徑

### 相關檔案
- PUBF4F（F4輔助檔案實體檔）

### 維護注意事項
- 邏輯檔案結構變更需同步更新實體檔案
- 複合主鍵需確保正確性和一致性
- 位置導向索引適用於螢幕佈局相關查詢
- 資料異動透過實體檔案進行

### 系統整合
- 配合F4功能的螢幕位置管理
- 支援按位置排序的F4設定檢視
- 適用於畫面設計工具的整合應用
- 提供位置導向的F4功能查詢介面 