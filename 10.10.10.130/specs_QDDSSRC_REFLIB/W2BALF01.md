# W2BALF01 檔案規格書

## 1. 基本資料
- **檔案名稱**: W2BALF01
- **檔案描述**: 後台銷售主檔邏輯檔01
- **檔案類型**: 邏輯檔案 (LF)
- **實體檔案**: W2BAPF
- **記錄格式**: BA0
- **索引**: BA02 + BA01(DESCEND) + BA03
- **選擇條件**: BA05='B' OR BA05=' '
- **用途**: 提供後台銷售主檔B類及空白狀態記錄的邏輯視圖
- **相關系統**: 後台銷售管理系統

## 2. 檔案功能說明
W2BALF01邏輯檔案主要用於：
- 提供後台銷售資料的特定狀態篩選視圖
- 支援B類狀態及空白狀態記錄查詢
- 按營業點+銷售編號倒序的排序查詢
- 優化特定狀態銷售記錄的查詢效能

## 3. 系統檔案清單
### 邏輯檔案
- W2BALF01: 後台銷售主檔邏輯檔01

### 實體檔案
- W2BAPF: 後台銷售主檔 (基底檔案)

### 相關邏輯檔案
- W2BALF02: 後台銷售主檔邏輯檔02
- W2BALF03: 後台銷售主檔邏輯檔03
- W2BALF04: 後台銷售主檔邏輯檔04

## 4. 紀錄格式

### 記錄: BA0 (承襲自W2BAPF)
| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 檢核說明 |
|----------|----------|------|------|------|------|----------|
| BA01 | 銷售編號 | 1-8 | 8 | S 0 | 索引鍵2(倒序) | 銷售單編號 |
| BA02 | 營業點 | 9-13 | 5 | A | 索引鍵1 | 營業點代碼 |
| BA03 | 銷售發貨號 | 14-25 | 12 | A | 索引鍵3 | 發貨單號 |
| BA04 | 總金額 | 26-36 | 11 | S 2 | - | 銷售總金額 |
| BA05 | 狀態 | 37 | 1 | A | 選擇條件 | B-特定狀態, ' '-空白狀態 |
| BA06 | 備註 | 38-39 | 2 | A | - | 銷售備註 |
| BA07 | 數量 | 40-167 | 128 | O | - | 包裝數量 |
| BA08 | 配送日期 | 168-169 | 2 | A | - | 配送日期 |
| BA09 | 確認人員 | 170-179 | 10 | A | - | 確認人員代號 |
| BA10 | 會員碼 | 180 | 1 | A | - | 會員識別碼 |
| BA11 | VIP號-電話 | 181-195 | 15 | A | - | VIP客戶電話 |
| BA12 | VIP號-分機 | 196-200 | 5 | A | - | VIP客戶分機 |
| BAXX | 異動日期 | 201-208 | 8 | S 0 | - | 異動日期 |
| BAYY | 異動時間 | 209-214 | 6 | S 0 | - | 異動時間 |
| BAZZ | 異動人員 | 215-224 | 10 | A | - | 異動人員 |

## 5. 主鍵欄位
- **邏輯鍵組合**: BA02 + BA01(DESCEND) + BA03
- **排序**: 營業點 + 銷售編號(倒序) + 銷售發貨號

## 6. 索引資料
### 主要索引
- **索引1**: BA02 (營業點)
- **索引2**: BA01 DESCEND (銷售編號，倒序)
- **索引3**: BA03 (銷售發貨號)

### 選擇條件
- **條件1**: BA05 = 'B' (B類狀態)
- **條件2**: BA05 = ' ' (空白狀態)

### 索引結構
```
KEY: BA02 (營業點) + BA01 DESCEND (銷售編號) + BA03 (銷售發貨號)
SELECT: BA05 IN ('B', ' ')
```

## 7. 使用說明
### 查詢作業
1. 主要用於B類及空白狀態銷售記錄查詢
2. 按營業點分類查詢
3. 銷售編號採倒序排列，最新在前
4. 支援銷售發貨號精確定位

### 排序特性
1. 優先按營業點排序
2. 其次按銷售編號倒序排序(最新在前)
3. 最後按銷售發貨號排序

### 應用場景
1. B類狀態銷售查詢
2. 初始狀態銷售記錄瀏覽
3. 營業點銷售歷史分析
4. 最新銷售記錄監控

## 8. 備註
- 此邏輯檔案承襲W2BAPF的所有欄位定義
- 特定選擇條件：僅顯示BA05='B'或BA05=' '的記錄
- 適用於B類及初始狀態銷售記錄的專門查詢
- 銷售編號倒序排列，便於查詢最新銷售資料 