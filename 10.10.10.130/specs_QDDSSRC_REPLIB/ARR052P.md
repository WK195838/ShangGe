# ARR052P 報表規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARR052P |
| 檔案類型 | 報表格式檔 (PRTF) |
| 檔案描述 | 應收帳款管理表 |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 程式名稱 | ARR052 |
| 作業系統 | AS/400 |
| 參考檔案 | RERF |

## 2. 報表結構

| 項目 | 規格 |
|------|------|
| 報表類型 | 管理報表 |
| 列印方向 | 直式 |
| 紙張設定 | 標準報表紙 |
| 參考檔案 | RERF |

## 3. 報表布局

### 報表標題
```
                            應收帳款管理表
                    
統計日期: [統計日期]                          日期: [列印日期]    頁數: [頁碼]
客戶範圍: [起始客戶] - [結束客戶]              時間: [列印時間]    <ARR052>

================================================================================
客戶代碼  客戶名稱      未收款     30天內     30-60天    60-90天    90天以上
================================================================================
```

### 明細內容
```
[代碼]    [客戶名稱]    [未收款]   [30天內]   [30-60天]  [60-90天]  [90天以上]
```

### 小計記錄
```
              小計：     [小計]     [小計]     [小計]     [小計]     [小計]
```

### 報表結尾
```
================================================================================
總計：               [總金額]   [30天內]   [30-60天]  [60-90天]  [90天以上]
================================================================================
        ***報表結束***
```

## 4. 報表欄位規格

### 明細欄位

| 欄位名稱 | 位置 | 長度 | 型態 | 說明 |
|----------|------|------|------|------|
| 客戶代碼 | 1 | 8 | A | 客戶識別代碼 |
| 客戶名稱 | 11 | 20 | A | 客戶名稱 |
| 未收款 | 33 | 12 | N | 總未收款金額 |
| 30天內 | 47 | 12 | N | 30天內應收 |
| 30-60天 | 61 | 12 | N | 30-60天應收 |
| 60-90天 | 75 | 12 | N | 60-90天應收 |
| 90天以上 | 89 | 12 | N | 90天以上應收 |

## 5. 明細資料欄位規格

### 格式化設定
- 金額欄位使用EDTCDE(1)格式

### 欄位來源
所有欄位均參考RERF檔案定義

## 6. 報表標題內容

### 標題資訊
- **報表名稱**: 應收帳款管理表
- **統計日期**: 應收帳款統計基準日期
- **客戶範圍**: 包含的客戶範圍

## 7. 報表欄位說明

### 客戶基本資訊
- **客戶代碼**: 客戶識別代碼
- **客戶名稱**: 客戶名稱

### 帳齡分析
- **未收款**: 客戶總未收款金額
- **30天內**: 30天內到期的應收款
- **30-60天**: 30-60天到期的應收款
- **60-90天**: 60-90天到期的應收款
- **90天以上**: 90天以上的逾期應收款

### 統計層級
- **明細層級**: 每位客戶的帳齡分析
- **總計層級**: 所有客戶的總計

## 8. 使用說明

### 報表用途
- 應收帳款帳齡分析
- 逾期帳款管理
- 催收作業依據

### 管理應用
- **風險評估**: 評估客戶信用風險
- **催收管理**: 優先處理逾期帳款
- **現金流預測**: 預估收款時程

### 相關程式
- **主程式**: ARR052
- **系統**: 應收帳款系統
- **功能**: 應收帳款管理表產生與列印 