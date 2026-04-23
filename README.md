# Utrust Online Page

靜態直播入口頁，適合部署在 GitHub Pages。

## 功能

- 密碼門檻（前端 SHA-256 比對）
- YouTube 直播嵌入
- Slido 互動嵌入
- 右下角品牌遮罩（`logo遮罩.png`）

## 檔案

- `index.html`：主頁面
- `logo遮罩.png`：播放器右下角遮罩圖

## 快速使用

1. 修改 `index.html` 內的 YouTube 與 Slido 連結。
2. 產生新密碼雜湊，更新 `ACCESS_HASH`。
3. 將專案推到 GitHub，啟用 GitHub Pages（`main` 分支）。

## 產生密碼雜湊

```bash
node -e "console.log(require('crypto').createHash('sha256').update('新密碼','utf8').digest('hex'))"
```

將輸出值貼到 `index.html` 的 `ACCESS_HASH`。

## 注意事項

- 此方案為低成本門檻，不是完整 DRM 或後台授權。
- 直播連結仍可能被技術使用者以開發者工具取得。
- 上線前建議先以手機與電腦實測一次。
