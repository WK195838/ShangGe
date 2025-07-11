# BAA150D - 供應商零件對應資料維護 螢幕規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 程式名稱 | BAA150D |
| 程式類型 | DSPF (顯示檔案) |
| 系統名稱 | 採購系統 |
| 子系統 | 供應商零件對應 |
| 作者 | A1034 STEPHANIE |
| 建立日期 | 79/07/30 |
| 更新日期 |  |
| 備註 | 供應商零件對應資料維護 |

## 2. 螢幕規格

### 2.1 螢幕基本設定
- 螢幕大小：24 行 × 80 欄位
- 顯示模式：*DS3 (雙密度)
- 訊息位置：第 22 行
- 支援列印功能
- 支援訊息控制
- 支援功能鍵處理

### 2.2 螢幕特性
- 支援子檔案顯示 (SFL)
- 支援分頁瀏覽 (ROLLUP/ROLLDOWN)
- 支援覆蓋模式
- 支援多種功能鍵

## 3. 螢幕布局

### 3.1 主要畫面布局 (DSPD1)
```
<BAA150D>  公司名稱                          日期: YY/MM/DD
使用者名稱  供應商零件對應資料維護

供應商代號: XXX

零件編號  供應商代號  供應商名稱  供應商料號  單價  數量
===============================================================
[子檔案資料顯示區域]

===============================================================
選擇: X ( 1.新增 2.修改 4.刪除)
供應商代號: XXX  供應商代號: XXX  供應商名稱: XXX  供應商料號: XXX  單價: XXX  數量: XXX

PF3 =返回前頁  PF5 =重新整理  PF12=返回前頁  PF13=清除畫面
PF19=新增資料  PA1 =下一筆資料  PA2 =上一筆資料
```

### 3.2 子檔案顯示區域 (SFLSR)
- 位置：第 9~17 行
- 每頁顯示 9 筆資料
- 支援上下頁瀏覽

## 4. 紀錄格式

### 4.1 主畫面紀錄格式 (DSPD1)
| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 程式名稱 | - | 1,2 | 9 | A | O | 顯示 "<BAA150D>" |
| 公司名稱 | CONAME | 1,20 | 40 | A | O | 公司名稱 |
| 日期 | $CHYMD | 1,72 | 6,0 | Y | O | 系統日期，格式 YY/MM/DD |
| 使用者 | $USERN | 2,2 | 10 | A | O | 使用者名稱 |
| 供應商代號 | DQE01 | 4,14 | 6,0 | R | B | 供應商代號，必須輸入 |

### 4.2 子檔案紀錄格式 (SFLSR)
| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 記錄號 | RRN | - | 4,0 | S | H | 記錄號 |
| 零件編號 | QE02 | 9,3 | 6,0 | R | O | 零件編號 |
| 供應商代號 | QE03 | 9,24 | 6,0 | R | O | 供應商代號，格式 MM/DD/YY |
| 供應商名稱 | QE04 | 9,36 | 6,0 | R | O | 供應商名稱 |
| 供應商料號 | QE05 | 9,50 | 6,0 | R | O | 供應商料號 |
| 單價 | QE06 | 9,62 | 6,0 | R | O | 單價 |
| 數量 | QE07 | 9,72 | 6,0 | R | O | 數量 |

### 4.3 子檔案控制紀錄格式 (SFLCR)
| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 選擇 | DOPT | 20,10 | 1 | A | B | 功能選擇，可選值：1,2,4 |
| 供應商代號 | DQE02 | 21,3 | 6,0 | R | B | 供應商代號 |
| 供應商代號 | DQE03 | 21,24 | 6,0 | R | B | 供應商代號 |
| 供應商名稱 | DQE04 | 21,36 | 6,0 | R | B | 供應商名稱 |
| 供應商料號 | DQE05 | 21,50 | 6,0 | R | B | 供應商料號 |
| 單價 | DQE06 | 21,62 | 6,0 | R | B | 單價 |
| 數量 | DQE07 | 21,72 | 6,0 | R | B | 數量 |

## 5. 明細畫面

### 5.1 子檔案顯示
- 支援最多 60 筆資料顯示
- 每頁顯示 9 筆資料
- 支援上下頁瀏覽 (PageUp/PageDown)
- 支援記錄選擇和編輯

### 5.2 錯誤訊息顯示
- ERR1: 欄位驗證錯誤訊息
- ERR2: 資料庫存取錯誤訊息
- ERR3: 程式錯誤訊息
- ERR4: 權限錯誤訊息
- ERR5: 檔案錯誤訊息
- ERR6: 參數錯誤訊息
- ERR7: 系統錯誤訊息
- ERR8: 其他錯誤訊息
- ERR9: 一般錯誤訊息

## 6. 功能鍵說明

### 6.1 功能鍵定義
| 功能鍵 | 功能說明 | 處理程式 |
|--------|----------|----------|
| F3 | 返回前頁 | 03 |
| F5 | 重新整理 | 05 |
| F12 | 返回前頁 | 12 |
| F13 | 清除畫面 | 13 |
| F19 | 新增資料 | 19 |
| PageUp | 上一頁 | 25 |
| PageDown | 下一頁 | 26 |

### 6.2 功能鍵特性
- F3/F12: 返回前一個畫面
- F5: 重新整理子檔案資料
- F13: 清除輸入欄位
- F19: 新增一筆供應商零件對應資料
- PageUp/PageDown: 分頁瀏覽子檔案資料

## 7. 輸入欄位驗證

### 7.1 供應商代號驗證
- 供應商代號 (DQE01)：必須為有效的供應商代號
- 供應商代號必須存在於供應商主檔中

### 7.2 功能選擇驗證
- 選擇 (DOPT)：必須為 1, 2, 或 4
- 1: 新增資料
- 2: 修改資料
- 4: 刪除資料

### 7.3 資料欄位驗證
- 所有輸入欄位必須符合資料格式要求
- 數值欄位必須為有效數字
- 日期欄位必須為有效日期格式

## 8. 錯誤處理

### 8.1 錯誤訊息處理
- 所有錯誤訊息顯示在第 22 行
- 錯誤訊息以高亮度顯示
- 錯誤發生時游標會定位到錯誤欄位

### 8.2 錯誤類型
- **欄位驗證錯誤**：輸入資料格式不正確
- **資料庫存取錯誤**：無法存取相關資料檔案
- **權限錯誤**：使用者權限不足
- **檔案錯誤**：檔案不存在或無法開啟
- **程式錯誤**：程式執行時發生錯誤
- **參數錯誤**：傳入參數不正確

### 8.3 錯誤處理程序
1. 系統檢測到錯誤時，顯示對應錯誤訊息
2. 游標自動定位到錯誤欄位
3. 使用者修正錯誤後可重新執行
4. 按 F3 可返回前頁取消操作

## 9. 使用說明

### 9.1 畫面用途
此畫面用於維護供應商與零件的對應關係資料，包括新增、修改、刪除供應商零件對應記錄，並提供查詢和瀏覽功能。

### 9.2 操作流程
1. 輸入供應商代號進行查詢
2. 檢視子檔案中的對應資料
3. 選擇功能（新增/修改/刪除）
4. 輸入或修改相關資料
5. 按 Enter 執行操作
6. 使用功能鍵進行其他操作

### 9.3 功能說明
- **新增 (1)**：新增一筆供應商零件對應記錄
- **修改 (2)**：修改選定的供應商零件對應記錄
- **刪除 (4)**：刪除選定的供應商零件對應記錄

### 9.4 系統特色
- 支援子檔案顯示大量資料
- 完整的 CRUD 操作功能
- 分頁瀏覽機制
- 完整的錯誤處理機制
- 多種功能鍵支援

### 9.5 使用時機
- 需要維護供應商零件對應關係時
- 新增供應商零件對應資料時
- 修改現有對應資料時
- 刪除過期對應資料時
- 查詢供應商零件對應狀況時

### 9.6 注意事項
- 供應商代號必須為有效的系統代號
- 新增資料前請確認供應商和零件資料已存在
- 修改資料時請小心確認資料正確性
- 刪除資料前請確認不會影響其他相關作業
- 使用分頁功能可瀏覽大量資料
- 按 F3 可安全返回前頁 