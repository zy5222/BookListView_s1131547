# BookListView_s1131547

## 核心功能介紹

### 1. 多重功能的圖書瀏覽 (ListView)
* **功能說明**：畫面左側為圖書主要展示區，內建《三國演義》、《西遊記》、《紅樓夢》等文學資料（包含書名、作者、類別與對應圖片）。
* **動態檢視切換**：透過右上角的下拉式選單 (`ComboBox`)，使用者可以即時切換「大圖示」、「詳細資料」、「小圖示」、「清單」與「大圖示加詳細資料 (`Tile`)」等 5 種不同的排版瀏覽模式。

### 2. 借書機制
* **操作方式**：使用者在圖書清單中對著想借的書籍觸發2下可以選取 (`ItemActivate` 事件)。
* **確認提示**：視窗會跳出一個對話方塊 (`MessageBox`) 詢問「確定要借閱嗎？」，待使用者確認按下「是」之後，才會將該書名加入到右側的「借書清單」(`ListBox`) 中。

## 防呆機制與設計

### 1. 重複借閱攔截保護
* **問題解決**：避免使用者不小心連點，或是重複將同一本書加入清單中。
* **判斷邏輯**：程式在觸發借閱提示前，會先使用 `Contains` 語法掃描右側借書清單。只有在 `exist != true`（清單內尚未有該書）的情況下，才會允許借閱動作，確保借出資料的正確性。

### 2. 視窗自動縮放與防重疊設計 (響應式佈局)
* **視覺優化**：解決了 Windows Forms 常見的視窗放大縮小時，左右區塊 (`Panel`) 互相覆蓋或產生大片留白的問題。
* **排版邏輯**：透過 `Dock` 屬性（右側的panel靠右停靠、左側的panel填滿）並結合「圖層顯示順序」的技巧，確保左側圖書區與右側清單區在拉扯視窗時，能等比例動態縮放，彼此互不侵犯地盤。

## 執行畫面
* **初始化面**:
  
  <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/add0ccd4-5b10-46e0-af50-8771b508e559" />
 
* **視窗放大縮小**:
  
  <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/d6fa2f12-0904-4f45-a4b6-0a5fd2300412" />
  <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/cd75088d-0479-4b9c-807a-4dde17ef1ed7" />
  
* **檢視方式選單**: 預設大圖示
  
  1.詳細資料
  
  <img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/1f4f61df-74e3-4570-aed7-383e545f3532" />

  2.小圖示
  
  <img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/26b4a8d0-c8dc-417c-a7ea-bf1ea9fe36ee" />

  3.清單
  
  <img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/fe6b8ef6-63a5-45a1-9a45-850cea74c134" />

  4.大圖示加詳細資料
  
  <img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/29816284-b51c-454b-9940-eee66e276be2" />

* **加入借書清單**:

  <img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/9140d966-fc3b-4c50-9ff6-321347312981" />
  <img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/69d47a5a-4127-4ae1-b534-ef6cc867c4a1" />



