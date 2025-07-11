# SOSCLF06 檔案規格書

## 1. 基本資料
- 檔名: SOSCLF06
- 類型: LF (Logical File)
- 說明: 試飲訂單主檔 key=sc02
- 主鍵: SC01+SC39+SC02 (複合主鍵)
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考實體檔: SOSCPF
- 索引約束: 三層複合索引

## 2. 檔案功能說明
此邏輯檔案為試飲訂單主檔複合條件檔，提供以下功能：
- 提供以程式記號+確認者+程式編號為主鍵的試飲訂單檢視
- 支援試飲訂單的複合條件查詢
- 記錄特定狀態的試飲訂單資料過濾
- 支援試飲管理的多重條件處理
- 提供試飲訂單的複雜檢視
- 支援試飲流程的多狀態管理
- 記錄試飲訂單的詳細篩選資料
- 支援試飲業務的精確查詢
- 提供試飲訂單的條件檢視
- 記錄試飲系統的進階檔案

## 3. 系統檔案清單
- 主要邏輯檔: SOSCLF06 (試飲訂單主檔邏輯檔06)
- 基礎實體檔: SOSCPF (銷售訂單主檔)
- 排序方式: SC01+SC39+SC02

## 4. 紀錄格式
邏輯檔案記錄格式SC0，依SC01+SC39+SC02三層複合主鍵排序，提供多重條件篩選的試飲訂單檢視。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| SC01 | 程式記號 | 1 | REF | 參考欄位 | 主鍵1，程式記號 |
| SC39 | 確認者 | 待計算 | REF | 參考欄位 | 主鍵2，確認者 |
| SC02 | 程式編號出站 | 待計算 | REF | 參考欄位 | 主鍵3，程式編號出站 |
| SC03 | 狀態 | 待計算 | REF | 參考欄位 | 狀態記號（篩選條件） |
| SC04 | 客戶代號 | 待計算 | REF | 參考欄位 | 客戶代號 |
| SC05 | 聯絡代號 | 待計算 | REF | 參考欄位 | 聯絡人代號 |
| SC06 | 客戶程式編號出站 | 待計算 | REF | 參考欄位 | 客戶程式編號 |
| SC07 | 程式日期 | 待計算 | REF | 參考欄位 | 程式執行日期 |
| SC08 | 已排定送貨日期 | 待計算 | REF | 參考欄位 | 預定送貨日期 |
| SC13 | 程式狀態 | 待計算 | REF | 參考欄位 | 程式狀態（篩選條件） |
| SC35 | 應收記號 | 待計算 | REF | 參考欄位 | 應收記號（篩選條件） |
| SCXX | 異動日期 | 待計算 | REF | 參考欄位 | 異動日期 |
| SCYY | 異動時間 | 待計算 | REF | 參考欄位 | 異動時間 |
| SCZZ | 異動者 | 待計算 | REF | 參考欄位 | 異動人員 |

## 6. 主鍵欄位
- 主鍵: SC01+SC39+SC02
  - SC01: 程式記號
  - SC39: 確認者
  - SC02: 程式編號出站
- 約束類型: 三層複合主鍵

## 7. 索引資料
- 主要索引: SC01+SC39+SC02 (依程式記號+確認者+程式編號)
- 索引類型: 邏輯檔案索引
- 排序特性: 
  - 第一層: 程式記號 (SC01)
  - 第二層: 確認者 (SC39)
  - 第三層: 程式編號出站 (SC02)
- 過濾條件:
  - SELECT: SC03 = 'S4' (選擇狀態S4)
  - SELECT: SC13 = 'V' (選擇程式狀態V)
  - SELECT: SC35 = 'N' (選擇應收記號N)

## 8. 備註
- 此邏輯檔案專用於試飲訂單的複合條件管理
- 記錄SC0為邏輯檔案記錄格式名稱
- 檔案註解中顯示為SOSCLF05，可能為複製錯誤，實際為SOSCLF06
- 使用三重SELECT條件進行精確篩選
- SELECT條件組合：狀態S4 + 程式狀態V + 應收記號N
- 專門處理特定條件的試飲訂單資料
- 以程式記號為主要檢索鍵
- 支援確認者相關的試飲訂單查詢
- 提供複雜的三層索引結構
- 用於試飲訂單的精確查詢
- 支援試飲管理的進階檢視
- 記錄試飲訂單的完整篩選資料
- 提供試飲管理的條件檢視
- 支援試飲政策的精確實施
- 用於試飲管理的複合查詢與分析
- 提供試飲分析的條件基礎資料
- 支援試飲管理的進階作業
- 記錄試飲訂單的詳細資訊
- 用於試飲決策的精確支援作業
- 提供試飲管理的條件平台
- 支援試飲策略的精確執行與分析
- 記錄試飲訂單的條件設定
- 用於試飲管理的進階作業
- 提供試飲維護的條件化作業
- 支援企業級的精確試飲訂單管理
- 記錄試飲業務的詳細軌跡 