# DCABPF 檔案規格書

## 1. 基本資料
- 檔名: DCABPF
- 類型: PF (Physical File)
- 說明: DC名稱對照檔
- 主鍵: AB01
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: (無)
- 索引約束: (無)

## 2. 檔案功能說明
此實體檔案為DC名稱對照檔，提供以下功能：
- 記錄DC名稱對照的資料
- 儲存DC名稱對照的設定資訊
- 支援DC名稱對照的完整生命週期管理
- 提供DC名稱對照的詳細分析
- 記錄DC名稱對照的各項組成
- 支援DC名稱對照管理作業
- 提供DC名稱對照資料的主要儲存結構
- 記錄DC名稱對照的內容
- 支援DC名稱對照的查詢與報表作業
- 支援DC名稱對照分析與管理作業

## 3. 系統檔案清單
- 主要實體檔: DCABPF (DC名稱對照檔)
- 相關檔案: 
  - DC#APF (捷盟發票控制檔)
  - DCAAPF (捷盟客戶與DC對應檔)
  - DCDAPF (捷盟發票驗收單號對照檔)
  - DCDBPF (捷盟發票轉出一次檔)
  - DC01PF (捷盟發票下載檔)
  - DC02PF (捷盟發票轉出檔)
- 參考檔: (無)

## 4. 紀錄格式
實體檔案記錄格式，包含完整的DC名稱對照資料欄位，記錄DC名稱對照分析資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| AB01 | DC代號 | 1-3 | 3A | 文字 | DC代號 |
| AB02 | DC名稱 | 4-21 | 18A | 文字 | DC名稱，ONLY屬性 |

## 6. 主鍵欄位
- 主鍵: AB01
  - AB01: DC代號
- 約束類型: (無)

## 7. 索引資料
- 主要索引: AB01 (依DC代號)
- 索引類型: 一般索引
- 排序特性: 
  - 第一層: DC代號 (AB01)

## 8. 備註
- 此實體檔案為DC名稱對照檔的主要儲存結構
- 用於管理DC名稱對照分析
- 支援DC名稱對照的完整資訊管理
- 記錄DC名稱對照的計算資訊
- 支援DC名稱對照管理作業
- 記錄DC名稱對照的內容與分析
- 支援DC名稱對照的查詢、報表與統計分析
- 提供DC名稱對照的完整管理功能
- AB01 DC代號用於DC識別
- AB02 DC名稱提供詳細的DC名稱描述，具ONLY屬性
- 支援DC名稱對照的追蹤與管理
- 提供DC名稱對照的詳細分析基礎
- 用於DC名稱對照的分析與控制
- 支援DC名稱對照報表的產生與分析
- 與 DC系列 形成相關的DC管理系列
- 提供DC名稱對照的完整軌跡記錄
- 支援DC名稱對照作業的稽核與管理
- 記錄DC的名稱對照資訊
- 用於DC名稱對照管理與決策支援
- 支援多維度DC名稱對照管理的需求
- 提供DC名稱對照層級的分析功能
- 提供完整的DC名稱對照設定與追蹤機制
- 按DC代號進行細分的DC名稱對照管理
- 支援DC名稱對照的規劃與執行追蹤
- 提供DC名稱對照的決策支援功能
- 與其他DC系列檔案形成完整的DC管理體系
- 支援DC名稱對照的分類管理
- 提供DC名稱對照的標準化說明
- 支援DC名稱對照的維護與更新
- 記錄DC名稱對照的基本資料
- 用於DC名稱對照的查詢與檢索
- 支援DC名稱對照的報表與分析
- 提供DC名稱對照的完整管理功能
- 與DCAAPF捷盟客戶與DC對應檔形成關聯
- 支援DC名稱對照的完整生命週期管理
- 提供DC名稱對照的標準化管理機制
- 簡化的檔案結構，專注於DC名稱對照的基本管理
- 作為DC名稱對照的主檔，提供基礎資料支援
- 支援DC名稱對照的快速查詢與檢索
- 提供DC名稱對照的統一標準與規範
- ONLY屬性欄位提供特殊的顯示控制
- 支援DC名稱的標準化管理
- 無異動追蹤欄位，為簡化的基本資料檔
- 提供DC代號與名稱的對照功能 