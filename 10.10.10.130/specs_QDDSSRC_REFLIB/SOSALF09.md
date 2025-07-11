# SOSALF09 檔案規格書

## 1. 基本資料
- 檔名: SOSALF09
- 類型: LF (Logical File)
- 說明: 通路型態產品報價資料檔
- 主鍵: SA02+SA03+SA05 (SA05降序)
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考實體檔: SOSAPF
- 索引約束: 邏輯檔案

## 2. 檔案功能說明
此邏輯檔案為通路型態產品報價資料檔，提供以下功能：
- 提供通路型態產品報價的特殊排序檢視
- 支援通路管理的產品報價特殊查詢
- 提供產品報價的不同維度分析
- 支援通路策略的報價管理
- 記錄通路型態的產品定價資訊
- 提供通路報價的特殊檢視
- 支援通路管理的特殊排序查詢
- 記錄通路型態的報價策略
- 支援產品管理的通路報價
- 提供通路型態報價的特殊邏輯檔案

## 3. 系統檔案清單
- 主要邏輯檔: SOSALF09 (通路型態產品報價資料檔)
- 基礎實體檔: SOSAPF (通路型態產品報價實體檔)
- 相關邏輯檔: SOSALF (標準排序版本)

## 4. 紀錄格式
邏輯檔案記錄格式，依SA02+SA03+SA05複合主鍵排序(SA05降序)，承繼SOSAPF實體檔案的所有欄位結構。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| SA02 | 主鍵欄位2 | 承繼 | 承繼 | 承繼SOSAPF | 主鍵1，通路型態相關 |
| SA03 | 主鍵欄位3 | 承繼 | 承繼 | 承繼SOSAPF | 主鍵2，通路型態相關 |
| SA05 | 主鍵欄位5 | 承繼 | 承繼 | 承繼SOSAPF | 主鍵3，降序排列 |
| SA01 | 主鍵欄位1 | 承繼 | 承繼 | 承繼SOSAPF | 非主鍵，通路型態相關 |
| SA04 | 主鍵欄位4 | 承繼 | 承繼 | 承繼SOSAPF | 非主鍵，通路型態相關 |
| ... | 其他欄位 | 承繼 | 承繼 | 承繼SOSAPF | 承繼SOSAPF實體檔的所有欄位 |

## 6. 主鍵欄位
- 主鍵: SA02+SA03+SA05
  - SA02: 通路型態主鍵1
  - SA03: 通路型態主鍵2
  - SA05: 通路型態主鍵3 (降序)
- 約束類型: 三層複合主鍵，特殊排序

## 7. 索引資料
- 主要索引: SA02+SA03+SA05 (依通路型態特殊排序)
- 索引類型: 邏輯檔案索引
- 排序特性: 
  - 第一層: SA02 (升序)
  - 第二層: SA03 (升序)
  - 第三層: SA05 (降序，使用DESCEND)

## 8. 備註
- 此邏輯檔案用於通路型態產品報價特殊排序管理
- 記錄SA0為邏輯檔案記錄格式名稱
- 基於SOSAPF實體檔案建立的特殊檢視
- 使用PFILE(SOSAPF)指定實體檔案
- 與SOSALF相同基礎檔案但不同排序策略
- 採用三層複合主鍵，省略SA01和SA04
- SA05使用DESCEND降序排列，提供特殊分析視角
- 承繼SOSAPF實體檔案的完整欄位結構
- 記錄通路型態的產品報價資訊
- 用於通路管理的特殊排序查詢作業
- 支援通路策略的特殊分析
- 記錄通路型態的報價軌跡
- 提供通路管理的特殊資料檢視
- 支援通路政策的報價實施
- 用於通路報價的特殊查詢與分析
- 提供通路分析的特殊基礎資料
- 支援通路管理的特殊標準作業
- 記錄通路報價的完整資訊
- 用於通路決策的特殊支援作業
- 提供通路報價管理的特殊資料平台
- 支援通路策略的特殊執行與分析
- 記錄通路報價的特殊標準設定
- 用於通路報價的特殊統一管理
- 提供通路維護的特殊標準化作業
- 支援企業級的通路報價特殊管理
- 記錄通路型態產品報價的特殊軌跡 