# REWF94 檔案規格書

## 1. 基本資料
- **檔案代號**: REWF94
- **檔案名稱**: 試飲分析表（B）
- **檔案類型**: PF (實體檔案)
- **記錄格式**: WF940
- **系統**: AS/400 RPG
- **功能**: 管理試飲活動的分析資料（B類型）

## 2. 檔案功能說明
試飲分析表（B）是試飲管理系統的第二類分析檔案，記錄試飲活動的詳細分析資料，包含年齡層、組別、年度、品牌、價位、容量、產品名稱等重要分析維度，並提供多種成本與價格計算分析。

## 3. 系統檔案清單
- 主檔案：REWF94 (試飲分析表B)
- 參考檔案：RERF (參考主檔)
- 關聯檔案：SC (價格檔)、MA (產品主檔)

## 4. 紀錄格式
### 記錄格式：WF940

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|----------|----------|------|------|------|------|----------|------|
| WF9412 | 年齡層 | - | R | 文字 | 顯示 | SC27 | 客戶年齡層分類 |
| WF9401 | 組別 | - | R | 文字 | 顯示 | SC10 | 產品組別分類 |
| WF9402 | 年度 | - | R | 文字 | 顯示 | MA10 | 分析年度 |
| WF9403 | 品牌 | - | R | 文字 | 顯示 | MA07 | 產品品牌代號 |
| WF9404 | 價位 | - | R | 文字 | 顯示 | SC04 | 產品價位等級 |
| WF9405 | 容量 | - | R | 文字 | 顯示 | SC05 | 產品容量規格 |
| WF9406 | 產品名稱 | - | R | 文字 | 顯示 | MA01 | 產品名稱說明 |
| WF9407 | 數量 | 5 | 5 | 數字 | 顯示 | - | 試飲數量統計 |
| WF9408 | 標準成本單價金額 | 11 | 11 | 數字 | 小數2位 | - | 標準成本計算 |
| WF9409 | FOB-售價金額 | 11 | 11 | 數字 | 小數2位 | - | FOB價格計算 |
| WF9410 | FHI-售價金額 | 11 | 11 | 數字 | 小數2位 | - | FHI價格計算 |
| WF9411 | DUTY售價金額 | 11 | 11 | 數字 | 小數2位 | - | 關稅價格計算 |

## 6. 主鍵欄位
- **複合主鍵**:
  - WF9412 (年齡層)
  - WF9401 (組別)
  - WF9402 (年度)
  - WF9404 (價位)
  - WF9405 (容量)
  - WF9406 (產品名稱)

## 7. 索引資料
- 主要索引：依年齡層、組別、年度、價位、容量、產品名稱排序
- 特殊設計：品牌欄位(WF9403)未納入主鍵
- 檔案結構：多層複合主鍵索引

## 8. 備註
- 此檔案為試飲分析系列的B類型檔案
- 新增年齡層分析維度，提供更細緻的客戶分析
- 支援多種價格計算分析（標準成本、FOB、FHI、DUTY）
- 主鍵設計特殊：品牌欄位被註解排除在外
- 與REWF93形成完整的試飲分析體系 