# 連結 index.html 與 secondpage.html 計劃

## 當前狀態分析

### index.html (主頁)
- 導航欄包含三個內部錨點連結：
  1. `#features` → "功能介紹"
  2. `#workflow` → "使用流程" 
  3. `#team` → "團隊介紹"
- 右上角有"立即開始"按鈕（目前無連結功能）
- 主要內容區有兩個行動按鈕："免費開始使用"和"查看演示"

### secondpage.html (收支明細頁面)
- 已包含返回 index.html 的連結：
  - Logo 連結到 `index.html`
  - "回首頁"按鈕連結到 `index.html`
- 頁面標題為"收支明細 - 日常收支记账"
- 顯示財務數據和分類明細

## 建議的連結方案

### 方案一：導航欄新增連結（推薦）
在現有導航欄中添加第四個連結，指向 `secondpage.html`：

**修改位置：** `index.html` 第 70-74 行
```html
<nav class="hidden md:flex items-center gap-10">
  <a class="text-sm font-semibold hover:text-primary transition-colors" href="#features">功能介紹</a>
  <a class="text-sm font-semibold hover:text-primary transition-colors" href="#workflow">使用流程</a>
  <a class="text-sm font-semibold hover:text-primary transition-colors" href="#team">團隊介紹</a>
  <a class="text-sm font-semibold hover:text-primary transition-colors" href="secondpage.html">收支明細</a>
</nav>
```

### 方案二：更新"立即開始"按鈕
將右上角的"立即開始"按鈕改為連結到 `secondpage.html`：

**修改位置：** `index.html` 第 76-78 行
```html
<a href="secondpage.html" class="rounded-full px-6 py-2 text-sm font-bold text-white hover:bg-primary/90 transition-all btn-3d btn-3d-primary tracking-wide">
  立即開始
</a>
```

### 方案三：主行動按鈕新增連結
在主要內容區的行動按鈕中新增一個連結：

**修改位置：** `index.html` 第 97-104 行
```html
<div class="flex flex-wrap gap-4">
  <a href="secondpage.html" class="rounded-xl px-8 py-4 text-lg font-bold text-white shadow-lg shadow-primary/20 hover:scale-105 transition-transform btn-3d btn-3d-primary tracking-wide">
    免費開始使用
  </a>
  <button class="rounded-xl border border-primary/20 px-8 py-4 text-lg font-bold text-primary hover:bg-primary/10 transition-colors btn-3d btn-3d-secondary tracking-wide">
    查看演示
  </button>
</div>
```

## 推薦的完整實施方案

### 主要修改：
1. **導航欄新增"收支明細"連結** - 讓用戶可以從任何頁面訪問財務明細
2. **"立即開始"按鈕連結到 secondpage.html** - 提供明確的行動呼籲
3. **保持 secondpage.html 的現有返回連結** - 已正確設置

### 具體代碼修改：

#### 1. 導航欄修改（index.html 第 73 行後添加）：
```html
<a class="text-sm font-semibold hover:text-primary transition-colors" href="secondpage.html">收支明細</a>
```

#### 2. "立即開始"按鈕修改（index.html 第 76-78 行）：
將 `<button>` 改為 `<a>` 標籤：
```html
<a href="secondpage.html" class="rounded-full px-6 py-2 text-sm font-bold text-white hover:bg-primary/90 transition-all btn-3d btn-3d-primary tracking-wide">
  立即開始
</a>
```

## 視覺一致性檢查
- 導航連結使用相同的樣式類別：`text-sm font-semibold hover:text-primary transition-colors`
- 按鈕使用相同的 3D 效果樣式：`btn-3d btn-3d-primary`
- 顏色方案與現有設計保持一致（primary color: #1e40af）

## 測試計劃
1. 點擊 index.html 中的"收支明細"連結應導航到 secondpage.html
2. 點擊 index.html 中的"立即開始"按鈕應導航到 secondpage.html
3. 從 secondpage.html 點擊"回首頁"按鈕應返回 index.html
4. 從 secondpage.html 點擊 Logo 應返回 index.html
5. 確保所有連結在移動設備和桌面設備上正常工作

## 檔案結構
```
moneynote/
├── index.html          (主頁面)
├── secondpage.html     (收支明細頁面)
└── plans/
    └── linking_plan.md (本計劃文件)
```

## 下一步行動
請確認您希望實施哪個方案，或提出修改建議。確認後，我可以切換到 Code 模式進行實施。