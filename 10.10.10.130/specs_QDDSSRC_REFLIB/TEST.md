# TEST 檔案規格書

## 1. 基本資料

| 欄位 | 內容 |
|------|------|
| 檔案名稱 | TEST |
| 檔案描述 | 庫存異動明細檔 |
| 檔案類型 | 邏輯檔案 (LF) |
| 記錄格式 | IL0 |
| 關鍵字 | IR03+IR02+IR01+IR04+IR06 |
| 實體檔案 | IMILPF |
| 作業系統 | AS/400 |
| 資料庫 | DB2/400 |
| 存取方式 | 索引存取 |

## 2. 檔案功能說明

庫存異動明細檔邏輯檔案是基於IMILPF實體檔案建立的測試檔案，主要用於庫存異動資料的查詢與分析。本檔案提供按產品編號、庫位點、期數編號、異動日期、供應商統編排序的庫存異動資料存取功能，支援庫存管理系統的資料分析需求。

## 3. 系統檔案清單

| 相關檔案 | 檔案名稱 | 說明 |
|----------|----------|------|
| 邏輯檔案 | TEST | 庫存異動明細檔邏輯檔 |
| 實體檔案 | IMILPF | 庫存異動實體檔 |
| 相關檔案 | POPGPF | 產品異動管理檔 |
| 相關檔案 | SOSDPF | 銷貨收入明細檔 |

## 4. 紀錄格式

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| IR01 | 期數編號第一位 | 1-1 | 1 | 文字 | 索引3 | 期數編號首位(IL01第1位) |
| IR02 | 庫位點 | 2-6 | 5 | 文字 | 索引2 | 庫位點編號(重命名IL03) |
| IR03 | 產品編號 | 7-11 | 5 | 文字 | 索引1 | 產品編號(重命名IL05) |
| IR04 | 異動日期 | 12-18 | 7 | 文字 | 索引4,DESC | 異動日期(重命名IL04) |
| IR05 | 編號 | 19-20 | 2 | 文字 | - | 編號(IL02第3-4位) |
| IR051 | 編號 | 21-21 | 1 | 文字 | 選擇 | 編號(IL02第4位)<'0' |
| IR06 | 供應商統編 | 22-33 | 12 | 文字 | 索引5 | 供應商統編(重命名IL02) |
| IR071 | 數量 | 34-39 | 6,0 | 數值 | - | 數量(重命名IL06) |
| IR09 | 進出碼 | 40-40 | 1 | 文字 | - | 進出碼(重命名IL07) |
| IR121 | 確認數量 | 41-46 | 6,0 | 數值 | - | 確認數量(重命名IL06) |

## 5. 主鍵欄位

- **排序鍵**：IR03+IR02+IR01+IR04+IR06 (產品編號+庫位點+期數編號+異動日期+供應商統編)
- **索引類型**：複合索引
- **排序方式**：IR04為降序(DESCEND)，其餘遞增
- **選擇條件**：IR051 COMP(LT '0')

## 6. 索引資料

| 索引名稱 | 索引欄位 | 索引類型 | 說明 |
|----------|----------|----------|------|
| PRIMARY | IR03+IR02+IR01+IR04+IR06 | LOGICAL | 庫存異動複合索引 |

## 7. 使用說明

1. **庫存異動查詢**：按產品編號查詢庫存異動記錄
2. **庫位管理**：按庫位點進行庫存資料分類查詢
3. **時間序列分析**：按異動日期降序查看最新異動記錄
4. **供應商追蹤**：按供應商統編追蹤相關異動記錄
5. **進出管理**：透過進出碼(+1/-1)區分進貨與出貨

## 8. 備註

- 邏輯檔案基於IMILPF實體檔案建立
- 使用RENAME功能重新命名欄位以提供更直觀的名稱
- IR04異動日期採用降序排列，便於查看最新記錄
- IR051選擇條件(< '0')用於篩選特定類型的異動記錄
- IR09進出碼：+1=進貨，-1=出貨，空白=依IR09欄位決定
- 支援庫存管理系統的多維度查詢與分析需求
- 作為測試檔案，可用於庫存系統功能驗證與資料分析 