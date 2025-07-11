# DPA003D - 錯誤統一發票重開 螢幕規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 程式名稱 | DPA003D |
| 程式類型 | DSPF (顯示檔案) |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 發票管理子系統 |
| 作者 | ANDY |
| 建立日期 | 81/07/13 |
| 更新日期 |  |
| 備註 | 錯誤統一發票重開 |

## 2. 螢幕規格

### 2.1 螢幕基本設定
- 螢幕大小：24 行 × 80 欄位
- 顯示模式：*DS3 (雙密度)
- 訊息位置：第 24 行
- 支援列印功能
- 支援訊息控制
- 支援功能鍵處理

### 2.2 螢幕特性
- 支援游標定位 (CSRLOC)
- 支援覆蓋模式
- 支援多種功能鍵
- 支援欄位驗證

## 3. 螢幕布局

### 3.1 主要畫面布局 (DSPD1)
```
DPA003                                                  日期: YY/MM/DD
SCR001  錯誤統一發票重開                                時間: HH:MM:SS
                                                           USER : XXXXX

          客戶代號: XXX-XXX

          客戶名稱: XXX-XXX

          產品代號: XXX

          發票日期: MM/DD/YY (MM/DD/YY)

          檢核方式: X (1-年度   2-月份)

          列印份數: XXX

          列印編號: XX

***請輸入錯誤統一發票重開參數***

F3 =返回前頁  F4 =說明資料
```

## 4. 紀錄格式

### 4.1 主畫面紀錄格式 (DSPD1)
| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 程式名稱 | - | 1,2 | 6 | A | O | 顯示 "DPA003" |
| 日期 | $EGMDY | 1,70 | 6,0 | Y | O | 系統日期，格式 YY/MM/DD |
| 畫面編號 | - | 2,2 | 6 | A | O | 顯示 "SCR001" |
| 畫面標題 | - | 2,31 | 8 | A | O | 顯示 "錯誤統一發票重開" |
| 時間 | TIME | 2,70 | 8 | T | O | 系統時間，格式 HH:MM:SS |
| 使用者 | $USER | 3,70 | 10 | A | O | 登入使用者代號 |
| 客戶代號起 | DSI03S | 7,41 | 6,0 | R | B | 客戶代號起始值 |
| 客戶代號迄 | DSI03E | 7,46 | 6,0 | R | B | 客戶代號結束值 |
| 客戶名稱起 | DSI04S | 8,41 | 6,0 | R | B | 客戶名稱起始值 |
| 客戶名稱迄 | DSI04E | 8,46 | 6,0 | R | B | 客戶名稱結束值 |
| 產品代號 | DSI05 | 9,41 | 6,0 | R | B | 產品代號 |
| 發票日期 | DSI06 | 10,41 | 6,0 | Y | B | 發票日期，格式 MM/DD/YY |
| 檢核方式 | $EVR | 16,41 | 1,0 | Y | B | 檢核方式選擇，可選值：1,2 |
| 列印份數 | $CPY | 17,41 | 3,0 | Y | B | 列印份數 |
| 列印編號 | $PRTID | 18,41 | 2,0 | Y | B | 列印編號 |

## 5. 明細畫面

### 5.1 輸入區域
- 客戶代號範圍輸入區域
- 客戶名稱範圍輸入區域
- 產品代號輸入區域
- 發票日期輸入區域
- 檢核方式選擇區域
- 列印參數設定區域

### 5.2 錯誤訊息顯示
- ERR1: 欄位驗證錯誤訊息
- ERR2: 資料庫存取錯誤訊息
- ERR3: 系統錯誤訊息
- ERR4: 程式錯誤訊息
- ERR5: 權限錯誤訊息
- ERR6: 檔案錯誤訊息
- ERR7: 參數錯誤訊息
- ERR10: 一般錯誤訊息
- ERR11: 其他錯誤訊息
- ERR12: 資料錯誤訊息

## 6. 功能鍵說明

### 6.1 功能鍵定義
| 功能鍵 | 功能說明 | 處理程式 |
|--------|----------|----------|
| F3 | 返回前頁 | 03 |
| F4 | 說明資料 | 04 |

### 6.2 功能鍵特性
- F3: 返回前一個畫面
- F4: 顯示說明資料

## 7. 輸入欄位驗證

### 7.1 客戶代號驗證
- 客戶代號起迄 (DSI03S, DSI03E)：必須為有效的客戶代號
- 起始值不能大於結束值
- 客戶代號必須存在於客戶主檔中

### 7.2 客戶名稱驗證
- 客戶名稱起迄 (DSI04S, DSI04E)：必須為有效的客戶名稱
- 起始值不能大於結束值
- 客戶名稱格式必須正確

### 7.3 產品代號驗證
- 產品代號 (DSI05)：必須為有效的產品代號
- 產品代號必須存在於產品主檔中
- 產品代號格式必須正確

### 7.4 發票日期驗證
- 發票日期 (DSI06)：必須為有效的日期格式 MM/DD/YY
- 日期必須在系統允許的範圍內
- 日期格式必須正確

### 7.5 檢核方式驗證
- 檢核方式 ($EVR)：必須為 1 或 2
- 1: 年度檢核
- 2: 月份檢核

### 7.6 列印參數驗證
- 列印份數 ($CPY)：必須為正整數
- 列印編號 ($PRTID)：必須為有效的印表機編號

## 8. 錯誤處理

### 8.1 錯誤訊息處理
- 所有錯誤訊息顯示在第 24 行
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
此畫面用於處理錯誤統一發票的重開作業，包括客戶代號範圍、客戶名稱範圍、產品代號、發票日期等參數設定，用於重新產生錯誤的統一發票。

### 9.2 操作流程
1. 輸入客戶代號範圍
2. 輸入客戶名稱範圍
3. 輸入產品代號
4. 輸入發票日期
5. 選擇檢核方式
6. 設定列印參數
7. 按 Enter 執行重開作業
8. 使用功能鍵進行其他操作

### 9.3 重開功能說明
- **年度檢核 (1)**：依年度範圍重開錯誤發票
- **月份檢核 (2)**：依月份範圍重開錯誤發票
- **客戶範圍重開**：可指定特定客戶範圍進行重開
- **產品重開**：可指定特定產品進行重開
- **列印功能**：支援多份列印和指定印表機

### 9.4 系統特色
- 支援範圍查詢功能
- 多種檢核方式選擇
- 完整的參數驗證機制
- 靈活的列印設定
- 完整的錯誤處理機制

### 9.5 使用時機
- 統一發票錯誤修正時
- 發票資料重新產生時
- 發票格式調整時
- 發票內容更正時
- 發票系統維護時

### 9.6 注意事項
- 客戶代號範圍必須正確設定
- 產品代號必須正確
- 發票日期必須合理
- 檢核方式必須正確選擇
- 列印參數必須正確設定
- 使用 F4 可查看詳細說明
- 按 F3 可安全返回前頁 