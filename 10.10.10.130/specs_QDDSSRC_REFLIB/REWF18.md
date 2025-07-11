# REWF18 檔案規格書

## 1. 基本資料
- **檔案名稱**: REWF18
- **檔案型態**: 實體檔案 (PF)
- **檔案說明**: 客戶基本資料檔 (MTMDPF)
- **參考檔案**: RERF

## 2. 檔案功能說明
REWF18為客戶基本資料檔(MTMDPF)，用於記錄客戶的基本資訊，包含客戶名稱、送貨名稱、客戶類別、地區、通路、業務等關鍵資料。檔案設計採用UNIQUE屬性確保記錄唯一性，主鍵為客戶名稱+送貨名稱。此檔案為客戶管理系統的核心檔案，提供完整的客戶資料維護功能。

## 3. 系統檔案清單
```
檔案名稱: REWF18 (MTMDPF)
記錄格式: MD0
記錄長度: 包含7個欄位
屬性: UNIQUE
```

## 4. 紀錄格式
### Record Format: MD0

## 5. 欄位規格表

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|---------|----------|------|------|------|------|----------|
| ME01 | 客戶名稱 | - | - | 字元 | REF | 客戶名稱 |
| ME02 | 送貨名稱 | - | - | 字元 | REF | 送貨對象名稱 |
| ME04 | 客戶類別 | - | - | 字元 | REF | 客戶分類代碼 |
| ME07 | 地區 | - | - | 字元 | REF | 客戶所屬地區 |
| MD07 | 通路 | - | - | 字元 | REF | 通路代碼 |
| MD08 | 業務 | - | - | 字元 | REF | 負責業務代碼 |

## 6. 主鍵欄位
- ME01 (客戶名稱)
- ME02 (送貨名稱)

## 7. 索引資料
主要索引：ME01+ME02
此索引確保客戶與送貨對象的組合唯一性，支援快速的客戶資料查詢。

## 8. 備註
- 採用UNIQUE屬性，確保客戶名稱+送貨名稱的唯一性
- 提供客戶管理系統的基礎資料維護
- 支援客戶分類管理功能
- 與地區管理、通路管理、業務管理檔密切關聯
- 為客戶關係管理(CRM)系統的核心檔案
- 支援客戶資料的完整性維護
- 提供業務分工與地區劃分的基礎資料
- 適用於客戶分析與市場區隔管理 