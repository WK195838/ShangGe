# BRBPPF 檔案規格書

## 1. 基本資料
- 檔名: BRBPPF
- 類型: PF (Physical File)
- 說明: 目標檔－Key Account (K/A客戶)
- 主鍵: BP01+BP02+BP04+BP05+BP10+BP06
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: (無)
- 索引約束: UNIQUE

## 2. 檔案功能說明
此實體檔案為目標檔－Key Account，提供以下功能：
- 記錄Key Account客戶的目標資料
- 儲存Key Account目標的設定資訊
- 支援Key Account目標的完整生命週期管理
- 提供Key Account目標的詳細分析
- 記錄Key Account目標的各項組成
- 支援Key Account目標管理作業
- 提供Key Account目標資料的主要儲存結構
- 記錄Key Account目標的內容
- 支援Key Account目標的查詢與報表作業
- 支援Key Account目標分析與管理作業

## 3. 系統檔案清單
- 主要實體檔: BRBPPF (目標檔－Key Account)
- 相關檔案: 
  - BRBAPF (目標版本主檔－依客戶)
  - BRBBPF (目標檔－依業務員)
  - BRBCPF (預算檔－依產品品牌／種類)
  - BRBDPF (預測銷售檔－依產品代號)
  - BRBEPF (產品歸類檔)
- 參考檔: (無)

## 4. 紀錄格式
實體檔案記錄格式，包含完整的Key Account目標資料欄位，記錄Key Account目標分析資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| BP01 | 通路別 | 1-2 | 2A | 文字 | 通路別代號 |
| BP02 | 目標年月 | 3-8 | 6S0 | 數值 | 目標年月，YYYYMM格式 |
| BP04 | 目標客戶代號 | 9-10 | 2A | 文字 | 目標客戶代號 |
| BP05 | 目標業務員代號 | 11-16 | 6A | 文字 | 目標業務員代號 |
| BP06 | 新舊產品區分 | 17-18 | 2A | 文字 | 新舊產品區分代號 |
| BP07 | 目標銷售量 | 19-27 | 9S2 | 數值 | 目標銷售量，以分為單位 |
| BP08 | 目標金額 | 28-35 | 8S0 | 數值 | 目標金額，以分為單位 |
| BP09 | 目標毛利 | 36-43 | 8S0 | 數值 | 目標毛利，以分為單位 |
| BP10 | 品類 | 44-45 | 2A | 文字 | 品類代號 |
| BPXX | 異動日期 | 46-53 | 8S0 | 數值 | 異動日期，YYYYMMDD格式 |
| BPYY | 異動時間 | 54-59 | 6S0 | 數值 | 異動時間，HHMMSS格式 |
| BPZZ | 異動者 | 60-69 | 10A | 文字 | 異動者代號 |

## 6. 主鍵欄位
- 主鍵: BP01+BP02+BP04+BP05+BP10+BP06
  - BP01: 通路別
  - BP02: 目標年月
  - BP04: 目標客戶代號
  - BP05: 目標業務員代號
  - BP10: 品類
  - BP06: 新舊產品區分
- 約束類型: UNIQUE約束

## 7. 索引資料
- 主要索引: BP01+BP02+BP04+BP05+BP10+BP06 (依通路別+目標年月+目標客戶代號+目標業務員代號+品類+新舊產品區分)
- 索引類型: UNIQUE索引
- 排序特性: 
  - 第一層: 通路別 (BP01)
  - 第二層: 目標年月 (BP02)
  - 第三層: 目標客戶代號 (BP04)
  - 第四層: 目標業務員代號 (BP05)
  - 第五層: 品類 (BP10)
  - 第六層: 新舊產品區分 (BP06)

## 8. 備註
- 此實體檔案為目標檔－Key Account的主要儲存結構
- 用於管理Key Account客戶目標分析
- 支援Key Account目標的完整資訊管理
- 記錄Key Account目標的計算資訊
- 支援Key Account目標管理作業
- 記錄Key Account目標的內容與分析
- 支援Key Account目標的查詢、報表與統計分析
- 提供Key Account目標的完整管理功能
- BP01 通路別用於通路區分
- BP02 目標年月採用YYYYMM格式，便於時間序列分析
- BP04 目標客戶代號用於Key Account客戶識別
- BP05 目標業務員代號用於業務員管理
- BP06 新舊產品區分用於產品生命週期管理
- BP07 目標銷售量以分為單位，提高精確度
- BP08 目標金額以分為單位，提高精確度
- BP09 目標毛利以分為單位，提高精確度
- BP10 品類用於產品分類管理
- BPXX-BPZZ 異動追蹤欄位，記錄完整的異動軌跡
- 支援Key Account目標的追蹤與管理
- 提供Key Account目標的詳細分析基礎
- 用於Key Account目標的分析與控制
- 支援Key Account目標報表的產生與分析
- 與 BRB系列 形成相關的目標管理系列
- 提供Key Account目標的完整軌跡記錄
- 支援Key Account目標作業的稽核與管理
- 記錄Key Account客戶的目標資訊
- 用於Key Account目標管理與決策支援
- 支援多維度Key Account目標管理的需求
- 提供Key Account目標層級的分析功能
- UNIQUE約束確保同一組合的唯一性
- 異動日期時間採用標準格式，便於追蹤
- 提供完整的Key Account目標設定與追蹤機制
- 按Key Account客戶進行細分的目標管理
- 支援月度Key Account目標規劃與執行追蹤
- 提供Key Account目標的決策支援功能
- 與其他BRB系列檔案形成完整的目標管理體系
- 支援Key Account客戶的特殊目標管理需求
- 提供Key Account客戶的專屬目標分析
- 支援通路別的Key Account目標管理
- 記錄Key Account客戶在不同品類的目標表現
- 支援新舊產品在Key Account客戶的目標管理
- 提供Key Account業務員的目標管理功能
- 支援Key Account目標的多維度分析與報表
- 6層主鍵設計支援複雜的Key Account目標管理需求 