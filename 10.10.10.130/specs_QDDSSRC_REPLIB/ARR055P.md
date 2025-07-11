# ARR055P 報表規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | ARR055P |
| 檔案類型 | 報表格式檔 (PRTF) |
| 檔案描述 | 物流點存貨成本表 |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 應收帳款報表 |
| 程式名稱 | ARR055 |
| 作業系統 | AS/400 |
| 參考檔案 | RERF |

## 2. 報表結構

| 項目 | 規格 |
|------|------|
| 報表類型 | 成本分析報表 |
| 列印方向 | 直式 |
| 紙張設定 | 標準報表紙 |
| 參考檔案 | RERF |

## 3. 報表布局

### 報表標題
```
                            物流點存貨成本表
                    
統計日期: [統計日期]                          日期: [列印日期]    頁數: [頁碼]
物流點範圍: [起始] - [結束]                    時間: [列印時間]    <ARR055>

================================================================================
物流點    產品代碼  產品名稱    庫存量    進貨成本    加工成本    總成本
================================================================================
```

### 明細內容
```
[物流點]  [代碼]    [產品名稱]  [庫存量]  [進貨成本]  [加工成本]  [總成本]
```

### 小計記錄
```
          物流點小計：             [庫存量]  [進貨成本]  [加工成本]  [總成本]
```

### 報表結尾
```
================================================================================
總計：                           [庫存量]  [進貨成本]  [加工成本]  [總成本]
================================================================================
        ***報表結束***
```

## 4. 報表欄位規格

### 明細欄位

| 欄位名稱 | 位置 | 長度 | 型態 | 說明 |
|----------|------|------|------|------|
| 物流點 | 1 | 8 | A | 物流點代碼 |
| 產品代碼 | 11 | 10 | A | 產品識別代碼 |
| 產品名稱 | 23 | 20 | A | 產品名稱 |
| 庫存量 | 45 | 10 | N | 目前庫存數量 |
| 進貨成本 | 57 | 12 | N | 進貨成本金額 |
| 加工成本 | 71 | 12 | N | 加工成本金額 |
| 總成本 | 85 | 12 | N | 總成本金額 |

## 5. 明細資料欄位規格

### 格式化設定
- 金額欄位使用EDTCDE(1)格式
- 數量欄位使用EDTCDE(3)格式

### 欄位來源
所有欄位均參考RERF檔案定義

## 6. 報表標題內容

### 標題資訊
- **報表名稱**: 物流點存貨成本表
- **統計日期**: 存貨成本統計基準日期
- **物流點範圍**: 包含的物流點範圍

## 7. 報表欄位說明

### 基本資訊
- **物流點**: 物流據點代碼
- **產品代碼**: 產品識別代碼
- **產品名稱**: 產品名稱

### 庫存資訊
- **庫存量**: 各物流點的產品庫存數量

### 成本分析
- **進貨成本**: 產品進貨成本
- **加工成本**: 產品加工處理成本
- **總成本**: 進貨成本與加工成本總和

### 統計層級
- **明細層級**: 每個物流點各產品的成本分析
- **物流點小計**: 按物流點分組的小計
- **總計層級**: 所有物流點的總計

## 8. 使用說明

### 報表用途
- 存貨成本分析
- 物流點成本管理
- 庫存評價作業

### 管理應用
- **成本控制**: 分析各物流點成本結構
- **庫存評價**: 計算存貨總價值
- **效率分析**: 比較各物流點營運效率

### 相關程式
- **主程式**: ARR055
- **系統**: 應收帳款系統
- **功能**: 物流點存貨成本表產生與列印 