# BRBCPF 檔案規格書

## 1. 基本資料
- 檔名: BRBCPF
- 類型: PF (Physical File)
- 說明: 預算檔－依產品品牌／種類
- 主鍵: BC01+BC02+BC03+BC04+BC05+BC06
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: (無)
- 索引約束: UNIQUE

## 2. 檔案功能說明
此實體檔案為預算檔－依產品品牌／種類，提供以下功能：
- 記錄依產品品牌／種類的預算資料
- 儲存預算的設定資訊
- 支援預算的完整生命週期管理
- 提供預算的詳細分析
- 記錄預算的各項組成
- 支援預算管理作業
- 提供預算資料的主要儲存結構
- 記錄預算的內容
- 支援預算的查詢與報表作業
- 支援預算分析與管理作業

## 3. 系統檔案清單
- 主要實體檔: BRBCPF (預算檔－依產品品牌／種類)
- 相關檔案: 
  - BRBAPF (目標版本主檔－依客戶)
  - BRBBPF (目標檔－依業務員)
  - BRBDPF (預測銷售檔－依產品代號)
  - BRBPPF (目標檔－Key Account)
- 參考檔: (無)

## 4. 紀錄格式
實體檔案記錄格式，包含完整的預算資料欄位，記錄產品品牌／種類預算分析資訊。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| BC01 | 通路別 | 1-2 | 2A | 文字 | 通路別代號 |
| BC02 | 預算年月 | 3-6 | 4S0 | 數值 | 預算年月，YYYY格式 |
| BC03 | 預算區域 | 7-8 | 2A | 文字 | 預算區域代號 |
| BC04 | 預算類型 | 9-9 | 1A | 文字 | 預算類型，1=ON通路，0=OFF通路 |
| BC05 | 預算產品業別 | 10-11 | 2A | 文字 | 預算產品業別代號 |
| BC06 | 預算產品種類 | 12-13 | 2A | 文字 | 預算產品種類代號 |
| BC07 | 預算數字 | 14-26 | 13S2 | 數值 | 預算數字，以分為單位 |
| BCXX | 異動日期 | 27-34 | 8S0 | 數值 | 異動日期，YYYYMMDD格式 |
| BCYY | 異動時間 | 35-40 | 6S0 | 數值 | 異動時間，HHMMSS格式 |
| BCZZ | 異動者 | 41-50 | 10A | 文字 | 異動者代號 |

## 6. 主鍵欄位
- 主鍵: BC01+BC02+BC03+BC04+BC05+BC06
  - BC01: 通路別
  - BC02: 預算年月
  - BC03: 預算區域
  - BC04: 預算類型
  - BC05: 預算產品業別
  - BC06: 預算產品種類
- 約束類型: UNIQUE約束

## 7. 索引資料
- 主要索引: BC01+BC02+BC03+BC04+BC05+BC06 (依通路別+預算年月+區域+類型+產品業別+產品種類)
- 索引類型: UNIQUE索引
- 排序特性: 
  - 第一層: 通路別 (BC01)
  - 第二層: 預算年月 (BC02)
  - 第三層: 預算區域 (BC03)
  - 第四層: 預算類型 (BC04)
  - 第五層: 預算產品業別 (BC05)
  - 第六層: 預算產品種類 (BC06)

## 8. 備註
- 此實體檔案為預算檔－依產品品牌／種類的主要儲存結構
- 用於管理依產品品牌／種類的預算分析
- 支援預算的完整資訊管理
- 記錄預算的計算資訊
- 支援預算管理作業
- 記錄預算的內容與分析
- 支援預算的查詢、報表與統計分析
- 提供預算的完整管理功能
- BC01 通路別用於通路區分
- BC02 預算年月採用YYYY格式，便於年度預算管理
- BC03 預算區域用於區域預算管理
- BC04 預算類型區分ON通路(1)和OFF通路(0)
- BC05 預算產品業別用於產品業別分類
- BC06 預算產品種類用於產品種類分類
- BC07 預算數字以分為單位，提高精確度
- BCXX-BCZZ 異動追蹤欄位，記錄完整的異動軌跡
- 支援預算的追蹤與管理
- 提供預算的詳細分析基礎
- 用於預算的分析與控制
- 支援預算報表的產生與分析
- 與 BRB系列 形成相關的預算目標管理系列
- 提供預算的完整軌跡記錄
- 支援預算作業的稽核與管理
- 記錄產品在不同通路和區域的預算資訊
- 用於預算管理與決策支援
- 支援多維度預算管理的需求
- 提供產品品牌／種類層級的預算分析功能
- 支援通路別和區域別的預算管理與分析作業
- UNIQUE約束確保同一組合的唯一性
- 異動日期時間採用標準格式，便於追蹤
- 支援ON/OFF通路的預算管理與比較
- 提供完整的預算設定與追蹤機制
- 按產品業別和種類進行細分的預算管理
- 支援年度預算規劃與執行追蹤
- 提供產品品牌策略的預算支援功能 