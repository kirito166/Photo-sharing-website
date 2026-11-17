# AGENTS.md - 照片展示網站開發與擴充規範

## 1. 專案目的 (Project Purpose)
本專案為「LUMEN 線上照片展示與攝影原作集網站」，旨在以沈浸式的深色藝廊風格（Dark Gallery Aesthetic）呈現高品質的攝影作品。
本規範旨在讓 AI 協作者在**新增照片**、**擴充專案內頁**或**調整全站視覺**時，能維持完全一致的質感、不規則網格排版與響應式體驗。

## 2. 目錄與檔案命名規則 (Directory & Naming Conventions)
- `index.html`：首頁，採用不對稱網格（Masonry Grid）展示精選照片。
- `style.css`：全站唯一的 CSS 樣式表。**禁止在單一 HTML 檔案內寫 `<style>` 行內樣式**。
- `assets/photos/`：存放所有展示的照片。
  - 命名格式：`photo-編號.jpg`（如：`photo-01.jpg`）。
- `galleries/`：存放主題展覽或專案詳細內頁。
  - 命名格式：`gallery-編號-主題英文.html`（如：`gallery-01-neon-night.html`）。

## 3. 網頁整體風格與設計規範 (UI/UX & Styling)
- **視覺風格**：當代極簡、深色調沉浸式藝廊風，強調照片色彩，運用大量「留白（Space）」與極細邊框線（Border）。
- **色彩系統**（定義於 `style.css` 的 `:root` 變數）：
  - 背景主色：`#0e1111`（深煤灰色）
  - 區塊與卡片：`#161a1a`（帶有極細微的暗邊框 `#242929`）
  - 主要文字（標題）：`#f8fafc`（襯線體 Serif 尤佳）
  - 次要文字（圖說、標籤）：`#8a9a9a`（無襯線體 Sans-serif）
  - 強調色（點綴）：`#d4af37`（暗金色）
- **版面結構**：
  - 頂部導覽（Header）：固定於上方（Sticky），包含左側品牌 LOGO 與右側展覽資訊。
  - 核心排版：採用不對稱的瀑布流網格（Masonry Grid，使用 CSS `column-count`），讓直式與橫式照片錯落有致。
  - 響應式設計：在行動裝置上自動轉為單欄（Single Column）垂直捲動，保留最舒適的看圖體驗。

## 4. 頁面結構標準 (Page Structure)

### A. 首頁 (`index.html`) 照片牆結構
每張照片元件必須包含以下標籤：
```html
<div class="photo-item">
  <img src="assets/photos/photo-01.jpg" alt="作品 01" loading="lazy">
  <div class="photo-caption">
    <span><strong class="caption-num">01 /</strong> Urban Night &amp; Neon</span>
    <span>2026</span>
  </div>
</div>