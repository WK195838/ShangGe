# POPFLF1 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | POPFLF1 |
| 檔案類型 | 邏輯檔 (LF) |
| 檔案說明 | 國外採購完稅主檔邏輯檔 |
| 主索引鍵 | PF04+PF02 (降序+升序) |
| 實體檔案 | POPFPF |
| 建立日期 | (依實際建立日期填入) |
| 維護人員 | (依實際維護人員填入) |

## 2. 檔案功能說明

此邏輯檔案用於提供國外採購完稅資料的特定存取路徑，以單據日期降序、檢索編號升序為主要排序方式。

### 主要功能
- 依單據日期降序、檢索編號升序存取國外採購完稅資料
- 支援最新日期優先的查詢需求
- 提供時間反向導向的國外採購完稅資料檢視

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 | 關聯 |
|----------|----------|------|------|
| POPFLF1 | LF | 國外採購完稅主檔邏輯檔 | 主檔案 |
| POPFPF | PF | 國外採購完稅主檔實體檔 | 實體檔案參照 |

## 4. 記錄格式

### 記錄格式名稱：PF0

| 格式說明 | 記錄長度 | 參照檔案 |
|----------|----------|----------|
| 國外採購完稅主檔邏輯記錄格式 | (參照實體檔) | POPFPF |

## 5. 欄位規格

依實體檔案 POPFPF 的欄位定義。

## 6. 主鍵欄位

| 順序 | 欄位代號 | 欄位名稱 | 排序 |
|------|----------|----------|------|
| 1 | PF04 | 單據日期 | 降序 (DESCEND) |
| 2 | PF02 | 檢索編號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：PF04+PF02
- **索引類型**：複合索引，PF04降序+PF02升序
- **唯一性**：依實體檔案設定

### 索引用途
- 依單據日期降序優先顯示最新的國外採購完稅資料
- 依檢索編號細分同日期資料
- 適用於需要最新資料優先顯示的查詢需求

## 8. 備註

### 特殊說明
- 此邏輯檔案參照實體檔案 POPFPF
- 使用降序排列 (DESCEND) 單據日期，適用於最新資料優先檢視
- 索引組合 PF04(降序)+PF02(升序) 提供時間反向的有序存取
- 註：檔案標題說明為 PF01+PF04+PF02 但實際鍵值為 PF04+PF02

### 相關檔案
- POPFPF（國外採購完稅主檔實體檔）
- POPFLF01（國外採購完稅主檔邏輯檔 - 廠商優先）
- POPFLF02（國外採購完稅主檔邏輯檔 - 日期優先）

### 維護注意事項
- 邏輯檔案結構變更需同步更新實體檔案
- 降序索引設計需考慮查詢效能
- 資料異動透過實體檔案 POPFPF 進行 