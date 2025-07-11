# ARR044P 報表規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARR044P |
| 檔案類型 | 報表格式檔 (PRTF) |
| 檔案描述 | 票據收入明細表 |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 程式名稱 | ARR044 |
| 作業系統 | AS/400 |
| 參考檔案 | RERF |

## 2. 報表結構

| 項目 | 規格 |
|------|------|
| 報表類型 | 明細報表 |
| 列印方向 | 直式 |
| 紙張設定 | 標準報表紙 |
| 參考檔案 | RERF |

## 3. 報表布局

### 報表標題
```
                              票據收入明細表
                    
票據期間: [起始日期] - [結束日期]              日期: [列印日期]    頁數: [頁碼]
客戶範圍: [起始客戶] - [結束客戶]              時間: [列印時間]    <ARR044>

================================================================================
票據日期  客戶代碼  客戶名稱      票據號碼      票據種類  到期日     金額     狀態
================================================================================
```

### 明細內容
```
MM/DD/YY  [代碼]    [客戶名稱]    [票據號碼]    [種類]    MM/DD/YY   [金額]   [狀態]
```

### 報表結尾
```
================================================================================
總計：                                                              [總金額]
================================================================================
```

## 4. 報表欄位規格

### 明細欄位

| 欄位名稱 | 位置 | 長度 | 型態 | 說明 |
|----------|------|------|------|------|
| 票據日期 | 1 | 6 | Y | 票據開立日期 |
| 客戶代碼 | 11 | 6 | A | 客戶識別代碼 |
| 客戶名稱 | 19 | 15 | A | 客戶名稱 |
| 票據號碼 | 36 | 12 | A | 票據編號 |
| 票據種類 | 50 | 8 | A | 票據類型 |
| 到期日 | 60 | 6 | Y | 票據到期日期 |
| 金額 | 68 | 12 | N | 票據金額 |
| 狀態 | 82 | 6 | A | 票據兌現狀態 |

## 5. 明細資料欄位規格

### 格式化設定
- 日期欄位使用EDTCDE(Y)格式
- 金額欄位使用EDTCDE(1)格式

### 欄位來源
所有欄位均參考RERF檔案定義

## 6. 報表標題內容

### 標題資訊
- **報表名稱**: 票據收入明細表
- **票據期間**: 統計的票據日期範圍
- **客戶範圍**: 包含的客戶範圍

## 7. 報表欄位說明

### 票據資訊
- **票據日期**: 票據開立日期
- **客戶代碼**: 票據開立客戶
- **客戶名稱**: 客戶名稱
- **票據號碼**: 票據識別編號
- **票據種類**: 票據類型分類
- **到期日**: 票據到期日期
- **金額**: 票據面額
- **狀態**: 兌現狀態（未兌現/已兌現）

## 8. 使用說明

### 報表用途
- 票據收入統計分析
- 票據兌現狀況追蹤
- 資金流量管理

### 管理應用
- **風險管控**: 監控未兌現票據
- **現金流預測**: 預估到期收款
- **客戶分析**: 客戶票據往來狀況

### 相關程式
- **主程式**: ARR044
- **系統**: 應收帳款系統
- **功能**: 票據收入明細表產生與列印 