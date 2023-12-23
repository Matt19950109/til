# 7-1 位置情報
## 位置情報の取得方法
- navigatorオブジェクト → geolocationオブジェクト → getCurrentPositionメソッドを使用
  
      navigator.geolocation.getCurrentPosition(success, fail);

# 7-2 Web API
- 何らかの機能をほかの開発が利用できるように公開する

### 取得した要素の中にHTMLを挿入する
      $('セレクタ').append(挿入するHTML)

例）天気予報の情報を取得
