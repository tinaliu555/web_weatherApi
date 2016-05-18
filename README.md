# wp2016s_assign5
作業說明：https://goo.gl/zP0AOq


### 要怎麼拿到 Yahoo 資料？
1. 以下將說明怎麼閱讀這個網頁，請打開連結 https://developer.yahoo.com/weather/
2. 可以直接看到他的第一個 example `Forecast for Nome, AK`
3. (這項看不懂可略)YQL Query 那個欄位是指說，如果用 yql 的方式，要怎麼撰寫他的 query
4. 仔細看 yql 欄位裡 `where text="nome, ak"` 這裡就是在指定地區。你可以試著把 `nome, ak` 換成 `Taipei City` ，然後點選 Test。
5. 閱讀 Response 區域裡面的資料，找看看你要的資訊放在哪個節點裡。
6. 複製下方的 endpoint 貼到網址列打開，這就是一個標準的 json 檔案了，裡面放著 `Taipei City` 的天氣資料。
7. 對他 getJSON 就可以在 callback function 裡面拿到資料。

```javascript
$.getJSON("http://your-endpointURL",function(data){
	console.log (data) ; // 可以比較方便你找到你要的資料在這個物件的哪個位置

	// 例如
	var currentTemperature = data.query.results.channel.item.condition.temp  ; // 就可以找到現在溫度
}
```
8. (自己研究文件) https://developer.yahoo.com/weather/documentation.html 。例如：裡面可以找到某個設定，直接指定溫度單位


### Skycon使用方式:
http://darkskyapp.github.io/skycons/
