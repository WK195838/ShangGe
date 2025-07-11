# S#SPPF 檔案規格書

## 1. 基本資料
- 檔名: S#SPPF
- 類型: PF (Physical File)
- 說明: 程式基本資料檔 A1062
- 主鍵: SP01
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: S#RF
- 索引約束: UNIQUE

## 2. 檔案功能說明
此實體檔案為程式基本資料檔，提供以下功能：
- 記錄系統中所有程式的基本資料
- 儲存程式的詳細資訊與分類
- 支援程式管理與維護作業
- 提供程式類型的分類管理
- 記錄程式的路徑與檔案資訊
- 支援程式版本的追蹤管理
- 提供程式權限管理的基礎資料
- 記錄程式的完整生命週期
- 支援程式清單的查詢與報表
- 提供系統程式的集中管理

## 3. 系統檔案清單
- 主要實體檔: S#SPPF (程式基本資料檔)
- 相關檔案: 
  - S#SDPF (安全管制資料檔)
  - S#SDLF (安全管制邏輯檔)
- 參考檔: S#RF

## 4. 紀錄格式
實體檔案記錄格式，包含完整的程式基本資料欄位，記錄程式的詳細資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| SP01 | 程式編號 | 1-10 | 10A | 參考 | 程式編號主鍵 |
| SP02 | 程式名稱 | 11-42 | 32O | 參考 | 程式名稱 |
| SP03 | 程式類型 | 43-43 | 1A | 參考 | M=主選單, P=主程式, S=副程式 |
| SP04 | 程式路徑 | 44-53 | 10O | 參考 | 程式路徑 |
| SP05 | 程式檔名 | 54-63 | 10O | 參考 | 程式檔名 |
| SP06 | 程式版本 | 64-73 | 10O | 參考 | 程式版本 |

## 6. 主鍵欄位
- 主鍵: SP01
  - SP01: 程式編號
- 約束類型: UNIQUE主鍵約束

## 7. 索引資料
- 主要索引: SP01 (依程式編號)
- 索引類型: UNIQUE主鍵索引
- 排序特性: 
  - 第一層: 程式編號 (SP01)
- 唯一性約束: 防止重複的程式編號

## 8. 備註
- 此實體檔案為程式基本資料檔的主要儲存結構
- 參考檔案S#RF提供相關欄位定義
- A1062為系統版本標識
- UNIQUE約束確保程式編號的唯一性
- 記錄SP0為實體檔案記錄格式名稱
- SP01程式編號為系統中所有程式的唯一識別
- SP02程式名稱提供程式的中文描述
- SP03程式類型分類：M=主選單, P=主程式, S=副程式
- SP04-SP06記錄程式的檔案位置與版本資訊
- 支援程式管理與維護作業
- 提供程式權限管理的基礎資料
- 用於安全管制系統的程式識別
- 支援程式清單的查詢與報表
- 記錄系統中所有程式的完整資訊
- 提供程式分類與管理功能
- 支援程式版本的追蹤管理
- 用於系統維護的程式清單管理
- 提供程式開發與部署的支援
- 支援程式生命週期的管理
- 記錄程式的詳細技術資訊
- 提供程式架構的整體檢視
- 支援系統文件的自動化產生
- 用於程式權限分配的基礎資料
- 提供程式管理的完整解決方案 