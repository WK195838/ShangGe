# SOSCLF10 檔案規格書

## 1. 基本資料
- 檔名: SOSCLF10
- 類型: LF (Logical File)
- 說明: 銷售訂單主檔 key=sc02
- 主鍵: SC02
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考實體檔: SOSCPF
- 索引約束: 單一主鍵

## 2. 檔案功能說明
此邏輯檔案為銷售訂單主檔程式編號導向檔，提供以下功能：
- 提供以程式編號出站為主鍵的訂單檢視
- 支援程式編號導向的訂單查詢
- 記錄特定程式狀態和營業員的訂單資料
- 支援銷售管理的訂單處理
- 提供程式編號的排序檢視
- 支援特定業務條件的訂單檢視
- 記錄銷售相關的訂單資料
- 支援業務管理的資料查詢
- 提供銷售導向的訂單檢視
- 記錄銷售系統的專用檔案

## 3. 系統檔案清單
- 主要邏輯檔: SOSCLF10 (銷售訂單主檔邏輯檔10)
- 基礎實體檔: SOSCPF (銷售訂單主檔)
- 排序方式: SC02 (程式編號出站)

## 4. 紀錄格式
邏輯檔案記錄格式SC0，依SC02單一主鍵排序，提供特定狀態和營業員條件的程式編號導向訂單檢視。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| SC02 | 程式編號出站 | 1 | REF | 參考欄位 | 主鍵，程式編號出站 |
| SC01 | 程式記號 | 待計算 | REF | 參考欄位 | 程式記號 |
| SC03 | 狀態 | 待計算 | REF | 參考欄位 | 狀態記號 |
| SC04 | 客戶代號 | 待計算 | REF | 參考欄位 | 客戶代號 |
| SC05 | 聯絡代號 | 待計算 | REF | 參考欄位 | 聯絡人代號 |
| SC06 | 客戶程式編號出站 | 待計算 | REF | 參考欄位 | 客戶程式編號 |
| SC07 | 程式日期 | 待計算 | REF | 參考欄位 | 程式執行日期 |
| SC08 | 已排定送貨日期 | 待計算 | REF | 參考欄位 | 預定送貨日期 |
| SC11 | 業務員編號 | 待計算 | REF | 參考欄位 | 業務員編號（篩選條件） |
| SC13 | 程式狀態 | 待計算 | REF | 參考欄位 | 程式狀態（篩選條件） |
| SC39 | 確認者 | 待計算 | REF | 參考欄位 | 確認者 |
| SCXX | 異動日期 | 待計算 | REF | 參考欄位 | 異動日期 |
| SCYY | 異動時間 | 待計算 | REF | 參考欄位 | 異動時間 |
| SCZZ | 異動者 | 待計算 | REF | 參考欄位 | 異動人員 |

## 6. 主鍵欄位
- 主鍵: SC02
  - SC02: 程式編號出站
- 約束類型: 單一主鍵

## 7. 索引資料
- 主要索引: SC02 (依程式編號出站)
- 索引類型: 邏輯檔案索引
- 排序特性: 
  - 第一層: 程式編號出站 (SC02)
- 過濾條件:
  - SELECT: SC13 = '*' (選擇程式狀態*)
  - SELECT: SC11 = 'W0005' (選擇營業員W0005)

## 8. 備註
- 此邏輯檔案用於程式編號導向的銷售訂單管理
- 記錄SC0為邏輯檔案記錄格式名稱
- 使用SELECT條件篩選程式狀態為'*'（待確認狀態）
- 使用SELECT條件篩選特定營業員'W0005'
- 專門處理特定業務員的待確認訂單
- 以程式編號為主要檢索鍵
- 提供簡化的單一索引結構
- 用於銷售管理的基礎查詢
- 支援業務管理的基本檢視
- 記錄銷售訂單的完整資料
- 提供銷售管理的標準檢視
- 支援銷售政策的訂單實施
- 用於業務管理的查詢與分析
- 提供銷售分析的基礎資料
- 支援銷售管理的標準作業
- 記錄銷售訂單的完整資訊
- 用於業務決策的支援作業
- 提供銷售管理的資料平台
- 支援銷售策略的執行與分析
- 記錄銷售流程的標準設定
- 用於銷售管理的統一作業
- 提供業務維護的標準化作業
- 支援企業級的銷售訂單管理
- 記錄業務營運的完整軌跡 