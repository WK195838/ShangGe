# ARAFLF2 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARAFLF2 |
| 檔案描述 | 價差折讓資料檔邏輯檔案2 |
| 檔案類型 | 邏輯檔案 (Logical File) |
| 基礎實體檔 | ARAFPF |
| 作業系統 | IBM i (AS/400) |
| 程式語言 | DDS |

## 2. 檔案功能說明

ARAFLF2是基於價差折讓資料實體檔ARAFPF的邏輯檔案，提供以下功能：
- 以發票年月(AF06)、客戶代號(AF02)的組合作為存取路徑
- 支援按發票年月、客戶順序查詢價差折讓資料
- 適用於需要依月份統計價差折讓業務的作業

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | ARAFPF | 實體檔案 | 價差折讓資料主檔 |
| 2 | ARAFLF2 | 邏輯檔案 | 價差折讓資料檔邏輯檔案2 |

## 4. 紀錄格式

| 紀錄格式名稱 | 說明 | 基礎檔案 |
|--------------|------|----------|
| AF0 | 價差折讓資料紀錄格式 | ARAFPF |

## 5. 欄位規格

ARAFLF2使用與基礎實體檔ARAFPF相同的欄位結構，主要欄位包括：

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|
| AF02 | 客戶代號 | 3-8 | 6 | 文字 | 必填欄位 |
| AF06 | 發票年月 | 17-20 | 4 | 數值 | 格式YYMM |
| ... | ... | ... | ... | ... | (其他欄位同ARAFPF) |

## 6. 主鍵欄位

ARAFLF2本身為邏輯檔案，無獨立主鍵定義，其資料完整性由基礎實體檔ARAFPF維護。

## 7. 索引資料

| 索引名稱 | 索引欄位 | 排序 | 說明 |
|----------|----------|------|------|
| 主要索引 | AF06 + AF02 | 升序 | 發票年月+客戶代號 |

### 索引鍵值組成：
1. AF06 (發票年月) - 升序排列
2. AF02 (客戶代號) - 升序排列

## 8. 備註

### 設計考量：
- 以發票年月為主要排序鍵，便於月份統計分析
- 以客戶代號為次要排序鍵，同月份下可依客戶區分
- 提供月份層級的價差折讓資料存取路徑

### 使用時機：
- 月份價差折讓統計報表
- 客戶月份價差折讓查詢作業
- 價差折讓趨勢分析
- 月結作業相關處理

### 注意事項：
- 本邏輯檔案依賴ARAFPF實體檔案的資料完整性
- 索引設計以月份為主軸，適合月份統計分析
- AF06欄位格式為YYMM，需注意年份轉換問題
- 適用於需要按月份進行價差折讓分析的管理報表 