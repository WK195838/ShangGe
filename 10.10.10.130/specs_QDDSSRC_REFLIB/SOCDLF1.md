# SOCDLF1 檔案規格書

## 1. 基本資料
- 檔名: SOCDLF1
- 類型: LF (Logical File)
- 說明: 銷售銷退月檔
- 主鍵: CD04
- 建立日期: (待補)
- 最後修改日期: (待補)
- 參考檔: SOCDPF
- 索引約束: 邏輯檔案

## 2. 檔案功能說明
此邏輯檔案為銷售銷退月檔，提供以下功能：
- 依產品代號排序的銷售銷退資料檢視
- 提供產品導向的銷售退貨查詢
- 支援產品銷售退貨的快速檢索
- 記錄產品的銷售與退貨統計
- 支援銷售退貨分析的資料檢視
- 提供產品與銷售的對照檢視
- 支援銷售管理的產品導向查詢
- 記錄銷售退貨的完整資訊
- 支援銷售分析的產品檢視
- 提供銷售退貨管理的邏輯檢視

## 3. 系統檔案清單
- 主要邏輯檔: SOCDLF1 (銷售銷退月檔邏輯檔1)
- 實體檔案: SOCDPF (銷售銷退月檔)
- 參考檔: RERF

## 4. 紀錄格式
邏輯檔案記錄格式，依產品代號排序，提供產品導向的銷售退貨檢視。

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明
| 欄位代號 | 名稱 | 位置 | 長度 | 屬性 | 檢核說明 |
|----------|------|------|------|------|----------|
| CD04 | 產品代號 | 參考實體檔 | 參考 | 參考 | 參考SOCDPF CD04 |

## 6. 主鍵欄位
- 主鍵: CD04
  - CD04: 產品代號
- 約束類型: 邏輯檔案主鍵

## 7. 索引資料
- 主要索引: CD04 (依產品代號)
- 索引類型: 邏輯檔案索引
- 排序特性: 
  - 第一層: 產品代號 (CD04)
- 實體檔案: SOCDPF

## 8. 備註
- 此邏輯檔案基於SOCDPF實體檔案
- 記錄CD0為邏輯檔案記錄格式名稱
- 依產品代號排序，便於產品導向的銷售管理
- 支援產品銷售退貨的快速查詢
- 提供產品與銷售的對照檢視
- 記錄完整的銷售退貨資訊
- 支援銷售分析的產品檢視
- 用於產品銷售管理的作業
- 支援銷售退貨的產品分析
- 記錄產品的銷售退貨軌跡
- 提供銷售管理的產品檢視
- 支援產品績效的分析
- 用於產品銷售的集中管理
- 提供銷售退貨的產品檢視
- 支援動態銷售的查詢與管理
- 記錄產品對銷售的完整關係
- 提供產品銷售管制的核心檢視
- 支援企業級的銷售管理需求
- 用於系統銷售的產品導向控制
- 提供銷售政策的產品實施檢視
- 支援銷售關係的追蹤與管理
- 記錄產品銷售的完整統計資訊
- 提供銷售分析的產品基礎資料
- 支援銷售報表的產品檢視
- 用於銷售決策的產品分析支援 