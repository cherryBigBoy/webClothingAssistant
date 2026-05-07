# 拾衣記 - AI 虛擬換衣平台

> AI 在地時尚導購平台，具備「推薦」與「以圖搜圖」雙模式，深度整合電腦視覺與生成式 AI 技術。

## 功能展示

本項目為系統展示界面的前端復刻，完整還原了交互流程與視覺設計，並使用 AI 生成的模擬圖片。

### 推薦模式

上傳個人照片 → AI 自動生成 3 套個人化穿搭 → 原圖/換衣效果對比展示

- 照片上傳（點擊或拖拽），預設展示示例人物
- 性別選擇（男生/女生）
- 6 種穿搭風格（街頭風、商務正式、日系簡約、韓系休閒、復古文青、運動風）
- AI 處理進度展示（4 步級聯式決策引擎流程）
- 穿搭卡片選擇與對比查看

### 搜圖模式

瀏覽服裝庫 → 選擇心儀單品 → AI 生成試穿效果

- 8 件示例服裝（工裝外套、針織衫、西裝外套等）
- 即時試穿生成模擬

### 線上店鋪搜尋

AI 穿搭推薦完成後，可搜尋線上精選店鋪，即看即買

- 店鋪搜尋（關鍵字即時篩選）
- 分類篩選（街頭潮流/極簡風格/商務正式/復古古著/運動機能）
- 店鋪卡片（封面圖、簡介、評分、平台標籤）
- 前往店鋪 / 收藏按鈕

## 技術特點

| 項目 | 說明 |
|------|------|
| 技術棧 | 純 HTML + CSS + Vanilla JS |
| 樣式方案 | CSS 變量 + 自定義屬性，無第三方 CSS 框架 |
| 字體 | Noto Sans TC（正文）+ Playfair Display（品牌） |
| 交互 | 事件委託 + 狀態管理，無框架依賴 |
| 響應式 | 支援桌面端 / 平板 / 手機 |
| 依賴 | 僅 Google Fonts（CDN） |
| 圖片 | 16 張 AI 生成模擬圖片（`images/` 目錄） |

## 快速開始

用瀏覽器直接打開 `index.html` 即可運行，無需構建步驟或安裝任何依賴。

```bash
# macOS
open index.html

# 或直接拖入瀏覽器
```

## 目錄結構

```
webClothingAssistant/
├── index.html              # 主頁面（單文件，包含全部 HTML / CSS / JS）
├── README.md               # 本文件
├── .gitignore              # Git 忽略配置
└── images/                 # AI 生成的模擬圖片
    ├── outfit_1.jpg            # 穿搭結果 1（街頭風 - 炸彈外套）
    ├── outfit_2.jpg            # 穿搭結果 2（街頭風 - 工裝夾克）
    ├── outfit_3.jpg            # 穿搭結果 3（街頭風 - 牛仔外套）
    ├── sample_person.jpg       # 示例人物照片（上傳區預設）
    ├── tryon_result.jpg        # AI 換衣結果對比圖
    ├── clothing_navy_workwear.jpg   # 商品圖：深藍工裝外套
    ├── clothing_beige_knit.jpg      # 商品圖：米白針織衫
    ├── clothing_khaki_chinos.jpg    # 商品圖：卡其休閒褲
    ├── clothing_black_blazer.jpg    # 商品圖：黑色西裝外套
    ├── clothing_grey_hoodie.jpg     # 商品圖：灰色運動衛衣
    ├── clothing_denim_shirt.jpg     # 商品圖：牛仔襯衫
    ├── clothing_white_polo.jpg      # 商品圖：白色Polo衫
    ├── clothing_army_jacket.jpg     # 商品圖：軍綠夾克
    ├── store_1.jpg                  # 店鋪封面：拾衣記精品
    ├── store_2.jpg                  # 店鋪封面：簡著工作室
    └── store_3.jpg                  # 店鋪封面：東岸衣櫥
```

## 設計規範

### 配色體系

```
背景色    #0a0a0a    深黑
卡片色    #141414    暗灰
金色強調  #D4A574    暖金
藍色次要  #4A90D9    科技藍
成功色    #4CAF50    綠色
文字主色  #FFFFFF    白色
```

### 頁面流程

```
首頁
├── 推薦模式 → 上傳照片 → AI 處理 → 結果展示 → 線上店鋪
└── 搜圖模式 → 選擇服裝 → AI 試穿 → 結果展示 → 線上店鋪
```

## 備註

本項目為 UI 交互原型復刻，AI 處理流程使用定時器模擬。實際部署時需對接後端 API：

- **特徵辨識**：VGG-16 / MediaPipe / SMPL-Anthropometry
- **服裝推薦**：級聯式決策引擎 + HSL 色彩空間 + 高斯懲罰函數
- **虛擬換衣**：Gemini 生成模型
- **圖像檢索**：CLIP + U2-Net
- **線上店鋪**：串接電商平台 API（蝦皮 / Momo / 樂天等）

## License

MIT
