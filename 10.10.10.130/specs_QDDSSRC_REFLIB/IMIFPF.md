# IMIFPF 檔案規格書

## 1. 基本資料

| 項目 | 內容 |
|------|------|
| 檔案名稱 | IMIFPF |
| 檔案類型 | 實體檔案 (Physical File) |
| 檔案用途 | 產品報廢明細檔 |
| 紀錄格式 | IF0 |
| 主鍵欄位 | IF02+IF03 |
| 特殊屬性 | UNIQUE、REF(RERF) |
| 特殊用途 | 產品報廢作業的明細資料管理 |

## 2. 檔案功能說明

IMIFPF是產品報廢明細檔的實體檔案：

1. **主要功能**：儲存產品報廢作業的明細資料
2. **檔案特性**：實體檔案，實際儲存資料
3. **系統用途**：支援產品報廢作業的明細管理
4. **資料完整性**：具有UNIQUE屬性，確保資料唯一性
5. **參考檔案**：使用REF(RERF)參考檔案進行欄位定義
6. **支援功能**：為產品報廢作業提供完整的明細資料基礎

## 3. 系統檔案清單

| 檔案名稱 | 檔案類型 | 說明 |
|----------|----------|------|
| IMIFPF | 實體檔案 | 產品報廢明細檔實體檔案（本檔案） |
| IMIEPF | 實體檔案 | 產品報廢主檔實體檔案 |
| IMIELF01 | 邏輯檔案 | 產品報廢主檔邏輯檔案（IE01+IE05+IE02排序） |
| IMIELF02 | 邏輯檔案 | 產品報廢主檔邏輯檔案（IE05+IE01+IE02排序） |
| IMIELF1 | 邏輯檔案 | 產品報廢主檔邏輯檔案（IE05降序+IE02排序） |

## 4. 紀錄格式

| 格式名稱 | 說明 |
|----------|------|
| IF0 | 產品報廢明細記錄格式 |

## 5. 欄位代號、名稱、位置、長度、屬性、檢核說明

| 欄位代號 | 欄位名稱 | 位置 | 長度 | 型態 | 屬性 | 說明 |
|----------|----------|------|------|------|------|------|
| IF01 | 報廢單號 | 1 | - | R | 參考欄位 | 報廢單號 |
| IF02 | 客戶代號 | 2 | - | R | 主鍵/參考欄位 | 客戶代號 |
| IF03 | 產品代號 | 3 | - | R | 主鍵/參考欄位 | 產品代號 |
| IF04 | 報廢數量 | 4 | - | R | 參考欄位 | 報廢數量 |
| IF05 | 報廢單位成本 | 5 | - | R | 參考欄位 | 報廢單位成本 |
| IF06 | 報廢日期 | 6 | 8 | 數值 | 參考欄位 | 報廢日期 |
| IF07 | 產品代號 | 7 | - | R | 參考欄位 | 產品代號 |
| IF08 | FOB總額 | 8 | - | R | 參考欄位 | FOB總額 |
| IF09 | FHI總額 | 9 | - | R | 參考欄位 | FHI總額 |
| IF10 | 關稅總額 | 10 | - | R | 參考欄位 | 關稅總額 |
| IFXX | 異動日期 | 11 | 8 | 數值 | 參考欄位 | 異動日期 |
| IFYY | 異動時間 | 12 | - | R | 參考欄位 | 異動時間 |
| IFZZ | 異動人員 | 13 | - | R | 參考欄位 | 異動人員 |

*註：所有欄位使用REF(RERF)參考檔案定義，R表示參考欄位*

## 6. 主鍵欄位

本實體檔案的主鍵欄位為：
- IF02（客戶代號）
- IF03（產品代號）

### 主鍵特性：
- **IF02（客戶代號）**：主鍵第一層，客戶代號
- **IF03（產品代號）**：主鍵第二層，產品代號
- **UNIQUE屬性**：確保客戶代號+產品代號的唯一性
- **兩層主鍵**：以客戶代號+產品代號作為複合唯一識別
- **資料完整性**：保證每個客戶的每個產品只有一筆明細記錄

## 7. 索引資料

| 索引名稱 | 索引鍵 | 排序 | 用途說明 |
|----------|--------|------|----------|
| 主索引 | IF02+IF03 | 升序+升序 | 客戶代號+產品代號複合主鍵索引 |

### 索引特性：
- **複合主鍵索引**：客戶代號+產品代號的複合索引
- **UNIQUE約束**：確保客戶代號+產品代號組合不重複
- **高效查詢**：提供快速的客戶產品組合查詢

## 8. 備註

1. **實體檔案特性**：
   - 產品報廢明細檔的實體檔案
   - 實際儲存報廢作業的明細資料
   - 具有UNIQUE屬性確保資料唯一性
2. **產品報廢明細功能**：
   - 支援產品報廢作業的明細管理
   - 提供報廢明細的完整資料儲存
   - 支援報廢作業的成本計算
3. **資料完整性設計**：
   - UNIQUE屬性確保客戶代號+產品代號唯一性
   - REF(RERF)參考檔案統一欄位定義
   - 完整的異動追蹤機制
4. **與其他檔案關聯**：
   - 與IMIEPF主檔案形成主明細關係
   - 支援完整的報廢作業資料結構
   - 提供報廢明細的詳細資訊
5. **報廢明細支援**：
   - 報廢單號管理（IF01）
   - 客戶代號管理（IF02）
   - 產品代號管理（IF03）
   - 報廢數量管理（IF04）
   - 報廢單位成本管理（IF05）
   - 報廢日期管理（IF06）
6. **成本管理功能**：
   - 報廢單位成本（IF05）
   - FOB總額（IF08）
   - FHI總額（IF09）
   - 關稅總額（IF10）
   - 完整的成本項目管理
7. **異動追蹤機制**：
   - 異動日期（IFXX）
   - 異動時間（IFYY）
   - 異動人員（IFZZ）
   - 完整的異動記錄追蹤
8. **業務應用**：
   - 產品報廢明細申請管理
   - 報廢成本計算
   - 報廢數量統計
   - 報廢明細記錄查詢
9. **系統整合**：
   - 與庫存管理系統（IMI系列）整合
   - 支援庫存狀態的報廢調整
   - 提供完整的庫存報廢明細管理
10. **資料驗證**：
    - 客戶代號+產品代號唯一性驗證
    - 報廢數量合理性驗證
    - 成本金額合理性驗證
    - 日期格式驗證
11. **報廢流程支援**：
    - 報廢明細申請記錄
    - 報廢明細執行記錄
    - 報廢明細確認記錄
    - 報廢明細完成記錄
12. **客戶管理整合**：
    - 客戶代號（IF02）作為主鍵第一層
    - 支援客戶別報廢明細管理
    - 提供客戶報廢明細記錄查詢
13. **產品管理整合**：
    - 產品代號（IF03）作為主鍵第二層
    - 產品代號（IF07）提供額外產品資訊
    - 支援產品別報廢明細統計
14. **時間維度管理**：
    - 報廢日期（IF06）管理
    - 異動日期（IFXX）管理
    - 異動時間（IFYY）管理
    - 完整的時間追蹤功能
15. **系統價值**：
    - 作為產品報廢系統的重要明細檔案
    - 提供完整的報廢明細資料管理功能
    - 支援報廢作業的各種明細查詢需求
16. **特殊設計**：
    - 客戶代號+產品代號複合主鍵設計
    - UNIQUE屬性確保資料完整性
    - REF(RERF)統一欄位定義
17. **庫存影響管理**：
    - 與庫存系統緊密整合
    - 支援庫存報廢狀態更新
    - 提供庫存報廢明細調整功能
18. **成本影響管理**：
    - 支援報廢成本明細計算
    - 提供成本報廢明細調整
    - 支援成本明細分析需求
19. **決策支援**：
    - 提供報廢決策明細資料
    - 支援報廢政策制定
    - 提供報廢效果明細評估
20. **合規管理**：
    - 支援報廢作業合規要求
    - 提供報廢明細記錄審計
    - 確保報廢作業透明度
21. **報廢統計功能**：
    - 支援報廢數量明細統計
    - 提供報廢金額明細統計
    - 支援報廢明細趨勢分析
22. **品質管理整合**：
    - 產品代號（IF03、IF07）管理
    - 支援品質報廢明細分析
    - 提供品質改善明細資料
23. **多維度分析**：
    - 客戶維度（IF02）
    - 產品維度（IF03、IF07）
    - 時間維度（IF06）
    - 數量維度（IF04）
    - 成本維度（IF05、IF08、IF09、IF10）
24. **系統維護**：
    - 實體檔案易於維護
    - 資料備份恢復支援
    - 提供良好的系統維護性
25. **參考檔案整合**：
    - 使用REF(RERF)參考檔案
    - 統一的欄位定義標準
    - 確保資料一致性
26. **報廢監控功能**：
    - 報廢數量（IF04）監控
    - 支援報廢作業明細狀態追蹤
    - 提供報廢明細異常監控
27. **資料完整性保證**：
    - UNIQUE屬性確保唯一性
    - 複合主鍵約束確保資料完整性
    - 參考檔案確保欄位一致性
28. **報廢作業效率**：
    - 複合主鍵提升查詢效率
    - 合理的欄位設計提升處理效率
    - 支援快速的報廢明細作業處理
29. **系統擴展性**：
    - 良好的檔案結構設計
    - 支援未來功能擴展
    - 提供系統成長空間
30. **業務流程支援**：
    - 完整的報廢明細作業流程支援
    - 從申請到確認的全程明細管理
    - 提供完整的業務流程明細基礎
31. **成本項目完整性**：
    - FOB總額（IF08）- 離岸價格總額
    - FHI總額（IF09）- 運費保險總額
    - 關稅總額（IF10）- 進口關稅總額
    - 完整的進口成本結構管理
32. **主明細關係**：
    - 與IMIEPF主檔形成完整的主明細架構
    - 支援一對多的報廢資料關係
    - 提供完整的報廢資料結構
33. **數量成本管理**：
    - 報廢數量（IF04）與單位成本（IF05）結合
    - 支援總成本計算和分析
    - 提供完整的數量成本管理
34. **產品識別機制**：
    - 主鍵產品代號（IF03）
    - 額外產品代號（IF07）
    - 雙重產品識別確保資料準確性
35. **報廢成本分析**：
    - 單位成本與總額成本的完整記錄
    - 支援成本結構分析
    - 提供報廢成本效益評估
36. **時間序列支援**：
    - 報廢日期（IF06）支援時間序列分析
    - 異動日期（IFXX）支援異動追蹤
    - 完整的時間維度管理
37. **客戶產品組合管理**：
    - 客戶代號+產品代號的複合主鍵
    - 支援客戶產品組合分析
    - 提供客戶產品報廢統計
38. **報廢單據整合**：
    - 報廢單號（IF01）連結主檔
    - 支援單據化的報廢管理
    - 提供完整的單據追蹤
39. **成本會計支援**：
    - 完整的成本項目記錄
    - 支援成本會計處理
    - 提供成本分攤基礎
40. **庫存調整基礎**：
    - 提供庫存調整的明細依據
    - 支援庫存數量調整
    - 確保庫存資料準確性 