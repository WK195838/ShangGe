# SOR201WF 檔案規格書

## 1. 基本資料
- 檔名: SOR201WF
- 類型: PF (Physical File)
- 說明: 送貨未確認彙總表
- 主鍵: WK01+WK06
- 建立日期: (待補)
- 最後修改日期: 2024/06/17 (需求編號 1130292)
- 參考檔: RERF
- 需求編號: 1130162, 1130292
- 修改人: DEREK
- 索引約束: 實體檔案

## 2. 檔案功能說明
此實體檔案為送貨未確認彙總表，提供以下功能：
- 記錄送貨明細的未確認狀態資訊
- 提供送貨確認管理的明細追蹤
- 支援配送管理的詳細未確認追蹤
- 記錄送貨作業的完整明細資訊
- 支援送貨作業的客戶追蹤
- 提供送貨管理的明細查詢
- 支援物流管理的詳細確認追蹤
- 記錄送貨明細與確認之間的狀態
- 支援客戶服務的送貨明細查詢
- 提供配送管理的工作檔案

## 3. 系統檔案清單
- 主要實體檔: SOR201WF (送貨未確認彙總表)
- 參考檔: RERF

## 4. 紀錄格式
實體檔案記錄格式，依送貨編號與產品編號排序，記錄送貨明細的未確認狀態與相關資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| WK01 | 送貨編號 | 1 | REF(SE02) | 參考欄位 | 主鍵1，送貨編號 |
| WK02 | 客戶代號 | 待計算 | REF(SE04) | 參考欄位 | 客戶代號 |
| WK03 | 聯絡代號 | 待計算 | REF(SE05) | 參考欄位 | 聯絡人代號 |
| WK04 | 配送日期 | 待計算 | REF(SE06) | 參考欄位 | 配送日期 |
| WK05 | 出貨點代碼點 | 待計算 | REF(SE07) | 參考欄位 | 出貨地點代碼 |
| WK06 | 產品編號 | 待計算 | REF(SF03) | 參考欄位 | 主鍵2，產品編號 |
| WK07 | 產品名稱 | 待計算 | REF(MA02) | 參考欄位 | 產品完整名稱 |
| WK08 | 電話數量 | 待計算 | REF(SF04) | 參考欄位 | 電話訂購數量 (修改歷史) |
| WK09 | 配送數量 | 待計算 | REF(SF05) | 參考欄位 | 配送數量 (修改歷史) |
| WK10 | 單價金額-FOB | 待計算 | REF(SF10) | 參考欄位 | FOB單價金額 |
| WK11 | 單價金額-FHI | 待計算 | REF(SF11) | 參考欄位 | FHI單價金額 |
| WK12 | 單價金額-DUTY | 待計算 | REF(SF12) | 參考欄位 | DUTY單價金額 |

## 6. 主鍵欄位
- 主鍵: WK01+WK06
  - WK01: 送貨編號 (參考SE02)
  - WK06: 產品編號 (參考SF03)
- 約束類型: 二層複合主鍵

## 7. 索引資料
- 主要索引: WK01+WK06 (依送貨編號+產品編號)
- 索引類型: 實體檔案索引
- 排序特性: 
  - 第一層: 送貨編號 (WK01)
  - 第二層: 產品編號 (WK06)

## 8. 備註
- 此實體檔案用於送貨未確認明細管理
- 記錄WK0為實體檔案記錄格式名稱
- 需求編號: 1130162 (初版), 1130292 (修改版)
- 修改歷史 (2024/06/17 DEREK修改):
  - WK08: 原為確認電話數量(SF19) → 改為電話數量(SF04)
  - WK09: 原為確認配送數量(SF20) → 改為配送數量(SF05)
- 依送貨編號與產品編號排序，便於送貨明細確認分析
- 所有欄位皆為參考欄位格式，提高一致性
- 記錄完整的送貨明細與確認狀態
- 包含三種價格類型：FOB、FHI、DUTY
- 用於配送管理的明細追蹤作業
- 支援送貨作業的詳細確認管控
- 記錄送貨確認的明細分析
- 提供客戶服務的詳細送貨查詢資料
- 支援物流管理的詳細未確認追蹤
- 用於送貨管理的明細統計
- 提供配送流程的詳細暫存資料
- 支援送貨作業的明細標準管理
- 記錄送貨確認的詳細軌跡
- 用於配送決策的明細支援作業
- 提供送貨管理的詳細資料平台
- 支援物流策略的詳細執行與分析
- 記錄送貨確認的詳細標準設定
- 用於配送管理的明細統一作業
- 提供送貨維護的詳細標準化作業
- 支援企業級的送貨明細確認管理
- 記錄送貨未確認明細的完整軌跡 