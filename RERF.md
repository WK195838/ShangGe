# RERF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | RERF |
| 檔案類型 | 參考檔案 (Reference File) |
| 檔案用途 | 系統欄位定義參考檔 |
| 紀錄格式 | RERFR |
| 資料庫 | REFLIB |
| 檔案特性 | 系統參考檔案 |
| 建立日期 | - |
| 最後修改日期 | - |

## 2. 檔案功能說明

RERF 是整個系統最重要的參考檔案，為所有系統檔案提供欄位定義和屬性參考：

1. **核心功能**：定義系統中所有檔案的欄位屬性、長度、型態等基本規格
2. **統一標準**：確保整個系統中相同性質的欄位具有一致的定義和格式
3. **參考基礎**：所有實體檔案和邏輯檔案都使用 REF(RERF) 來參考欄位定義
4. **系統架構**：支援多個子系統的欄位定義，包括：
   - 進貨系統 (POP___)
   - 銷貨系統 (SOS___)
   - 庫存系統 (IMI___)
   - 應收帳款系統 (ARA___)
   - 主檔系統 (MTM___)
   - 參數設定系統 (PA#___)
5. **資料完整性**：透過統一的欄位定義確保資料的一致性和完整性

## 3. 系統檔案清單

### 主要參考檔案
| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| RERF | 參考檔案 | 系統欄位定義參考檔（本檔案） |

### 參考的子系統檔案群組

#### 3.1 進貨系統檔案 (POP___)
- POPAPF：進貨產品基本資料檔
- POPBPF：進貨主檔
- POPCPF：進貨明細檔
- POPDPF：產品進貨供應商主檔
- POPEPF：產品進貨供應商明細檔
- POPFPF：產品進貨組合主檔
- POPGPF：產品進貨組合明細檔
- POPHPF：年度進貨供應商主檔
- POPIPF：年度進貨供應商明細檔
- POPJPF：進貨單據明細檔
- POPNPF：產品供應商價格明細檔

#### 3.2 銷貨系統檔案 (SOS___)
- SOSAPF：客戶產品售價明細檔
- SOSBPF：客戶產品基本明細檔
- SOSCPF：銷貨客戶主檔
- SOSDPF：銷貨客戶明細檔
- SOSEPF：出貨主檔
- SOSFPF：出貨明細檔
- SOSGPF：銷貨退回主檔
- SOSHPF：銷貨退回明細檔
- SOSIPF：發票主檔
- SOSJPF：發票明細檔

#### 3.3 庫存系統檔案 (IMI___)
- IMIAPF：產品庫存主檔
- IMIBPF：產品成本調整明細檔
- IMICPF：倉庫產品盤點主檔
- IMIDPF：倉庫產品盤點明細檔
- IMIEPF：產品報廢主檔
- IMIFPF：產品報廢明細檔

#### 3.4 應收帳款系統檔案 (ARA___)
- ARAAPF：發票號碼設定資料檔
- ARABPF：銀行帳號資料檔
- ARACPF：收款主檔
- ARADPF：收款沖帳明細檔
- ARAEPF：票據兌現主檔
- ARAFPF：銷貨折讓主檔

#### 3.5 主檔系統檔案 (MTM___)
- MTMAPF：產品基本資料檔
- MTMBPF：供應商基本資料檔
- MTMCPF：幣別基本資料檔
- MTMDPF：客戶基本資料檔

#### 3.6 參數設定系統檔案 (PA#___)
- PA#1PF：規則代碼檔
- PA#2PF：單據代碼檔
- PA#APF：規則規則檔
- PA#BPF：公司檔
- PA#CPF：銷貨客戶類別設定檔
- PA#DPF：銷貨地區資料檔

## 4. 紀錄格式

### 記錄格式：RERFR
- **記錄類型**：參考記錄
- **用途**：提供系統所有欄位的定義規格
- **特性**：包含完整的欄位屬性定義

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

### 5.1 系統參數檔案欄位定義 (#___)

#### 規則代碼檔 (#1__)
| 欄位代號 | 欄位名稱 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|
| #101 | 規則類別 | 8 | A | - | 規則類別代號 |
| #102 | 規則說明 | 22 | A | O | 規則說明 |
| #103 | 規則名稱說明一 | 32 | A | O | 規則名稱說明一 |
| #104 | 規則名稱說明列印 | 32 | A | O | 規則名稱說明列印 |
| #105 | 規則長度 | 3 | P | - | 規則長度 |
| #106 | 規則長度小數 | 3 | P | - | 規則長度小數 |
| #107 | 可自動與否 | 1 | A | - | 可自動與否 (Y/N) |

#### 單據代碼檔 (#2__)
| 欄位代號 | 欄位名稱 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|
| #201 | 單據類別 | 1 | A | - | 單據類別 (S-銷貨客戶, D-出貨檔, I-進貨主) |
| #202 | 單據 | 2 | A | - | 單據代號 |
| #203 | 單據說明 | 22 | A | O | 單據說明 |
| #204 | 檢查狀態 | 1 | A | - | 檢查狀態 (Y/N) |
| #205 | 庫存單據 | 2 | A | - | 庫存單據代號 |

#### 公司檔 (#B__)
| 欄位代號 | 欄位名稱 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|
| #B01 | 公司代號 | 2 | A | - | 公司代號 |
| #B02 | 公司名稱 | 34 | A | O | 公司名稱 |
| #B03 | 公司說明 | 16 | A | O | 公司說明 |
| #B04 | 公司地址一 | 34 | A | O | 公司地址一 |
| #B05 | 公司地址二 | 34 | A | O | 公司地址二 |
| #B06 | 公司類型 | 1 | A | - | 公司類型 (A-直營店, W-試飲店) |
| #B07 | 負責人 | 12 | A | O | 負責人 |
| #B08 | 公司電話一 | 15 | A | - | 公司電話一 |
| #B09 | 公司電話二 | 15 | A | - | 公司電話二 |
| #B10 | 傳真號 | 15 | A | - | 傳真號 |
| #B11 | 郵遞區號 | 5 | A | - | 郵遞區號 |
| #B12 | 統一編號 | 8 | A | - | 統一編號 |
| #B13 | 營業編號 | 9 | A | - | 營業編號 |
| #B14 | 客戶代號 | 5 | A | - | 客戶代號 |
| #B15 | 單據代號 | 4 | A | - | 單據代號 |
| #B16 | 月結年月 | 6 | S | B2MODA | 月結年月 |
| #B17 | 發票公司 | - | A | R | 發票公司，參考 #B01 |

#### 共用欄位 (#A__)
| 欄位代號 | 欄位名稱 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|
| #AXX | 異動日期 | 8 | S | B2MODA | 異動日期 |
| #AYY | 異動時間 | 6 | S | - | 異動時間 |
| #AZZ | 異動者 | 10 | A | - | 異動者 |

### 5.2 產品主檔欄位定義 (MA__)

#### 產品基本資料檔
| 欄位代號 | 欄位名稱 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|
| MA01 | 產品代號 | 9 | A | - | 產品代號 |
| MA02 | 條碼資料 | 34 | A | O | 條碼資料 |
| MA03 | 產品說明 | 18 | A | O | 產品說明 |
| MA04 | 包裝單位數量 | 30 | A | - | 包裝單位數量 |
| MA05 | 包裝單位數量 | 30 | A | - | 包裝單位數量 |
| MA06 | 包裝說明 | 15 | A | - | 包裝說明 |
| MA07 | 產品性質 | 1 | A | - | 產品性質 |
| MA08 | 產品項次 | 2 | A | - | 產品項次 |
| MA09 | 產品容量 | 2 | A | - | 產品容量 |
| MA10 | 產品產地 | 2 | A | - | 產品產地 |
| MA11 | 產品類別 | 2 | A | - | 產品類別 |
| MA12 | 主要供應商 | 5 | A | - | 主要供應商 |
| MA13 | 庫存週期 | 6 | A | O | 庫存週期 |
| MA14 | 進貨週期 | 6 | A | O | 進貨週期 |
| MA15 | 重量比 | 4 | S | - | 重量比 |
| MA16 | 保存期限 | 3 | P | - | 保存期限 |
| MA17 | 包裝類別 | 9 | A | - | 包裝類別 |
| MA18 | 出貨時間 | 3 | P | - | 出貨時間 |
| MA19 | 業務人員 | 6 | A | - | 業務人員 |
| MA20 | 產地 | 14 | A | O | 產地 |
| MA26 | F.O.B.-TOTAL | 11 | P | - | F.O.B.-TOTAL |
| MA27 | FHI-TOTAL | 11 | P | - | FHI-TOTAL |
| MA28 | DUTY-TOTAL | 11 | P | - | DUTY-TOTAL |
| MA29 | 保留庫存量 | 6 | S | - | 保留庫存量 |
| MA30 | 可用庫存量 | 6 | S | - | 可用庫存量 |
| MA31 | F.O.B.-UNIT | 9 | S | - | F.O.B.-UNIT |
| MA32 | FHI-UNIT | 9 | S | - | FHI-UNIT |
| MA33 | DUTY-UNIT | 9 | S | - | DUTY-UNIT |
| MA34 | 標準成本 | 9 | S | - | 標準成本 |
| MA35 | 最小進貨數量 | 6 | S | - | 最小進貨數量 |
| MA36 | 最大進貨數量 | 6 | S | - | 最大進貨數量 |
| MA37 | 保留變安全量 | 6 | S | - | 保留變安全量 |
| MA38 | 可用變安全量 | 6 | S | - | 可用變安全量 |
| MA39 | 銷貨最後日期 | 8 | S | B2CHKA,R | 銷貨最後日期，參考 #AXX |
| MA53 | 建立日期 | 8 | S | B2CHKA,R | 建立日期，參考 #AXX |
| MA54 | 禮盒標示 | 1 | A | - | 禮盒標示 (Y/ ) |
| MA55 | 可否手動 | 1 | A | - | 可否手動 (Y/ ) |
| MA56 | 可否手動 | 1 | A | - | 可否手動 (Y/ ) |
| MA57 | 自動組合 | 1 | A | - | 自動組合 (Y/ ) |
| MA58 | 使用狀況 | 1 | A | - | 使用狀況 (A-ACTIVE, I-INACTIVE) |
| MA59 | 所屬店 | 1 | A | - | 所屬店 (D-總店, B-分店, Z-寄店) |
| MAXX | 異動日期 | 8 | S | B2CHKA,R | 異動日期，參考 #AXX |
| MAYY | 異動時間 | - | A | R | 異動時間，參考 #AYY |
| MAZZ | 異動者 | - | A | R | 異動者，參考 #AZZ |

### 5.3 供應商主檔欄位定義 (MB__)

#### 供應商基本資料檔
| 欄位代號 | 欄位名稱 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|
| MB01 | 供應商代號 | - | A | R | 供應商代號，參考 MA12 |
| MB02 | 供應商名稱 | 42 | A | O | 供應商名稱 |
| MB03 | 供應商說明 | 18 | A | O | 供應商說明 |
| MB04 | 統一編號 | 14 | A | O | 統一編號 |
| MB05 | 郵遞區號 | 7 | A | - | 郵遞區號 |
| MB06 | 供應商地址一 | 32 | A | O | 供應商地址一 |
| MB07 | 供應商地址二 | 32 | A | O | 供應商地址二 |
| MB08 | 供應商地址三 | 32 | A | O | 供應商地址三 |
| MB09 | 供應商地址四 | 32 | A | O | 供應商地址四 |
| MB10 | 供應商地址五 | 32 | A | O | 供應商地址五 |
| MB11 | 聯絡人 | 22 | A | O | 聯絡人 |
| MB12 | 會計人 | 22 | A | O | 會計人 |
| MB13 | 電話號碼 | 15 | A | - | 電話號碼 |
| MB14 | 電話號碼 | 15 | A | - | 電話號碼 |
| MB15 | 傳真號碼 | 15 | A | - | 傳真號碼 |
| MB16 | 電子信箱 | 15 | A | - | 電子信箱 |
| MB17 | 幣別 | 3 | A | - | 幣別 |
| MB18 | 付款方式 | 2 | A | - | 付款方式 |
| MB19 | 業務人員 | - | A | R | 業務人員，參考 MA19 |
| MB23 | 建立日期 | 8 | S | B2CHKA,R | 建立日期，參考 #AXX |
| MB24 | 供應商類型 | 1 | A | - | 供應商類型 (0-外商, 1-國內, 2-國外) |
| MB25 | 應付帳款期間 | 10 | S | - | 應付帳款期間 |
| MB26 | 應付帳款期間 | 10 | S | - | 應付帳款期間 |
| MBXX | 異動日期 | 8 | S | B2CHKA,R | 異動日期，參考 #AXX |
| MBYY | 異動時間 | - | A | R | 異動時間，參考 #AYY |
| MBZZ | 異動者 | - | A | R | 異動者，參考 #AZZ |

## 6. 主鍵欄位

RERF 為參考檔案，不具有實體記錄，因此無主鍵欄位。所有欄位定義均為其他檔案提供參考規格。

## 7. 索引資料

RERF 為參考檔案，不具有索引結構。

## 8. 備註

### 8.1 檔案特性
- **系統核心**：RERF 是整個系統的核心參考檔案，所有檔案的欄位定義都依賴此檔案
- **統一標準**：確保系統中相同性質的欄位具有一致的定義和格式
- **維護重要性**：任何對 RERF 的修改都會影響整個系統，需要特別謹慎

### 8.2 欄位屬性說明
- **R**：參考其他欄位定義
- **O**：輸出專用欄位
- **K**：主鍵欄位
- **B2CHKA**：日期檢查
- **B2MODA**：年月檢查

### 8.3 系統關聯
- 所有實體檔案都使用 REF(RERF) 來定義欄位屬性
- 邏輯檔案透過實體檔案間接使用 RERF 的定義
- 螢幕檔案使用 REFFLD 來參考 RERF 中的欄位定義

### 8.4 維護注意事項
1. 修改 RERF 前必須評估對整個系統的影響
2. 欄位長度的變更可能需要重新編譯相關程式
3. 新增欄位定義時需要考慮與既有欄位的一致性
4. 刪除欄位定義前必須確認沒有其他檔案在使用

### 8.5 版本控制
- RERF 的任何變更都應該有完整的變更記錄
- 建議在測試環境充分測試後才套用到正式環境
- 重要變更應該有備份和回復計畫