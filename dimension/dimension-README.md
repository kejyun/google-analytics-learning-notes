# 自訂維度

自定維度可以針對自己客製化的設定，設定要額外傳送給 GA 的相關資訊，讓你在報表中比較好去進行資料分析


## 設定自定維度

###  使用 `ga()` 函式設定

```javascript
var dimensionValue = 'SOME_DIMENSION_VALUE';
ga('set', 'dimension1', dimensionValue);
ga('set', 'dimension2', dimensionValue);
ga('set', 'dimension3', dimensionValue);
```


###  使用 `gtag()` 函式設定

在使用官方說明說只需要將 `dimension1` 、 `dimension2` 之類的資料設定到 `custom_map` 就好，但經測試，目前需要在外層也設定 `dimension1` 之類的資料設定，這樣資料才有辦法正確的送給 GA

```javascript
// Maps 'dimension2' to 'age'.
gtag('config', 'UA-XXXXXXXXXX', {
    'dimension1' : 'age',
    'custom_map': {
        'dimension1': 'age'
    }
});
```



## 參考資料
* [自訂維度和指標 - Analytics (分析)說明](https://support.google.com/analytics/answer/2709828?hl=zh-Hant)
* [如何知道網站各分類的成效？用GA自訂維度、自訂報表暸解各項指標！ - 翔說什麼](https://shian.tw/article/1696)
* [javascript - gtag not sending custom dimensions for events - Stack Overflow](https://stackoverflow.com/questions/48120557/gtag-not-sending-custom-dimensions-for-events/48189202#48189202)
* [看懂GA報表前，你不可不知道的Google Analytics維度與指標 | awoo](https://www.awoo.com.tw/blog/ga-dimensions-metrics/)
* [GA自訂維度的應用 分類之下的文章成效 - Google - Let's Write](https://letswrite.tw/ga-custom-dimension/)
