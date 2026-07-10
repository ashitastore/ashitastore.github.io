# 🛒 Ashita Store 商品手動新增指南

本指南將引導您如何在未來手動為網站新增商品。我們已將商品設計為**模組化目錄架構**，您只需簡單複製、貼上即可完成新增！

---

## 📌 新增商品 3 步驟

### 步驟 1：建立並編輯商品資料夾
1. 前往 `products/` 目錄，複製 `template` 資料夾。
2. 將複製出來的資料夾重新命名為您新商品的**英文簡稱**（全部小寫，空格用底線或連字號代替，例如：`antimite-textile` 或 `eco-cleaner`）。
3. 進入該新資料夾中：
   * 將您的商品封面圖片命名為 `cover.jpg` 並取代原本的檔案（建議比例為 1:1 正方形）。
   * 開啟 `index.html`，根據標記（如 `【商品名稱】`、`【商品價格】`）修改商品名稱、文案、規格參數，以及底部的**蝦皮電商購買連結**（將 `href` 修改為您的賣場連結）。

---

### 步驟 2：在「產品中心 (products.html)」新增卡片
1. 開啟根目錄下的 `products.html`。
2. 找到對應的分類區塊（例如 `#natural` 天然食品區、`#health` 保健功能區、`#home` 生活用品區）的 `<div class="product-grid">`。
3. 複製以下 HTML 卡片代碼，並貼在該網格內：

```html
<article class="product-card-v2"> 
    <!-- ⚠️ 請將 src 的路徑修改為您剛建立的商品封面圖路徑 -->
    <img src="assets/images/household.png" alt="新商品名稱"> 
    <div class="product-body"> 
        <!-- ⚠️ 修改商品名稱 -->
        <h3>新商品名稱</h3> 
        <!-- ⚠️ 修改簡短介紹 -->
        <p>這是一句話商品精簡介紹，用來吸引顧客點擊查看詳情。</p> 
        <div class="card-action">
            <!-- ⚠️ 將 href 的路徑指向您剛建立的商品 index.html -->
            <a href="products/您的資料夾名稱/index.html" class="btn btn-sm-store"><i class="fas fa-search"></i> 查看詳情</a> 
        </div>                                 
    </div>                             
</article>
```

---

### 步驟 3：在「首頁 (index.html)」新增精選推薦（非必填）
如果您希望這項新商品也出現在首頁的「精選商品推薦」中：
1. 開啟根目錄下的 `index.html`。
2. 尋找 `<div class="product-grid">` 區塊。
3. 將上述相同的 HTML 卡片代碼貼進去即可！

---

## 💡 本機測試與發布

1. **本機預覽**：修改完成後，您可以直接在瀏覽器中雙擊打開根目錄的 `index.html`，點擊您新加入的商品卡片，確認能順利跳轉到該商品的詳細行銷頁，且圖片、文字、購買按鈕均顯示正確。
2. **部署上線**：在終端機中執行以下 git 指令，將變更推送到 GitHub：
   ```bash
   git add .
   git commit -m "feat: add new product xxx"
   git push origin main
   ```
   推送成功後，約等 1-2 分鐘 GitHub Actions 建置完成，即可在 `https://ashitastore.github.io` 看到最新的商品！
