# data2img
這個程式可以用來把資料轉成圖片，再轉回資料。我想這樣轉換是因為我想找個更簡便的方法來傳送關卡代碼

順便來做把聲音轉成圖片，因為facebook不支援語音留言，但是支援圖片留言。疑，等等，facebook好像支援影片留言，這表示我不需要把聲音轉成圖片嗎？Oh no！

展示一下我做的結果： [data2img.html](data2img.html)

## 運作原理

我把資料切成每 16 個 bit (2 位元組) 一塊，每 16 個 bit 就轉成 8x8 的圖案，然後再把它們拼起來

為什麼是 8x8 的圖案呢？因為 jpg 壓縮是以 8x8 為單位，這樣萬一我的編碼被 Facebook 破壞了，也只會破壞那個 8x8 區塊的內容

有個網站說，Facebook 可以支援 960x720 的圖片，而不會改變解析度。好吧，其實 [Facebook 自己就有說]()。所以我就用 960x720 的圖片來儲存資料。960x720 的圖片共有 960x720/(8x8)=10800 個 8x8 區塊，所以共可以儲存 10800 x 2位元組 = 21600 位元組，約等於 21 KB

[Facebook 自己就有說]: https://www.facebook.com/help/266520536764594/
