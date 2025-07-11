# DPB002D - 備份檔案整理 螢幕規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 程式名稱 | DPB002D |
| 程式類型 | DSPF (顯示檔案) |
| 系統名稱 | 應收帳款系統 |
| 子系統 | 檔案管理子系統 |
| 作者 | A1034 STEPHANIE |
| 建立日期 | 81/05/04 |
| 更新日期 |  |
| 備註 | 備份檔案整理 |

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
- 支援強制資料輸入 (FRCDTA)
- 支援螢幕鎖定 (LOCK)
- 支援多種功能鍵

## 3. 螢幕布局

### 3.1 主要畫面布局 (DSPD1)
```
DPB002                                                  日期: YY/MM/DD
SCR001  備份檔案整理                                    時間: HH:MM:SS
                                                           USER : XXXXX

          備份年度: YYYY-YYYY

          目標設備: XXXXXXXXXX

          目標卷冊: XXXXXX

          目前備份: XXXXXXXXXX

+------------------------------------------+
|                                          |
| 注意:按F14鍵可備份檔案，按F3取消檔案     |
|                                          |
|  說明:將備份檔案整理到指定設備的指定     |
|       年度目錄下                         |
|                                          |
+------------------------------------------+

***請輸入目標設備***

F3 =返回前頁  F14=備份檔案
```

## 4. 紀錄格式

### 4.1 主畫面紀錄格式 (DSPD1)
| 欄位名稱 | 欄位代號 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| 程式名稱 | - | 1,2 | 6 | A | O | 顯示 "DPB002" |
| 日期 | $EGMDY | 1,70 | 6,0 | Y | O | 系統日期，格式 YY/MM/DD |
| 畫面編號 | - | 2,2 | 6 | A | O | 顯示 "SCR001" |
| 畫面標題 | - | 2,32 | 6 | A | O | 顯示 "備份檔案整理" |
| 時間 | TIME | 2,70 | 8 | T | O | 系統時間，格式 HH:MM:SS |
| 使用者 | $USER | 3,70 | 10 | A | O | 登入使用者代號 |
| 備份年度起 | DMYS | 5,38 | 4,0 | Y | O | 備份年度起始值，格式 YYYY |
| 備份年度迄 | DMYE | 5,46 | 4,0 | Y | O | 備份年度結束值，格式 YYYY |
| 目標設備 | DTDEV | 6,38 | 10 | A | O | 目標設備名稱 |
| 目標卷冊 | DVOL | 7,38 | 6 | A | O | 目標卷冊名稱 |
| 目前備份 | DFILE | 9,38 | 10 | A | O | 目前備份檔案名稱 |

## 5. 明細畫面

### 5.1 說明框區域
- 位置：第 11~19 行，第 17~65 欄
- 大小：9 行 × 49 欄
- 包含邊框設計
- 顯示操作說明和注意事項

### 5.2 錯誤訊息顯示
- ERR1: 權限錯誤訊息
- ERR2: 設備錯誤訊息

### 5.3 警告訊息
- 第 20 行顯示 "***請輸入目標設備***" 警告訊息

## 6. 功能鍵說明

### 6.1 功能鍵定義
| 功能鍵 | 功能說明 | 處理程式 |
|--------|----------|----------|
| F3 | 返回前頁 | 03 |
| F14 | 備份檔案 | 14 |

### 6.2 功能鍵特性
- F3: 返回前一個畫面，取消檔案整理作業
- F14: 執行檔案備份作業，將備份檔案整理到指定設備

## 7. 輸入欄位驗證

### 7.1 年度範圍驗證
- 備份年度起迄 (DMYS, DMYE)：必須為有效的年度格式 YYYY
- 起始年度不能大於結束年度
- 年度範圍必須合理

### 7.2 目標設備驗證
- 目標設備 (DTDEV)：必須為有效的設備名稱
- 設備名稱長度不能超過 10 個字元
- 設備必須存在且可存取

### 7.3 目標卷冊驗證
- 目標卷冊 (DVOL)：必須為有效的卷冊名稱
- 卷冊名稱長度不能超過 6 個字元
- 卷冊必須存在且可存取

### 7.4 檔案存在性驗證
- 指定年度範圍內必須有備份檔案存在
- 目標設備必須有足夠的儲存空間
- 使用者必須具有檔案存取權限

## 8. 錯誤處理

### 8.1 錯誤訊息處理
- 所有錯誤訊息顯示在第 24 行
- 錯誤訊息以高亮度顯示
- 錯誤發生時游標會定位到錯誤欄位

### 8.2 錯誤類型
- **權限錯誤**：使用者權限不足
- **設備錯誤**：目標設備不存在或無法存取
- **卷冊錯誤**：目標卷冊不存在或無法存取
- **空間錯誤**：目標設備儲存空間不足
- **檔案錯誤**：備份檔案不存在或無法存取

### 8.3 錯誤處理程序
1. 系統檢測到錯誤時，顯示對應錯誤訊息
2. 游標自動定位到錯誤欄位
3. 使用者修正錯誤後可重新執行
4. 按 F3 可返回前頁取消操作

## 9. 使用說明

### 9.1 畫面用途
此畫面用於將備份檔案整理到指定的設備、卷冊和年度目錄下，提供檔案備份和整理功能，確保備份資料的安全保存。

### 9.2 操作流程
1. 系統顯示備份年度範圍
2. 確認目標設備和卷冊
3. 檢視目前備份檔案
4. 按 F14 執行檔案備份作業
5. 等待檔案整理完成
6. 使用功能鍵進行其他操作

### 9.3 檔案整理功能說明
- **年度範圍整理**：依指定年度範圍整理備份檔案
- **設備備份**：將檔案備份到指定設備
- **卷冊管理**：管理目標卷冊
- **目錄管理**：自動建立年度目錄結構
- **檔案搬移**：將備份檔案搬移到目標位置

### 9.4 系統特色
- 支援年度範圍指定
- 支援多種設備類型
- 支援卷冊管理
- 完整的檔案管理功能
- 安全的備份機制
- 完整的錯誤處理機制

### 9.5 使用時機
- 備份檔案整理時
- 系統維護作業時
- 資料備份時
- 儲存空間管理時
- 檔案歸檔作業時

### 9.6 注意事項
- 目標設備必須正確設定
- 目標卷冊必須正確設定
- 年度範圍必須合理
- 確保有足夠的儲存空間
- 注意檔案存取權限
- 大型檔案整理可能需要較長時間
- 使用 F14 可執行檔案備份
- 按 F3 可安全返回前頁 