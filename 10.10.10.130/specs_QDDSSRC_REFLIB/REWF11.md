# REWF11 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF11
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 客戶對帳單檔 format
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF11為客戶對帳單檔，用於記錄客戶對帳相關資訊，包含送貨日期、各種單據編號(訂單、送貨、發票、帳款)、應收金額、客戶資訊等。檔案設計支援完整的客戶對帳作業，並經過B2CHKA修訂以優化日期欄位格式。

## 3. 系統檔案清單
```
檔案名稱: REWF11
記錄格式: WF110
記錄長度: 包含9個欄位
修訂版本: B2CHKA
```

## 4. 紀錄格式
### Record Format: WF110

## 5. 欄位規格表

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| WF1101 | 送貨日期 | - | 8 | 數值 | REFFLD(#AXX), 8 00 | 送貨日期YYYYMMDD |
| WF1102 | 訂單編號 | - | - | 字元 | REFFLD(SC02) | 參考訂單主檔 |
| WF1103 | 送貨順序 | - | - | 字元 | REFFLD(SE02) | 參考送貨主檔 |
| WF1104 | 發票編號 | - | - | 字元 | REFFLD(SI02) | 參考發票主檔 |
| WF1105 | 應收金額 | - | - | 數值 | REFFLD(AD08) | 應收帳款金額 |
| WF1106 | 帳款編號 | - | - | 字元 | REFFLD(AC06) | 帳款管理編號 |
| WF1107 | 預計收款日期 | - | 8 | 數值 | REFFLD(#AXX), 8 00 | 預計收款日期YYYYMMDD |
| WF1108 | 客戶名稱 | - | - | 字元 | REFFLD(SI08) | 客戶名稱 |
| WF1109 | 送貨名稱 | - | - | 字元 | REFFLD(SI09) | 送貨對象名稱 |

## 6. 主鍵欄位
- WF1108 (客戶名稱)
- WF1109 (送貨名稱)
- WF1106 (帳款編號)
- WF1101 (送貨日期)
- WF1102 (訂單編號)
- WF1103 (送貨順序)
- WF1104 (發票編號)

## 7. 索引資料
主要索引：WF1108+WF1109+WF1106+WF1101+WF1102+WF1103+WF1104
此複合索引支援客戶對帳的完整查詢需求。

## 8. 備註
- B2CHKA修訂：調整日期欄位格式為8位數字
- 日期欄位採用YYYYMMDD格式，提升年度識別能力
- 整合訂單、送貨、發票、帳款等多系統資訊
- 支援完整的客戶對帳作業流程
- 與多個主檔系統密切關聯
- 提供應收帳款管理功能
- 適用於財務對帳與收款管理 