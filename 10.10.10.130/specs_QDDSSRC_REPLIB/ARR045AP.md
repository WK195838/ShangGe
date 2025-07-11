# ARR045AP 報表規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARR045AP |
| 檔案類型 | 報表格式檔 (PRTF) |
| 檔案描述 | 銷貨收入明細表 |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 程式名稱 | ARR045A |
| 作業系統 | AS/400 |
| 參考檔案 | RERF |
| 版本編號 | A1118 |

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
                              銷貨收入明細表
                    
銷貨期間: [起始日期] - [結束日期]              日期: [列印日期]    頁數: [頁碼]
客戶範圍: [起始客戶] - [結束客戶]              時間: [列印時間]    <ARR045A>

================================================================================
銷貨日期  發票號碼  客戶代碼  客戶名稱      產品代碼  產品名稱    數量    單價    金額
================================================================================
```

### 明細內容
```
MM/DD/YY  [發票號]  [代碼]    [客戶名稱]    [產品碼]  [產品名]   [數量]  [單價]  [金額]
```

### 小計記錄
```
                客戶小計：                                        [小計數量]     [小計金額]
```

### 報表結尾
```
================================================================================
總計：                                                           [總數量]       [總金額]
================================================================================
        ***報表結束***
```

## 4. 報表欄位規格

### 明細欄位

| 欄位名稱 | 位置 | 長度 | 型態 | 說明 |
|----------|------|------|------|------|
| 銷貨日期 | 1 | 6 | Y | 銷貨發票日期 |
| 發票號碼 | 11 | 10 | A | 發票編號 |
| 客戶代碼 | 23 | 6 | A | 客戶識別代碼 |
| 客戶名稱 | 31 | 15 | A | 客戶名稱 |
| 產品代碼 | 48 | 8 | A | 產品識別代碼 |
| 產品名稱 | 58 | 12 | A | 產品名稱 |
| 數量 | 72 | 8 | N | 銷貨數量 |
| 單價 | 82 | 10 | N | 銷貨單價 |
| 金額 | 94 | 12 | N | 銷貨金額 |

## 5. 明細資料欄位規格

### 格式化設定
- 日期欄位使用EDTCDE(Y)格式
- 金額欄位使用EDTCDE(1)格式
- 數量欄位使用EDTCDE(3)格式

### 欄位來源
所有欄位均參考RERF檔案定義

## 6. 報表標題內容

### 標題資訊
- **報表名稱**: 銷貨收入明細表
- **銷貨期間**: 統計的銷貨日期範圍
- **客戶範圍**: 包含的客戶範圍

## 7. 報表欄位說明

### 銷貨資訊
- **銷貨日期**: 發票開立日期
- **發票號碼**: 發票識別編號
- **客戶代碼**: 銷貨客戶代碼
- **客戶名稱**: 客戶名稱
- **產品代碼**: 銷貨產品代碼
- **產品名稱**: 產品名稱
- **數量**: 銷貨數量
- **單價**: 銷貨單價
- **金額**: 銷貨總金額

### 統計層級
- **明細層級**: 每筆銷貨交易明細
- **客戶小計**: 按客戶分組的小計
- **總計層級**: 所有銷貨的總計

## 8. 使用說明

### 報表用途
- 銷貨收入統計分析
- 客戶銷貨狀況追蹤
- 產品銷售績效分析

### 管理應用
- **業績分析**: 銷貨收入統計
- **客戶分析**: 客戶購買行為分析
- **產品分析**: 產品銷售狀況分析

### 相關程式
- **主程式**: ARR045A
- **系統**: 應收帳款系統
- **功能**: 銷貨收入明細表產生與列印 