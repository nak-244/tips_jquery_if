# jQueryでURLを取得してページごとに条件分岐させる記述

「トップページだけに効果を適用したい」などページごとに条件分岐をさせたい場面もあります。  
今回はページURLを取得して条件分岐させる方法を忘備録としてメモ。  

## URLを取得して条件分岐

jQueryやJavaScriptでは「location」を使うことでURLやパスなどの情報を取得することができます。

```java:文例一覧
$(window).on('load',function(){ 
 
  // URLの取得
  var url = location.href
 
  // パスの取得
  var path = location.pathname
 
  // パラメーターの取得
  var param = location.search
 
  // ページ内アンカーの取得
  var anc = location.hash
 
  if (url == "http://example.com/"){
    // URLが http://example.com/ の場合に実行する内容 
  } 
  if (path == "/sample/sample.html"){
    // ドメイン以下のパス名が /sample/sample.html の場合に実行する内容 
  }
  if (param == "?search=123"){
    // パラメーターの値が 123 の場合に実行する内容
  }
  if (anc == "#anchor01"){
    // URLのハッシュ値が #anchor01 の場合に実行する内容 
  } 
});
```

またURLの一部に、指定の文字列が含む場合を条件としたい時は次のように記述します。

```java:文例一覧
$(window).on('load',function(){
　if(document.URL.match(指定する文字列)) {
　    //指定する文字列がURLに含まれる場合に実行する内容
　}
});
```
