# 媽咪精選好物 - 團購頁面系統

## 📁 專案結構

```
mommystartup-shop/
├── index.html          # 前台頁面（給客人看的）
├── admin/
│   └── index.html      # 後台管理介面
├── data/
│   └── products.json   # 資料檔案
├── netlify.toml        # Netlify 設定
└── README.md           # 本說明文件
```

## 🚀 部署到 Netlify

### 方法一：GitHub 連結部署（推薦）

1. **建立 GitHub Repository**
   - 在 GitHub 建立新的 repo（例如：`mommystartup-shop`）
   - 將整個資料夾上傳到 GitHub

2. **連結 Netlify**
   - 登入 [Netlify](https://netlify.com)
   - 點擊 "Add new site" → "Import an existing project"
   - 選擇 GitHub，授權並選擇你的 repo
   - 點擊 "Deploy site"

3. **設定自訂網域（可選）**
   - 在 Netlify 的 "Domain settings" 中設定
   - 可以用子網域如 `shop.mommystartup.com`

### 方法二：直接拖曳部署

1. 將整個 `mommystartup-shop` 資料夾壓縮成 zip
2. 登入 Netlify
3. 直接將 zip 檔拖曳到 Netlify 的部署區域

## 📝 日常更新流程

### 方式 A：使用後台管理（最簡單）

1. 開啟後台管理頁面：`你的網址/admin`
2. 在各區塊編輯內容（Hero、商品、設定）
3. 點擊「匯出資料」→「複製 JSON」
4. 到 GitHub repo，編輯 `data/products.json`
5. 貼上新的 JSON 內容並 commit
6. Netlify 會自動重新部署（約 1-2 分鐘）

### 方式 B：直接編輯 JSON

1. 直接在 GitHub 編輯 `data/products.json`
2. 修改對應欄位
3. Commit 變更
4. 自動部署完成

## 📋 JSON 資料格式說明

```json
{
  "siteInfo": {
    "title": "網站標題",
    "subtitle": "副標題",
    "logo": "Logo 圖片網址"
  },
  "hero": {
    "title": "最新團購標題",
    "image": "主視覺圖片網址",
    "description": "團購說明文字",
    "ctaText": "按鈕文字",
    "ctaLink": "按鈕連結",
    "endDate": "結團日期 YYYY-MM-DD"
  },
  "regularProducts": [
    {
      "id": 1,
      "name": "商品名稱",
      "image": "商品圖片網址",
      "description": "商品說明",
      "link": "購買連結",
      "badge": "標籤（熱銷/新品/常態/空白）"
    }
  ],
  "social": {
    "facebook": "FB 連結",
    "instagram": "IG 連結",
    "line": "LINE 連結"
  },
  "footer": {
    "copyright": "版權聲明"
  }
}
```

## 🖼️ 圖片上傳建議

由於這是靜態網站，圖片需要先上傳到其他地方取得網址：

1. **繼續使用 WordPress 媒體庫**
   - 在原本的 WP 後台上傳圖片
   - 複製圖片網址使用

2. **使用免費圖床**
   - [Imgur](https://imgur.com)
   - [ImgBB](https://imgbb.com)

3. **使用 GitHub**
   - 在 repo 中建立 `images` 資料夾
   - 上傳圖片後使用 raw 連結

## 🔄 進階：自動化更新

如果想要更方便的更新流程，可以考慮：

1. **使用 Netlify CMS**（需要額外設定）
2. **串接 Headless CMS**（如 Contentful, Strapi）
3. **使用 Google Sheets 作為資料來源**（需要額外開發）

## ❓ 常見問題

**Q: 更新後多久會生效？**
A: GitHub commit 後約 1-2 分鐘 Netlify 會自動部署完成。

**Q: 圖片不顯示怎麼辦？**
A: 確認圖片網址是否正確，且允許跨網域存取（CORS）。

**Q: 可以在後台直接發布嗎？**
A: 目前後台是純前端，資料存在瀏覽器中。需要手動複製 JSON 到 GitHub 才會更新線上版本。

## 📞 技術支援

如有問題，請聯繫開發人員協助處理。
