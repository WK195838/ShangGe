# WFJL10LF 檔案規格書

## 1. 基本資料

| 欄位 | 內容 |
|------|------|
| 檔案名稱 | WFJL10LF |
| 檔案描述 | 傳票－暫存檔邏輯檔 |
| 檔案類型 | 邏輯檔案 (LF) |
| 記錄格式 | WFJL10R |
| 關鍵字 | JL1001+JL1002+J1002$+JL1003+J1003$+JL1004+JL1005+JL1006+JL1007+JL1008+JL1009+JL1010+JL1011 |
| 實體檔案 | WFJL10PF |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |
| 存取方式 | 索引存取 |

## 2. 檔案功能說明

WFJL10LF是基於WFJL10PF傳票暫存檔建立的邏輯檔，提供完整的傳票資料排序存取功能。本邏輯檔整合確認日期、期數編號、處理編號、會計科目、會計子科目等多維度排序，支援傳票系統的複雜查詢與處理需求。

## 3. 系統檔案清單

| 相關檔案 | 檔案名稱 | 說明 |
|----------|----------|------|
| 邏輯檔案 | WFJL10LF | 傳票暫存邏輯檔 |
| 實體檔案 | WFJL10PF | 傳票暫存檔 |
| 參考檔案 | GLRF | 會計總帳參考檔 |

## 4. 紀錄格式

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| JL1001 | 確認日期 | 1-8 | 8,0 | 數值 | 索引1 | 確認日期 |
| JL1002 | 期數編號 | 9-11 | 3 | 文字 | 索引2 | 期數編號 |
| J1002$ | 處理編號 | 12-12 | 1 | 文字 | 索引3 | 處理編號 |
| JL1003 | 傳票編號 | 13-13 | 1 | 文字 | 索引4 | 傳票編號 |
| J1003$ | 借貸編號 | 14-14 | 1 | 文字 | 索引5 | 借貸編號 |
| JL1004 | 會計科目 | 15-18 | 4 | 文字 | 索引6 | 會計科目代碼 |
| JL1005 | 會計子科目 | 19-21 | 3 | 文字 | 索引7 | 會計子科目代碼 |
| JL1006 | 部門編號 | 22-23 | 2 | 文字 | 索引8 | 部門編號 |
| JL1007 | 摘要統編第一位 | 24-35 | 12 | 文字 | 索引9 | 摘要統編第一位 |
| JL1008 | 摘要統編第二位 | 36-47 | 12 | 文字 | 索引10 | 摘要統編第二位 |
| JL1009 | 幣別 | 48-50 | 3 | 文字 | 索引11 | 幣別代碼 |
| JL1010 | 數量 | 51-60 | 10,0 | 數值 | 索引12 | 數量 |
| JL1011 | 金額 | 61-70 | 10,0 | 數值 | 索引13 | 金額 |

## 5. 主鍵欄位

- **排序鍵**：JL1001+JL1002+J1002$+JL1003+J1003$+JL1004+JL1005+JL1006+JL1007+JL1008+JL1009+JL1010+JL1011 (十三重複合索引)
- **索引類型**：複合索引
- **排序方式**：遞增排序

## 6. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| PRIMARY | 十三重複合鍵 | LOGICAL | 傳票暫存完整索引 |

## 7. 使用說明

1. **傳票排序查詢**：提供按十三重複合鍵的傳票資料排序存取
2. **會計科目定位**：支援按會計科目與子科目的精確定位
3. **部門別統計**：按部門編號進行傳票資料分類統計
4. **摘要管理**：整合雙重摘要統編的完整摘要管理
5. **複雜查詢支援**：支援傳票系統的複雜多維度查詢需求

## 8. 備註

- 邏輯檔案基於WFJL10PF實體檔案建立
- 十三重複合索引提供極精確的資料定位功能
- 參考GLRF會計總帳檔案進行欄位定義
- 整合確認日期、期數、處理、傳票、借貸等完整傳票資訊
- 支援雙重摘要統編管理
- 為傳票系統提供高效能的多維度存取方式
- 適用於複雜的會計傳票查詢與處理作業 