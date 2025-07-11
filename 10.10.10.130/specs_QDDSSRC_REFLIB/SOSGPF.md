# SOSGPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | SOSGPF |
| 檔案類型 | PF (物理檔案) |
| 檔案說明 | 銷貨退回主檔 |
| 排序鍵值 | SG02 |
| 記錄長度 | - |
| 記錄格式 | SG0 |
| 參考檔案 | RERF |
| 檔案屬性 | UNIQUE |

## 2. 檔案功能說明

本檔案儲存銷貨退回的主要資料，包含退回單基本資訊、客戶資料、退回原因、處理狀態等詳細資訊。是銷貨退回處理系統的核心檔案。

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| SOSGPF | PF | 銷貨退回主檔物理檔 |

## 4. 記錄格式

### 記錄格式：SG0

## 5. 欄位說明

| 欄位代號 | 名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|------|------|------|------|------|------|
| SG01 | 客戶編號 | - | - | R | COLHDG | 客戶編號 |
| SG02 | 退貨單號 | - | - | R | COLHDG | 退貨單號格式：客戶-編號-月年編碼-流水號 |
| SG03 | 編號 | - | - | R | COLHDG | 編號 |
| SG04 | 路線代碼 | - | - | R | COLHDG | 路線代碼 |
| SG05 | 銷貨代碼 | - | - | R | COLHDG | 銷貨代碼 |
| SG06 | 退貨日期 | - | 8 | DATE | COLHDG | 退貨日期 |
| SG07 | 退回地點代號 | - | - | R | COLHDG | 退回地點代號 |
| SG08 | 退貨原因 | - | - | R | COLHDG | 退貨原因 |
| SG09 | 原送貨單號 | - | - | R | COLHDG | 原送貨單號 |
| SG10 | 退回折扣 | - | - | R | COLHDG | 退回折扣 |
| SG11 | 業務員 | - | - | R | COLHDG | 業務員 |
| SG12 | 銷貨編號 | - | - | R | COLHDG | 銷貨編號 |
| SG13 | 退回放置郵遞區號 | - | - | R | COLHDG | 退回放置郵遞區號 |
| SG14 | 櫃台 | - | - | R | COLHDG | 櫃台 |
| SG15 | 地區 | - | - | R | COLHDG | 地區 |
| SG16 | 簽收編號 | - | - | R | COLHDG | 簽收編號 |
| SG17 | 退未出貨單號 | - | - | R | COLHDG | 若有退回退貨時的原未出貨單號 |
| SG18 | 原發票單號 | - | - | R | COLHDG | 若有退回退貨時的原發票單號 |
| SG19 | 退回總金額FOB | - | - | R | COLHDG | 退回總金額FOB |
| SG20 | 退回總金額FHI | - | - | R | COLHDG | 退回總金額FHI |
| SG21 | 退回總金額DUTY | - | - | R | COLHDG | 退回總金額DUTY |
| SG22 | 實際退回總金額FOB | - | - | R | COLHDG | 實際退回總金額FOB |
| SG23 | 實際退回總金額FHI | - | - | R | COLHDG | 實際退回總金額FHI |
| SG24 | 實際退回總金額DUTY | - | - | R | COLHDG | 實際退回總金額DUTY |
| SG25 | 實際退回幣別金額 | - | - | R | COLHDG | 實際退回幣別金額 |
| SG26 | 建檔日期 | - | 8 | DATE | COLHDG | 建檔日期（確認日期） |
| SG27 | 異動代號 | - | 12 | CHAR | COLHDG | 異動代號 |
| SG28 | 字串一 | - | 12 | CHAR | COLHDG | 字串一 |
| SG29 | 字串二 | - | 12 | CHAR | COLHDG | 字串二 |
| SG30 | 字串三 | - | 12 | CHAR | COLHDG | 字串三 |
| SG31 | 數字一 | - | 11.2 | NUM | COLHDG | 數字一 |
| SG32 | 數字二 | - | 11.2 | NUM | COLHDG | 數字二 |
| SG33 | 數字三 | - | 11.2 | NUM | COLHDG | 數字三 |
| SG34 | 備註一 | - | 30 | CHAR | COLHDG | 備註一 |
| SG35 | 備註二 | - | 30 | CHAR | COLHDG | 備註二 |
| SG36 | 備註三 | - | 30 | CHAR | COLHDG | 備註三 |
| SG37 | 旗標一 | - | 1 | CHAR | COLHDG | 旗標一 |
| SG38 | 旗標二 | - | 1 | CHAR | COLHDG | 旗標二 |
| SG39 | 旗標三 | - | 1 | CHAR | COLHDG | 旗標三 |
| SGXX | 異動日期 | - | 8 | DATE | COLHDG | 異動日期 |
| SGYY | 異動時間 | - | - | R | COLHDG | 異動時間 |
| SGZZ | 異動者 | - | - | R | COLHDG | 異動者 |

## 6. 主鍵欄位

### 主鍵
- SG02（退貨單號）

## 7. 索引資料

| 索引名稱 | 索引欄位 | 排序方式 | 說明 |
|----------|----------|----------|------|
| 主索引 | SG02 | 遞增 | 按退貨單號排序 |

## 8. 備註

1. 本檔案為銷貨退回主檔的核心檔案
2. 退貨單號格式：客戶-編號-月年編碼-流水號
3. 具有 UNIQUE 屬性，確保記錄唯一性
4. 櫃台狀態說明：
   - '*'：待確認
   - ' '：已退回未確認
   - 'V'：已確認
   - 'A'：已實際
   - 'N'：無需實際（實際處理時排除）
5. 包含 FOB、FHI、DUTY 等多種成本金額計算方式
6. 支援多種備註和旗標欄位以記錄特殊處理情況
7. SG37 旗標一說明：N-取消未出庫且等候
8. 修改記錄：
   - 00A 1010614 DEREK 新增旗標：取消未出庫且等候(N) 