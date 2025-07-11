# ARACLF121 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARACLF121 |
| 檔案類型 | LF (Logical File) |
| 檔案說明 | 收款主檔 key=ac01+ac12+ac11+ac07+ac06 (s) |
| 基礎檔案 | ARACPF (收款主檔) |
| 建立日期 | - |
| 修改日期 | - |
| 程式設計師 | - |

## 2. 檔案功能說明

ARACLF121 是收款主檔 (ARACPF) 的邏輯檔案，提供以公司代號、預計兌現日期、收款號碼為排序的資料存取路徑。此檔案具有選擇條件，僅包含收款兌現日期不等於0的記錄。主要用於已兌現收款資料的查詢與報表處理，特別是需要按公司別和預計兌現日期進行已兌現收款管理的應用程式。

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| ARACLF121 | LF | 收款主檔邏輯檔案 (含選擇條件) |
| ARACPF | PF | 收款主檔實體檔案 (基礎檔案) |

## 4. 紀錄格式

| 記錄格式名稱 | 說明 |
|--------------|------|
| AC0 | 收款主檔記錄格式 |

基礎檔案：ARACPF (收款主檔)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|----------|
| AC01 | 公司代號 | - | - | 索引鍵 | 公司代號 |
| AC07 | 預計兌現日期 | - | - | 索引鍵 | 預計兌現日期 |
| AC06 | 收款號碼 | - | - | 索引鍵 | 收款號碼 |
| AC11 | 收款兌現日期 | - | - | 選擇條件 | 必須不等於0 |

註：其他欄位繼承自基礎檔案 ARACPF

## 6. 主鍵欄位

| 主鍵序號 | 欄位代號 | 欄位名稱 | 排序方式 |
|----------|----------|----------|----------|
| 1 | AC01 | 公司代號 | 升序 |
| 2 | AC07 | 預計兌現日期 | 升序 |
| 3 | AC06 | 收款號碼 | 升序 |

## 7. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| 主索引 | AC01+AC07+AC06 | 唯一索引 | 提供以公司、預計兌現日期、收款號碼排序的存取路徑 |

**選擇條件**：
- AC11 ≠ 0 (收款兌現日期不等於0，即已兌現記錄)

## 8. 備註

1. 此邏輯檔案基於 ARACPF 收款主檔
2. 具有選擇條件：僅包含 AC11≠0 的記錄，即已兌現的收款資料
3. AC07 (預計兌現日期) 採用升序排列，與其他類似檔案的降序不同
4. 以公司代號 (AC01) 為第一排序鍵，適用於多公司環境
5. 與 ARACLF06、ARACLF12 有相同的選擇條件，但索引結構更簡化
6. 提供按預計兌現日期升序排列的已兌現收款管理視角
7. 適用於需要按時間順序查詢已兌現收款的作業
8. 繼承基礎檔案 ARACPF 的所有欄位定義和屬性 