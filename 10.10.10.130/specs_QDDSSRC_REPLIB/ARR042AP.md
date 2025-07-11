# ARR042AP 報表規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARR042AP |
| 檔案類型 | 報表格式檔 (PRTF) |
| 檔案描述 | 帳齡分析表 |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 程式名稱 | ARR042A |
| 作業系統 | AS/400 |
| 參考檔案 | RERF |

## 2. 報表結構

| 項目 | 規格 |
|------|------|
| 報表類型 | 明細報表 |
| 列印方向 | 直式 |
| 紙張設定 | 標準報表紙 |
| 參考檔案 | RERF |
| 記錄格式 | 4個 (PH1, PD1, PD2, PE1) |

## 3. 報表布局

### 報表標題 (PH1)
```
                              帳齡分析表
                    
日期範圍: [起始日期] - [結束日期]              日期: [列印日期]    頁數: [頁碼]
客戶範圍: [起始客戶] - [結束客戶]              時間: [列印時間]    <ARR042A>

================================================================================
客戶代碼  客戶名稱        未到期      1-30天     31-60天    61-90天    90天以上    合計
================================================================================
```

### 明細內容 (PD1)
```
[客戶代碼] [客戶名稱]    [未到期金額] [1-30天]  [31-60天]  [61-90天]  [90天以上]  [合計]
```

### 小計記錄 (PD2)
```
                小計：   [未到期金額] [1-30天]  [31-60天]  [61-90天]  [90天以上]  [小計]
```

### 報表結尾 (PE1)
```
================================================================================
總計：                   [未到期金額] [1-30天]  [31-60天]  [61-90天]  [90天以上]  [總合計]
================================================================================
        ***報表結束***
```

## 4. 報表欄位規格

### 標題區欄位

| 欄位名稱 | 位置 | 長度 | 型態 | 說明 |
|----------|------|------|------|------|
| 報表標題 | 30 | - | A | "帳齡分析表" |
| 日期範圍起 | 13 | 6,0 | Y | 分析期間起始日期 |
| 日期範圍迄 | 24 | 6,0 | Y | 分析期間結束日期 |
| 客戶範圍起 | 13 | R | R | 客戶代碼起始值 |
| 客戶範圍迄 | 24 | R | R | 客戶代碼結束值 |
| $EGMDY | 59 | 6,0 | Y | 列印日期 |
| PAGNBR | 76 | - | - | 頁碼 |
| TIME | 59 | - | - | 列印時間 |

## 5. 明細資料欄位規格

### 明細記錄 (PD1)

| 欄位名稱 | 位置 | 長度 | 型態 | 說明 |
|----------|------|------|------|------|
| MC02 | 1 | R | R | 客戶代碼 |
| ME03 | 11 | R | R | 客戶名稱 |
| AMT0 | 32 | R | R | 未到期金額 |
| AMT1 | 45 | R | R | 1-30天帳款金額 |
| AMT2 | 56 | R | R | 31-60天帳款金額 |
| AMT3 | 67 | R | R | 61-90天帳款金額 |
| AMT4 | 78 | R | R | 90天以上帳款金額 |
| AMTTOT | 89 | R | R | 該客戶總帳款金額 |

**註**: 所有明細欄位均參考RERF檔案定義

## 6. 報表標題內容

### 主標題
- **報表名稱**: "帳齡分析表"
- **位置**: 居中顯示
- **字體**: 標準字體

### 子標題
- **日期範圍**: 顯示分析的日期範圍
- **客戶範圍**: 顯示分析的客戶範圍

### 系統資訊
- **列印日期**: 報表產生日期
- **列印時間**: 報表產生時間
- **頁碼**: 自動編號
- **程式識別**: <ARR042A>

## 7. 報表欄位說明

### 帳齡分類說明
- **未到期**: 尚未到期的應收帳款
- **1-30天**: 逾期1-30天的應收帳款
- **31-60天**: 逾期31-60天的應收帳款
- **61-90天**: 逾期61-90天的應收帳款
- **90天以上**: 逾期90天以上的應收帳款
- **合計**: 該客戶所有帳齡的總計金額

### 資料來源
- 所有欄位資料來源於RERF參考檔案
- 日期欄位使用系統日期格式 EDTCDE(Y)
- 時間欄位使用系統時間格式
- 金額欄位使用 EDTCDE(1) 千分位格式

### 統計層級
- **明細層級**: 每個客戶的帳齡分析
- **小計層級**: 按特定條件分組的小計
- **總計層級**: 所有客戶的帳齡總計

## 8. 使用說明

### 報表產生流程
1. 執行ARR042A程式
2. 設定分析條件範圍
   - 客戶代碼範圍
   - 分析日期範圍
3. 系統計算各帳齡區間金額
4. 產生帳齡分析報表

### 分析功能
- **風險評估**: 根據帳齡分布評估收款風險
- **客戶分析**: 個別客戶的應收帳款狀況
- **整體分析**: 全體客戶的帳齡分布狀況

### 管理用途
- **收款策略**: 制定不同帳齡的收款策略
- **風險控制**: 識別高風險客戶
- **財務分析**: 應收帳款品質分析
- **決策支援**: 提供信用政策決策依據

### 報表特色
- **多層級統計**: 提供明細、小計、總計
- **完整分類**: 五個帳齡區間完整分析
- **即時計算**: 依據最新資料即時計算
- **格式標準**: 符合財務報表標準格式

### 注意事項
- 帳齡計算以報表產生日為基準
- 金額統計包含所有幣別的應收帳款
- 建議定期產生以追蹤帳款品質變化
- 可作為內部管理及外部稽核的重要報表

### 相關程式
- **主程式**: ARR042A
- **系統**: 應收帳款系統
- **功能**: 帳齡分析表產生與列印 