# ARADLF03 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARADLF03 |
| 檔案類型 | LF (Logical File) |
| 檔案說明 | 收款明細檔 key=ad07+ad04+ad05+ad06 |
| 基礎檔案 | ARADPF (收款明細檔) |
| 建立日期 | - |
| 修改日期 | - |
| 程式設計師 | - |

## 2. 檔案功能說明

ARADLF03 是收款明細檔 (ARADPF) 的邏輯檔案，提供以發票日期(降序)、客戶代號、發票號碼、收款日期、收款序號、收款號碼、預計兌現日期為排序的資料存取路徑。此檔案不含選擇條件，包含所有收款明細記錄。主要用於收款明細資料的查詢與報表處理，特別是需要按發票日期進行收款明細管理的應用程式。

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| ARADLF03 | LF | 收款明細檔邏輯檔案 |
| ARADPF | PF | 收款明細檔實體檔案 (基礎檔案) |

## 4. 紀錄格式

| 記錄格式名稱 | 說明 |
|--------------|------|
| AD0 | 收款明細檔記錄格式 |

基礎檔案：ARADPF (收款明細檔)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|
| AD11 | 發票日期 | - | - | 索引鍵(降序) | 發票日期，降序排列 |
| AD02 | 客戶代號 | - | - | 索引鍵 | 客戶代號 |
| AD03 | 發票號碼 | - | - | 索引鍵 | 發票號碼 |
| AD04 | 收款日期 | - | - | 索引鍵 | 收款日期 |
| AD05 | 收款序號 | - | - | 索引鍵 | 收款序號 |
| AD06 | 收款號碼 | - | - | 索引鍵 | 收款號碼 |
| AD07 | 預計兌現日期 | - | - | 索引鍵 | 預計兌現日期 |

註：其他欄位繼承自基礎檔案 ARADPF

## 6. 主鍵欄位

| 主鍵序號 | 欄位代號 | 欄位名稱 | 排序方式 |
|----------|----------|----------|----------|
| 1 | AD11 | 發票日期 | 降序 |
| 2 | AD02 | 客戶代號 | 升序 |
| 3 | AD03 | 發票號碼 | 升序 |
| 4 | AD04 | 收款日期 | 升序 |
| 5 | AD05 | 收款序號 | 升序 |
| 6 | AD06 | 收款號碼 | 升序 |
| 7 | AD07 | 預計兌現日期 | 升序 |

## 7. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| 主索引 | AD11(DESC)+AD02+AD03+AD04+AD05+AD06+AD07 | 唯一索引 | 提供以發票日期(降序)、客戶、發票、收款日期、序號、號碼、預計兌現日期排序的存取路徑 |

## 8. 備註

1. 此邏輯檔案基於 ARADPF 收款明細檔
2. 不含選擇條件，包含所有收款明細記錄
3. AD11 (發票日期) 採用降序排列，便於查詢最新的發票明細
4. 以發票日期為第一排序鍵，適用於按發票時間管理收款明細
5. 索引鍵包含完整的收款明細識別資訊
6. 適用於需要按發票日期排序的收款明細查詢作業
7. 與收款主檔的邏輯檔案對應，提供明細層級的資料存取
8. 繼承基礎檔案 ARADPF 的所有欄位定義和屬性 