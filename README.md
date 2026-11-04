# Roon OS 本機管理頁 繁體中文化

把 Roon OS（ROCK / Nucleus）的本機管理網頁翻成繁體中文（台灣用語）。

## 安裝

1. 在瀏覽器裝好 [Tampermonkey](https://www.tampermonkey.net/)。
2. Chrome / Edge：到擴充功能頁面，開啟「開發人員模式」，並在 Tampermonkey 的詳細資料中開啟「允許使用者指令碼」。
3. 點這個連結：**[安裝 roon-zh-tw.user.js](https://raw.githubusercontent.com/crytropy/Roon-zh-tw/main/roon-zh-tw.user.js)**
4. Tampermonkey 會跳出安裝畫面，按「安裝」。
5. 打開 Roon 主機的網頁就會是中文。

之後這個 Repo 有更新，Tampermonkey 會自動抓新版。

## 設定你的主機位址

腳本預設只在 `http://192.168.3.10` 執行。你的主機位址不一樣的話：

1. 點 Tampermonkey 圖示 →「管理面板」→ 點這個腳本。
2. 切到「設定」分頁。
3. 在「使用者比對（User matches）」加上你的位址，例如 `http://192.168.1.50/*`。
4. 按「儲存」。

想同時用 Tailscale 位址開，就再加一行，例如 `http://100.x.x.x/*`。

> 不要直接改腳本裡的 `@match`。腳本自動更新時，你改的地方會被蓋掉。「使用者比對」的設定則會保留。

## 怎麼改翻譯

腳本裡的 `DICT` 就是對照表，左邊英文、右邊中文。

- 英文要和網頁上的一模一樣（前後空白不用管）。
- 有 `{}` 的是填空句，`{}` 代表會變動的部分（數字、名稱）。
- 中文順序和英文不同時，用 `{1}`、`{2}` 指定第幾個。
- 改完要推上 GitHub 的話，記得把腳本開頭的 `@version` 加一號（例如 `1.0.1` → `1.0.2`），Tampermonkey 才會發現有新版。

## 刻意不翻的

- Roon、Roon Server、RoonOS、Tailscale、ARC、SMB、DNS、HTTPS 等名稱
- 時區清單、IP、版本號、序號
- 要貼給 Roon 技術支援的英文訊息（保持英文對方才看得懂）

## 注意

- 翻譯是從 RoonOS 3.0（build 287）的網頁程式抓出來的。Roon 更新網頁後，新加的字可能會變回英文，到時再補進 `DICT` 就好。
- 這個腳本只改「畫面上的字」，不會動到任何設定。
