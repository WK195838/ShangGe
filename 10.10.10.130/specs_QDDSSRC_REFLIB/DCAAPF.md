# DCAAPF 檔案規格書

## 1. 基本資料
- 檔名: DCAAPF
- 類型: PF (Physical File)
- 說明: 捷盟客戶與DC對應檔
- 主鍵: AA01
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: RERF
- 索引約束: UNIQUE

## 2. 檔案功能說明
此實體檔案為捷盟客戶與DC對應檔，提供以下功能：
- 記錄捷盟客戶與DC對應的資料
- 儲存捷盟客戶與DC對應的設定資訊
- 支援捷盟客戶與DC對應的完整生命週期管理
- 提供捷盟客戶與DC對應的詳細分析
- 記錄捷盟客戶與DC對應的各項組成
- 支援捷盟客戶與DC對應管理作業
- 提供捷盟客戶與DC對應資料的主要儲存結構
- 記錄捷盟客戶與DC對應的內容
- 支援捷盟客戶與DC對應的查詢與報表作業
- 支援捷盟客戶與DC對應分析與管理作業

## 3. 系統檔案清單
- 主要實體檔: DCAAPF (捷盟客戶與DC對應檔)
- 相關檔案: 
  - DC#APF (捷盟發票控制檔)
  - DCABPF (DC名稱對照檔)
  - DCDAPF (捷盟發票驗收單號對照檔)
  - DCDBPF (捷盟發票轉出一次檔)
  - DC01PF (捷盟發票下載檔)
  - DC02PF (捷盟發票轉出檔)
- 參考檔: RERF

## 4. 紀錄格式
實體檔案記錄格式，包含完整的捷盟客戶與DC對應資料欄位，記錄捷盟客戶與DC對應分析資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| AA01 | 客戶編號 | 1-9 | 9A | 文字 | 客戶編號 |
| AA02 | DC編號 | 10-12 | 3A | 文字 | DC編號 |
| AA03 | 客戶代號 | 13-17 | 5A | 文字 | 客戶代號 |
| AA04 | 通路代號 | 18-21 | 4A | 文字 | 通路代號 |
| AAXX | 異動日期 | 22-29 | 8S0 | 數值 | 異動日期，YYYYMMDD格式，參考#AXX |
| AAYY | 異動時間 | 30-35 | 6S0 | 數值 | 異動時間，HHMMSS格式，參考#AYY |
| AAZZ | 異動者 | 36-45 | 10A | 文字 | 異動者代號，參考#AZZ |

## 6. 主鍵欄位
- 主鍵: AA01
  - AA01: 客戶編號
- 約束類型: UNIQUE約束

## 7. 索引資料
- 主要索引: AA01 (依客戶編號)
- 索引類型: UNIQUE索引
- 排序特性: 
  - 第一層: 客戶編號 (AA01)

## 8. 備註
- 此實體檔案為捷盟客戶與DC對應檔的主要儲存結構
- 用於管理捷盟客戶與DC對應分析
- 支援捷盟客戶與DC對應的完整資訊管理
- 記錄捷盟客戶與DC對應的計算資訊
- 支援捷盟客戶與DC對應管理作業
- 記錄捷盟客戶與DC對應的內容與分析
- 支援捷盟客戶與DC對應的查詢、報表與統計分析
- 提供捷盟客戶與DC對應的完整管理功能
- AA01 客戶編號用於客戶識別
- AA02 DC編號用於DC識別
- AA03 客戶代號用於客戶代號管理
- AA04 通路代號用於通路識別
- AAXX 異動日期參考RERF系統參考檔的#AXX欄位
- AAYY 異動時間參考RERF系統參考檔的#AYY欄位
- AAZZ 異動者參考RERF系統參考檔的#AZZ欄位
- 支援捷盟客戶與DC對應的追蹤與管理
- 提供捷盟客戶與DC對應的詳細分析基礎
- 用於捷盟客戶與DC對應的分析與控制
- 支援捷盟客戶與DC對應報表的產生與分析
- 與 DC系列 形成相關的捷盟客戶管理系列
- 提供捷盟客戶與DC對應的完整軌跡記錄
- 支援捷盟客戶與DC對應作業的稽核與管理
- 記錄捷盟客戶與DC的對應資訊
- 用於捷盟客戶與DC對應管理與決策支援
- 支援多維度捷盟客戶與DC對應管理的需求
- 提供捷盟客戶與DC對應層級的分析功能
- UNIQUE約束確保客戶編號的唯一性
- 異動日期時間採用標準格式，便於追蹤
- 提供完整的捷盟客戶與DC對應設定與追蹤機制
- 按客戶編號進行細分的捷盟客戶與DC對應管理
- 支援捷盟客戶與DC對應的規劃與執行追蹤
- 提供捷盟客戶與DC對應的決策支援功能
- 與其他DC系列檔案形成完整的捷盟客戶管理體系
- 支援捷盟客戶與DC對應的分類管理
- 提供捷盟客戶與DC對應的標準化說明
- 支援捷盟客戶與DC對應的維護與更新
- 記錄捷盟客戶與DC對應的基本資料
- 用於捷盟客戶與DC對應的查詢與檢索
- 支援捷盟客戶與DC對應的報表與分析
- 提供捷盟客戶與DC對應的完整管理功能
- 參考RERF系統參考檔，確保資料一致性
- 與DCABPF DC名稱對照檔形成關聯
- 支援捷盟客戶與DC對應的完整生命週期管理
- 提供捷盟客戶與DC對應的標準化管理機制
- 作為捷盟客戶與DC對應的主檔，提供基礎資料支援
- 支援捷盟客戶與DC對應的快速查詢與檢索
- 提供捷盟客戶與DC對應的統一標準與規範
- 建立客戶與DC之間的對應關係
- 支援通路代號的管理與追蹤 