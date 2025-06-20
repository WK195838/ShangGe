# ARADLF07 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARADLF07 |
| 檔案描述 | 收款明細檔邏輯檔案07 |
| 檔案類型 | 邏輯檔案 (Logical File) |
| 基礎實體檔 | ARADPF |
| 作業系統 | IBM i (AS/400) |
| 程式語言 | DDS |

## 2. 檔案功能說明

ARADLF07是基於收款明細實體檔ARADPF的邏輯檔案，提供以下功能：
- 以發票單號(AD10)、客戶代號(AD02)、單據日期(AD12)的組合作為存取路徑
- 支援按發票單號、客戶代號、日期順序查詢收款明細資料
- 適用於需要依發票單號排序的收款明細查詢作業

## 3. 系統檔案清單

| 序號 | 檔案名稱 | 檔案類型 | 說明 |
|------|----------|----------|------|
| 1 | ARADPF | 實體檔案 | 收款明細主檔 |
| 2 | ARADLF07 | 邏輯檔案 | 收款明細檔邏輯檔案07 |

## 4. 紀錄格式

| 紀錄格式名稱 | 說明 | 基礎檔案 |
|--------------|------|----------|
| AD0 | 收款明細紀錄格式 | ARADPF |

## 5. 欄位規格

ARADLF07使用與基礎實體檔ARADPF相同的欄位結構，主要欄位包括：

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|
| AD01 | 公司別 | 1-2 | 2 | 文字 | 必填欄位 |
| AD02 | 客戶代號 | 3-8 | 6 | 文字 | 必填欄位 |
| AD10 | 發票單號 | 19-28 | 10 | 文字 | 必填欄位 |
| AD12 | 單據日期 | 31-38 | 8 | 數值 | 日期格式YYYYMMDD |
| ... | ... | ... | ... | ... | (其他欄位同ARADPF) |

## 6. 主鍵欄位

ARADLF07本身為邏輯檔案，無獨立主鍵定義，其資料完整性由基礎實體檔ARADPF維護。

## 7. 索引資料

| 索引名稱 | 索引欄位 | 排序 | 說明 |
|----------|----------|------|------|
| 主要索引 | AD10 + AD02 + AD12 | 升序 | 發票單號+客戶代號+單據日期 |

### 索引鍵值組成：
1. AD10 (發票單號) - 升序排列
2. AD02 (客戶代號) - 升序排列  
3. AD12 (單據日期) - 升序排列

## 8. 備註

### 設計考量：
- 以發票單號為主要排序鍵，便於按發票查詢相關收款明細
- 次要排序為客戶代號，同一發票下可依客戶區分
- 第三排序為單據日期，提供時間順序參考

### 使用時機：
- 發票收款明細查詢作業
- 按發票單號產生收款明細報表
- 發票收款狀況分析作業

### 注意事項：
- 本邏輯檔案依賴ARADPF實體檔案的資料完整性
- 索引鍵值的組合確保資料存取的效率性
- 適用於以發票為主軸的收款管理作業 