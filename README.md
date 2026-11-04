# Roon OS 本機管理頁 繁體中文化

把 Roon OS（ROCK / Nucleus）的本機管理網頁翻成繁體中文（台灣用語）。

## 安裝

1. 在瀏覽器裝好 [Tampermonkey](https://www.tampermonkey.net/)。
2. Chrome / Edge：到擴充功能頁面，開啟「開發人員模式」，並在 Tampermonkey 的詳細資料中開啟「允許使用者指令碼」。
3. 點 Tampermonkey 圖示 →「新增腳本」。
4. 把編輯器裡的內容全部刪掉，貼上 `roon-zh-tw.user.js` 的全部內容。
5. 按 `Ctrl + S` 儲存。
6. 打開 http://192.168.3.10 就會是中文。

## 主機 IP 換了怎麼辦

改腳本最上面這一行：

```
// @match        http://192.168.3.10/*
```

想同時用 Tailscale 位址開，就再多加一行 `@match`，例如：

```
// @match        http://100.x.x.x/*
```

## 怎麼改翻譯

腳本裡的 `DICT` 就是對照表，左邊英文、右邊中文。

- 英文要和網頁上的一模一樣（前後空白不用管）。
- 有 `{}` 的是填空句，`{}` 代表會變動的部分（數字、名稱）。
- 中文順序和英文不同時，用 `{1}`、`{2}` 指定第幾個。

## 刻意不翻的

- Roon、Roon Server、RoonOS、Tailscale、ARC、SMB、DNS、HTTPS 等名稱
- 時區清單、IP、版本號、序號
- 要貼給 Roon 技術支援的英文訊息（保持英文對方才看得懂）

## 注意

- 翻譯是從 RoonOS 3.0（build 287）的網頁程式抓出來的。Roon 更新網頁後，新加的字可能會變回英文，到時再補進 `DICT` 就好。
- 這個腳本只改「畫面上的字」，不會動到任何設定。
