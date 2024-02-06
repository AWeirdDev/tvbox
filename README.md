<img alt="Taiwan Flag"
     src="https://github.com/AWeirdScratcher/tvbox/assets/90096971/1995d468-fee7-44c3-8bfb-298884d559eb"
     align="right"
     width="160" />

# 🍕 TVBox 數據源

> Last updated: 2024-02-06
> 
> <a href="https://github.com/o0HalfLife0o/TVBoxOSC/releases/tag/20240130-1747" target="_blank">🐣 TVBox</a> • [@awdev](https://github.com/AWeirdScratcher)

嘿，歡迎使用 TVBox 數據源 for Taiwan！

這個專案主要使用 GitHub 和自己的伺服器，複製 JSON 或 TXT 連結即可使用此數據源。

數據源：

```
https://raw.githubusercontent.com/AWeirdScratcher/tvbox/main/sources.json
```

直播連結（可選）：

```
https://flying-sponge-vocal.ngrok-free.app/tv-tw.txt
```

## 直播節目

收錄了以下節目：

- 新聞台
  - TVBS新聞台
  - 三立新聞台
  - EBC東森新聞台
  - EBC東森財經新聞
  - 台視新聞台
  - CTV中視新聞台
  - 寰宇新聞台
- 音樂頻道
  - Lofi-Radio
  - Synthwave-Radio
 
節目直播來源為 YouTube，且已經經過處理可供隨時播放。

參見「致開發者」以了解更多。

## 致開發者 <kbd>\< /></kbd>

如果需要自訂 `lives`，可以使用下列 config：

```jsonc
// ...
  "lives": [
          {
              "name": "Live",
              "url": "https://flying-sponge-vocal.ngrok-free.app/tv-tw.txt", // YouTube 直播自動更新 API
              "type": 0,
              "logo": "https://raw.githubusercontent.com/AWeirdScratcher/tvbox/main/logos/{name}.png",
              "ua": "Bot TvBox", // User-Agent
              "epg": "https://flying-sponge-vocal.ngrok-free.app/epg?channel={name}&date={date}" // 節目表
          }
  ],
// ...
```

### tv-tw.txt 是如何運作的？ <kbd>\< /></kbd>

YouTube 的直播影片檔每經過一段時間便會自動刪除 (auto expires)，因此伺服器每經過 5 分鐘便會重新生成一個連結，並產生新的 `tv-tw.txt` 檔。

詳情請參見 [yt-dlp](https://pypi.org/project/yt-dlp)。
