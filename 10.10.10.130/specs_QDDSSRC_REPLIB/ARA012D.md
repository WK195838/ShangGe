# ARA012D 專櫃轉帳資料批次作業 螢幕規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 程式代號 | ARA012D |
| 程式名稱 | 專櫃轉帳資料批次作業 |
| 程式類型 | 螢幕格式檔（DSPF） |
| 作者 | A1187 JOYCE |
| 建立日期 | 81/03/18 |
| 程式名稱 | ARA012 |
| 系統 | 應收帳款 |
| 子系統 | 應收帳管作業 |
| 功能說明 | 專櫃轉帳資料批次作業 |

## 2. 螢幕規格

| 項目 | 規格 |
|------|------|
| 螢幕大小 | 24x80 |
| 螢幕類型 | DSPSIZ(24 80 *DS3) |
| 參考檔案 | REF(*LIBL/RERF) |
| 訊息位置 | MSGLOC(24) |
| 列印功能 | PRINT |

## 3. 螢幕布局

```
ARA012                         程式訊息                        日期:MM/DD/YY
SCR001                       專櫃轉帳資料批次作業                時間:HH:MM:SS
                                                                USER :XXXXXXX




      

      

      

        截止日:MM/DD/YY




底線      F3 =回到前頁                                        F14=處理作業
                                                                [錯誤訊息位置]
```

## 4. 紀錄格式

### 4.1 主畫面記錄格式

#### DSPD1 - 主輸入記錄
| 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|------|------|------|------|------|
| D#ROW | | 3,0 | N | H | 游標列位置 |
| D#COL | | 3,0 | N | H | 游標欄位置 |
| $EGMDY | 1,70 | 6,0 | N | O | 系統日期(EDTCDE(Y)) |
| $USER | 3,70 | 10 | A | O | 使用者代號 |
| DSC08 | 9,40 | 6,0 | N | O | 截止日期(EDTWRD('  /  /  ')) |

## 5. 明細畫面

### 5.1 參數設定畫面
- **DSPD1**: 專櫃轉帳批次參數設定
  - 設定處理截止日期
  - 簡化的參數輸入介面
  - 游標位置控制功能

## 6. 功能鍵說明

| 功能鍵 | 說明 |
|--------|------|
| F3 | 回到前頁 |
| F14 | 處理作業 |
| CA03(03) | 回到前頁('回到前頁') |
| CF14(14) | 處理作業('處理作業') |

## 7. 輸入欄位驗證

### 7.1 欄位格式驗證
- **DSC08**: 日期格式(EDTWRD('  /  /  '))
- **截止日期**: 必須為有效的日期格式

### 7.2 游標控制
- **CSRLOC**: 支援游標位置控制(D#ROW, D#COL)
- **OVERLAY**: 覆蓋顯示模式

## 8. 錯誤處理

### 8.1 錯誤訊息指示器
| 指示器 | 訊息ID | 說明 |
|--------|--------|------|
| 98 | UPT 2142 | 錯誤訊息1 |
| 97 | UPT 2110 | 錯誤訊息2 |
| 96 | UPT 2150 | 錯誤訊息3 |
| 95 | UPT 0010 | 錯誤訊息4 |
| 94 | UPT 2010 | 錯誤訊息5 |
| 93 | UPT 0040 | 錯誤訊息6 |
| 92 | UPT 1011 | 錯誤訊息7 |
| 91 | UPT 0041 | 錯誤訊息8 |
| 90 | UPT 1011 | 錯誤訊息9 |
| 88 | URE 0108 | 系統相關錯誤 |

### 8.2 訊息處理
- 訊息顯示位置: 第24列
- 訊息檔案: PTMF, REMF
- 程式訊息: URE9999 (REMF)
- 一般訊息: UPT9999 (PTMF)

## 9. 使用說明

### 9.1 作業流程
1. 輸入處理截止日期
2. 確認截止日期格式正確
3. 按F14執行專櫃轉帳批次處理
4. 系統進行專櫃相關資料的轉帳作業

### 9.2 專櫃轉帳功能
- **批次處理**: 大量專櫃轉帳資料處理
- **截止日控制**: 依截止日期篩選資料範圍
- **自動化處理**: 減少人工作業錯誤

### 9.3 注意事項
- 截止日期為必要輸入欄位
- 日期格式須符合MM/DD/YY標準
- 執行前請確認截止日期設定正確
- 批次處理完成後需檢查處理結果

### 9.4 專櫃作業說明
- **專櫃轉帳**: 專櫃相關的轉帳資料處理
- **批次作業**: 一次處理大量轉帳資料
- **截止日控制**: 確保資料處理的時間範圍
- **簡化操作**: 僅需設定截止日期即可執行 