# REWF99 檔案規格書

## 1. 基本資料
- **檔案代號**: REWF99
- **檔案名稱**: 異動明細表（B）－禮盒組拆
- **檔案類型**: PF (實體檔案)
- **記錄格式**: WF990
- **系統**: AS/400 RPG
- **功能**: 管理禮盒產品組拆異動的明細記錄（B類型）

## 2. 檔案功能說明
異動明細表（B）是禮盒產品組拆管理系統的第二類異動檔案，記錄禮盒產品組拆作業的詳細異動資料，包含倉庫別、單據號、異動日期、來源倉庫別、產品編號等重要資訊，並包含M001程式修改記錄，提供更完整的禮盒異動管理功能。

## 3. 系統檔案清單
- 主檔案：REWF99 (異動明細表B)
- 參考檔案：RERF (參考主檔)
- 關聯檔案：IMIRLF (庫存異動檔)、IMISLF99 (庫存檔)

## 4. 紀錄格式
### 記錄格式：WF990

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 參考欄位 | 說明 |
|----------|----------|------|------|------|------|----------|------|
| WF9901 | 倉庫別 | - | R | 文字 | 顯示 | IR02 | 倉庫識別代號 |
| WF991A | 單據 | - | R | 文字 | 顯示 | IR05 | 異動單據號碼 |
| WF9902 | 異動日期 | 8 | 8 | 數字 | M001 | IR04 | 異動作業日期 |
| WF9908 | 來源倉庫別 | - | R | 文字 | 顯示 | IR11 | 來源倉庫代號 |
| WF9903 | 產品編號 | - | R | 文字 | 顯示 | IR06 | 產品識別編號 |
| WF9904 | 價位 | - | R | 文字 | 顯示 | @IS02 | 產品價位等級 |
| WF9905 | 容量 | - | R | 文字 | 顯示 | @IS03 | 產品容量規格 |
| WF9906 | 產品名稱 | - | R | 文字 | 顯示 | IR03 | 產品名稱說明 |
| WF9907 | 進出 | 4 | 4 | 文字 | 顯示 | - | 進出庫標記 |
| WF9909 | 確認碼 | 8 | 8 | 數字 | M001 | @IS04 | 確認狀態碼 |
| WF9910 | 數量 | 6 | 6 | 數字 | 顯示 | - | 異動數量 |
| WF9911 | FOB- | 11 | 11 | 數字 | 小數2位 | - | FOB成本金額 |
| WF9912 | FHI- | 11 | 11 | 數字 | 小數2位 | - | FHI成本金額 |
| WF9913 | DUTY | 11 | 11 | 數字 | 小數2位 | - | 關稅成本金額 |

## 6. 主鍵欄位
- **複合主鍵**:
  - WF9901 (倉庫別)
  - WF991A (單據)
  - WF9902 (異動日期)
  - WF9908 (來源倉庫別)
  - WF9903 (產品編號)
  - WF9904 (價位)
  - WF9905 (容量)
  - WF9906 (產品名稱)

## 7. 索引資料
- 主要索引：依倉庫別、單據、異動日期、來源倉庫別、產品編號、價位、容量、產品名稱排序
- 檔案結構：八層複合主鍵索引
- 特殊功能：禮盒組拆異動追蹤（B類型）

## 8. 備註
- 此檔案為異動明細系列的B類型檔案
- 包含M001程式修改記錄，確保資料維護的正確性
- 與REWF98形成完整的禮盒組拆異動管理體系
- 主鍵中來源倉庫別位置調整，提供不同的查詢優化
- 支援多種成本計算（FOB、FHI、DUTY）
- 與庫存管理系統緊密整合，確保異動資料準確性 