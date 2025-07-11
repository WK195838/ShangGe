# MTMBLF02 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | MTMBLF02 |
| 檔案描述 | 費用廠商資料檔 (邏輯檔) |
| 檔案類型 | LF (Logical File) |
| 記錄格式 | MB0 |
| 主鍵 | MB01 (供應商代號) |
| 實體檔案 | MTMBPF |
| 檔案屬性 | 邏輯檢視，條件篩選 |

## 2. 檔案功能說明

MTMBLF02 為 MTMBPF 供應商基本資料檔的費用廠商專用邏輯檔案，提供：
- 費用類供應商的專門檢視
- 費用廠商管理與維護
- 費用支付對象查詢
- 費用管理支援

## 3. 系統檔案清單

| 檔案代號 | 檔案名稱 | 說明 |
|----------|----------|------|
| MTMBLF02 | 費用廠商資料邏輯檔 | 主檔 |
| MTMBPF | 供應商基本資料實體檔 | 實體檔案 |
| MTMBLF | 供應商基本資料邏輯檔 | 基本邏輯檔 |
| RERF | 參考檔案 | 欄位定義參考 |

## 4. 紀錄格式

### 記錄格式：MB0 (繼承自 MTMBPF，條件篩選)

## 5. 欄位規格

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| MB01 | 供應商代號 | 1-8 | 8 | A | R | 主鍵，供應商識別碼 |
| MB02 | 供應商名稱 | 9-26 | 18 | A | R | 供應商中文名稱 |
| MB03 | 英文名稱 | 27-44 | 18 | A | R | 供應商英文名稱 |
| MB04 | 供應商簡稱 | 45-54 | 10 | A | R | 供應商簡稱 |
| MB05 | 統一編號 | 55-62 | 8 | A | R | 統一編號 |
| MB06 | 供應商分類 | 63-67 | 5 | A | R | 供應商分類代號 |
| MB07 | 付款條件 | 68-72 | 5 | A | R | 付款條件代號 |
| MB08 | 供應商狀態 | 73 | 1 | A | R | 'A'-有效，'I'-停用 |
| MB09 | 負責人 | 74-83 | 10 | A | R | 供應商負責人 |
| MB10 | 聯絡電話 | 84-98 | 15 | A | R | 供應商電話 |
| MB11 | 傳真號碼 | 99-113 | 15 | A | R | 傳真號碼 |
| MB12 | 供應商地址 | 114-153 | 40 | A | R | 供應商地址 |
| MB13 | 採購員 | 154-158 | 5 | A | R | 負責採購員代號 |
| MB14 | 費用性質 | 159 | 1 | A | R | 'E'-費用類，篩選條件 |
| 其他欄位 | 繼承MTMBPF | | | | | 參考MTMBPF規格 |

## 6. 主鍵欄位

| 鍵值序號 | 欄位代號 | 欄位名稱 | 排序 |
|----------|----------|----------|------|
| 1 | MB01 | 供應商代號 | 升序 |

## 7. 索引資料

### 主要索引
- **索引名稱**：主鍵索引
- **索引欄位**：MB01
- **索引類型**：PRIMARY
- **說明**：供應商代號升序排序

### 輔助索引
1. **分類索引**：MB06 (供應商分類)
2. **狀態索引**：MB08 (供應商狀態)
3. **採購員索引**：MB13 (採購員代號)
4. **付款條件索引**：MB07 (付款條件)

### 邏輯檢視特性
- **基底檔案**：MTMBPF
- **檢視條件**：MB14 = 'E' (費用類供應商)
- **檢視類型**：條件篩選檢視
- **排序方式**：MB01 升序

## 8. 備註

### 設計考量
1. 此檔案為 MTMBPF 的條件邏輯檢視檔案
2. 專門處理費用類供應商資料
3. 提供費用管理專用功能

### 費用廠商類型
- **服務類費用**：清潔、保全、維修等服務
- **租賃類費用**：設備租賃、場地租賃等
- **專業服務費**：顧問、法律、會計等專業服務
- **行政費用**：辦公用品、水電、電信等

### 參考關聯
- **實體檔案**：MTMBPF (MB14 = 'E')
- **採購員檔案**：MTMCPF (MB13 = MC01)
- **付款條件**：PA#付款條件檔 (MB07 = 條件代號)
- **費用代碼**：NPNGPF (費用歸類)

### 業務規則
1. 僅顯示費用類供應商 (MB14 = 'E')
2. 供應商代號必須唯一
3. 採購員需對應有效員工
4. 停用供應商不影響歷史費用記錄

### 資料完整性
1. 資料內容完全依賴 MTMBPF 實體檔案
2. 僅顯示 MB14 = 'E' 的記錄
3. MB13 需對應 MTMCPF 中的有效員工
4. MB07 需對應有效的付款條件

### 使用注意事項
1. 此為邏輯檔案，不可直接寫入資料
2. 所有異動需透過 MTMBPF 實體檔案進行
3. 新增費用廠商時需設定 MB14 = 'E'
4. 適用於費用支付與管理流程 