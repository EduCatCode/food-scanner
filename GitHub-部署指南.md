# GitHub Pages 部署指南

## 問題解決方案

你遇到的空白頁面問題已經修正！問題原因是 GitHub Pages 預設使用 Jekyll 處理網站，會干擾 HTML 的正常顯示。

已添加以下修正：
- ✅ 創建了 `index.html`（GitHub Pages 的預設首頁）
- ✅ 添加了 `.nojekyll` 檔案（停用 Jekyll 處理）

## 正確部署步驟

### 方法一：使用 GitHub 網頁介面（最簡單）

#### 步驟 1：建立倉庫
1. 登入 GitHub (https://github.com)
2. 點擊右上角的 `+` → `New repository`
3. 填寫倉庫名稱，例如：`food-scanner`
4. 選擇 `Public`（公開）
5. 點擊 `Create repository`

#### 步驟 2：上傳檔案
1. 在新倉庫頁面，點擊 `uploading an existing file`
2. 將以下 2 個檔案拖放到上傳區：
   - ✅ `index.html`
   - ✅ `.nojekyll`
3. 在底部填寫提交訊息（例如：`初始提交`）
4. 點擊 `Commit changes`

**重要：請確保上傳 `.nojekyll` 檔案！** 這是修正空白頁面的關鍵。

#### 步驟 3：啟用 GitHub Pages
1. 點擊倉庫的 `Settings`（設定）
2. 在左側選單找到 `Pages`
3. 在 `Source` 下方選擇：
   - Branch: `main`
   - Folder: `/ (root)`
4. 點擊 `Save`
5. 等待 1-2 分鐘，頁面會顯示網址：
   ```
   Your site is live at https://你的用戶名.github.io/food-scanner/
   ```

#### 步驟 4：測試
1. 點擊顯示的網址
2. 用手機瀏覽器開啟
3. 應該可以看到完整的應用程式介面（紫色漸層背景、掃描按鈕等）

---

### 方法二：使用 Git 命令列（進階）

如果你熟悉 Git：

```bash
# 1. 在本地資料夾初始化 Git
cd "C:\Users\User\Desktop\小作品"
git init

# 2. 添加檔案
git add index.html .nojekyll

# 3. 提交
git commit -m "初始提交：食物掃描器應用"

# 4. 連接到 GitHub 倉庫（替換成你的倉庫網址）
git remote add origin https://github.com/你的用戶名/food-scanner.git

# 5. 推送
git branch -M main
git push -u origin main
```

然後按照方法一的「步驟 3」啟用 GitHub Pages。

---

## 檔案清單

請確保上傳以下檔案到 GitHub：

| 檔案名稱 | 說明 | 必要性 |
|---------|------|--------|
| `index.html` | 主應用程式檔案 | ✅ 必要 |
| `.nojekyll` | 停用 Jekyll 處理（修正空白頁面） | ✅ 必要 |
| `README.md` | 說明文件（可選） | ⭕ 可選 |

---

## 常見問題排查

### Q1: 頁面還是空白？
**解決方案：**
1. 確認已上傳 `.nojekyll` 檔案
2. 在 GitHub 倉庫檢查檔案列表，確認 `.nojekyll` 存在
3. 等待 5-10 分鐘讓 GitHub Pages 重新構建
4. 強制重新整理瀏覽器（Ctrl+Shift+R 或 Cmd+Shift+R）
5. 清除瀏覽器快取

### Q2: 看不到 `.nojekyll` 檔案？
**解決方案：**
- Windows 預設隱藏以 `.` 開頭的檔案
- 在檔案總管開啟「顯示隱藏的檔案」選項
- 或直接在 GitHub 網頁上創建：
  1. 點擊 `Add file` → `Create new file`
  2. 檔案名稱輸入 `.nojekyll`
  3. 內容留空
  4. 點擊 `Commit new file`

### Q3: 頁面顯示 404 錯誤？
**解決方案：**
1. 確認 GitHub Pages 設定中選擇了正確的分支（main）
2. 確認檔案名稱是 `index.html`（不是 `food-scanner.html`）
3. 等待幾分鐘讓部署完成

### Q4: 相機權限無法使用？
**解決方案：**
- GitHub Pages 自動提供 HTTPS，所以相機應該可以正常使用
- 確認瀏覽器彈出權限請求時點擊「允許」
- 如果還是不行，檢查手機設定中是否允許瀏覽器使用相機

---

## 驗證清單

部署前請確認：
- [ ] 已建立 GitHub 倉庫
- [ ] 已上傳 `index.html`
- [ ] 已上傳 `.nojekyll`（重要！）
- [ ] 已在 Settings → Pages 啟用 GitHub Pages
- [ ] 已等待 1-2 分鐘讓部署完成
- [ ] 在手機瀏覽器測試網址

完成這些步驟後，應該可以看到完整的應用程式，不再是空白頁面！

---

## 部署成功後的樣子

你應該看到：
- 🟣 紫色漸層背景
- 📱 白色卡片包含「食物品質掃描器」標題
- 🔘 藍紫色的「開始掃描條碼」按鈕
- 📝 手動輸入營養成分的表單

如果看到這些，恭喜部署成功！

---

## 需要協助？

如果仍有問題：
1. 檢查瀏覽器主控台（F12）是否有錯誤訊息
2. 確認 GitHub Pages 設定頁面顯示綠色的 "Your site is published"
3. 嘗試使用無痕模式開啟網址（排除快取問題）
