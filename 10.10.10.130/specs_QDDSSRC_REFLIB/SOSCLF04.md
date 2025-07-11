# SOSCLF04 檔案規格書

## 1. 基本資料
- 檔名: SOSCLF04
- 類型: LF (Logical File)
- 說明: 銷售訂單主檔 key=sc39+sc02
- 主鍵: SC39+SC02
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考實體檔: SOSCPF
- 索引約束: 二層複合索引

## 2. 檔案功能說明
此邏輯檔案為銷售訂單主檔確認者簡化排序檔，提供以下功能：
- 提供以確認者+程式編號為主鍵的排序檢視
- 支援確認者導向的訂單查詢
- 記錄確認者相關的訂單資料簡化檢視
- 支援確認者工作負荷的快速查詢
- 提供程式編號的直接排序檢視
- 支援訂單管理的確認者基本查詢
- 記錄確認者訂單的基礎資料
- 支援訂單處理的確認者檢視
- 提供簡化的確認者訂單檢視
- 記錄確認者系統的基本檔案

## 3. 系統檔案清單
- 主要邏輯檔: SOSCLF04 (銷售訂單主檔邏輯檔04)
- 基礎實體檔: SOSCPF (銷售訂單主檔)
- 排序方式: SC39+SC02

## 4. 紀錄格式
邏輯檔案記錄格式SC0，依SC39+SC02二層複合主鍵排序，提供確認者導向的基本訂單檢視。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| SC39 | 確認者 | 1 | REF | 參考欄位 | 主鍵1，確認者 |
| SC02 | 程式編號出站 | 待計算 | REF | 參考欄位 | 主鍵2，程式編號出站 |
| SC01 | 程式記號 | 待計算 | REF | 參考欄位 | 程式記號 |
| SC03 | 狀態 | 待計算 | REF | 參考欄位 | 狀態記號 |
| SC04 | 客戶代號 | 待計算 | REF | 參考欄位 | 客戶代號 |
| SC05 | 聯絡代號 | 待計算 | REF | 參考欄位 | 聯絡人代號 |
| SC06 | 客戶程式編號出站 | 待計算 | REF | 參考欄位 | 客戶程式編號 |
| SC07 | 程式日期 | 待計算 | REF | 參考欄位 | 程式執行日期 |
| SC08 | 已排定送貨日期 | 待計算 | REF | 參考欄位 | 預定送貨日期 |
| SC13 | 程式狀態 | 待計算 | REF | 參考欄位 | 程式狀態 |
| SCXX | 異動日期 | 待計算 | REF | 參考欄位 | 異動日期 |
| SCYY | 異動時間 | 待計算 | REF | 參考欄位 | 異動時間 |
| SCZZ | 異動者 | 待計算 | REF | 參考欄位 | 異動人員 |

## 6. 主鍵欄位
- 主鍵: SC39+SC02
  - SC39: 確認者
  - SC02: 程式編號出站
- 約束類型: 二層複合主鍵

## 7. 索引資料
- 主要索引: SC39+SC02 (依確認者+程式編號)
- 索引類型: 邏輯檔案索引
- 排序特性: 
  - 第一層: 確認者 (SC39)
  - 第二層: 程式編號出站 (SC02)

## 8. 備註
- 此邏輯檔案用於確認者導向的簡化訂單管理
- 記錄SC0為邏輯檔案記錄格式名稱
- 無額外的OMIT或SELECT條件，提供完整的訂單資料
- 以確認者為主要檢索鍵
- 支援確認者工作負荷的快速查詢
- 提供簡化的二層索引結構
- 用於確認者相關的基礎查詢
- 支援確認者管理的基本檢視
- 記錄確認者訂單的完整資料
- 提供確認者管理的標準檢視
- 支援確認者政策的訂單實施
- 用於確認者管理的查詢與分析
- 提供確認者分析的基礎資料
- 支援確認者管理的標準作業
- 記錄確認者訂單的完整資訊
- 用於確認者決策的支援作業
- 提供確認者管理的資料平台
- 支援確認者策略的執行與分析
- 記錄確認者訂單的標準設定
- 用於確認者管理的統一作業
- 提供確認者維護的標準化作業
- 支援企業級的確認者訂單管理
- 記錄確認者工作的完整軌跡 