# Parserライブラリについて
Parserライブラリは、スクレイピング処理に特化したライブラリ。HTML形式で記述されたページ全体の膨大なテキストデータを基礎的な関数やメソッドのみで抽出すると、とても複雑な記述になってしまうため、Parserライブラリを使う。Parserライブラリによって、取得したHTML形式のWebページのデータを簡単に処理することができる。
# Parserライブラリのインストール
①エディタ左側の「ライブラリ」の「＋」ボタンをクリック<br>
②ポップアップの「スクリプトID」欄にParserライブラリのIDを入力し「検索」をクリック<br>
③Parserライブラリであることを確認し、「追加」ボタンをクリック
# Parserライブラリの使い方
```Javascript
Parser.data(text).from(startText).to(endText).build()//条件に合う文字列の最初の一つを抽出

Parser.data(text).from(startText).to(endText).iterate()//条件に合う文字列を回数分抽出して配列に格納
```
text：処理対象の文字列<br>
startText：抽出開始位置となる文字列<br>
endText：抽出終了位置となる文字列
