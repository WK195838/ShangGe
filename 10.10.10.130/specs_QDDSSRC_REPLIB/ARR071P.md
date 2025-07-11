# ARR071P 報表規格書

## 1. 基本資料
- 檔案名稱：ARR071P
- 類型：PRTF
- 主要用途：折讓成本差異表列印

## 2. 報表結構
- 報表類型：明細報表
- 主要格式：PH1、PD1、PT1、PE1、PE2、PE3

## 3. 報表布局
- 標題、日期、時間、使用者資訊
- 多個資料欄位（COMP、DSH03S/E、DSG04S/E、DSG26S/E、$EVR、$CPY、$PRTID 等）

## 4. 報表欄位規格
| 欄位代號 | 名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|------|------|------|------|------|------|
| COMP     | 公司別|?    | 1    | 字串 | 必填 | 1=台北 2=台中 3=高雄 " "=全部 |
| DSH03S   | 起產品|?    | 9    | 參照 | 必填 |      |
| DSH03E   | 迄產品|?    | 9    | 參照 | 必填 |      |
| DSG04S   | 起客戶|?    | 5    | 字串 | 必填 |      |
| DSG04E   | 迄客戶|?    | 5    | 字串 | 必填 |      |
| DSG26S   | 起日期|?    | 6    | 日期 | 必填 | MM/DD/YY |
| DSG26E   | 迄日期|?    | 6    | 日期 | 必填 | MM/DD/YY |
| $EVR     | 狀態 |?    | 1    | 數值 | 必填 | 1-有效 2-作廢 |
| $CPY     | 複製 |?    | 3    | 數值 | 必填 |      |
| $PRTID   | 列印ID|?    | 2    | 數值 | 必填 |      |

## 5. 明細資料欄位規格
- WF7804：折讓日期
- WF7805：折讓單號
- WF7806：產品代號
- WF7802/WF7803：客戶代號
- WF7810/WF7811：折讓金額
- WF7808/WF7809：成本金額
- TOT089：總計

## 6. 報表標題內容
- 折讓成本差異表

## 7. 報表欄位說明
- 依畫面提示操作

## 8. 使用說明
- 依畫面提示操作 