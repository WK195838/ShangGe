# ARAEPF 檔案規格書

## 1. 基本資料
- 檔名: ARAEPF
- 類型: PF (Physical File)
- 說明: 票據兌現主檔
- 主鍵: AE01+AE02+AE03
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: RERF

## 2. 檔案功能說明
此實體檔案為票據兌現主檔，提供以下功能：
- 記錄票據兌現的基本資料
- 儲存票據的預計入帳日期與實際兌現金額
- 支援票據兌現的完整生命週期管理
- 提供票據與銀行帳戶的對應關係
- 記錄票據兌現的處理狀態
- 支援應收帳款管理系統的票據兌現處理
- 提供票據兌現資料的主要儲存結構
- 記錄票據的到期與兌現資訊
- 支援票據兌現的查詢與報表作業

## 3. 系統檔案清單
- 主要實體檔: ARAEPF (票據兌現主檔)
- 相關邏輯檔: 
  - ARAELF1 (票據兌現主檔邏輯檔)
- 參考檔: RERF (系統參考檔)
- 相關檔案: ARABPF (銀行帳號資料檔)

## 4. 紀錄格式
實體檔案記錄格式，包含完整的票據兌現資料欄位，支援票據兌現管理的各項需求。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| AE01 | 公司別 | 1-2 | 2A | 文字 | 參考 #B01，必填，公司代碼 |
| AE02 | 預計入帳日期 | 3-10 | 8S0 | 日期 | 參考 #AXX，必填，預計入帳日期 |
| AE03 | 帳戶號碼 | 11-24 | 14A | 文字 | 參考 AB02，必填，銀行帳戶號碼 |
| AE04 | 兌現金額 | 25-33 | 9P0 | 數值 | 兌現金額，以分為單位 |
| AEXX | 異動日期 | 34-41 | 8S0 | 日期 | 參考 #AXX，最後異動日期 |
| AEYY | 異動時間 | 42-47 | 6S0 | 時間 | 參考 #AYY，最後異動時間 |
| AEZZ | 異動者 | 48-57 | 10A | 文字 | 參考 #AZZ，最後異動人員 |

## 6. 主鍵欄位
- 主鍵: AE01 + AE02 + AE03
  - AE01: 公司別
  - AE02: 預計入帳日期
  - AE03: 帳戶號碼

## 7. 索引資料
- 主要索引: AE01 + AE02 + AE03 (依公司別、預計入帳日期、帳戶號碼)
- 索引類型: 非唯一索引
- 排序特性: 
  - 第一層: 公司別 (AE01)
  - 第二層: 預計入帳日期 (AE02)
  - 第三層: 帳戶號碼 (AE03)

## 8. 備註
- 此實體檔案為票據兌現的主要儲存結構
- 支援票據兌現的完整資訊管理
- 記錄票據的預計入帳日期與實際兌現金額
- 與銀行帳號資料檔(ARABPF)密切相關，透過帳戶號碼關聯
- 支援應收帳款管理系統的票據兌現處理
- 提供邏輯檔案的基礎資料來源
- 記錄票據的到期與兌現資訊
- 支援票據兌現的查詢、報表與統計分析
- 包含完整的異動追蹤欄位(日期、時間、異動者)
- 用於票據到期提醒與兌現管理作業
- 支援票據兌現狀態的追蹤與管理
- 提供票據與銀行帳戶的對應關係管理 