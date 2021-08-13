# HTML Handson
## 0. HTMLとは？
HTMLとはハイパーテキストマークアップランゲージの略で、Webページを作成するために開発された言語です。
タグを利用して、見出しや段落、表といった要素を書き並べていくことができます。
今回はHTMLの基本的な構造と書き方、最低限覚えておくといいタグを紹介します！！

## 1. HTMLの雛形
HTMLの形はこれだ！

```
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>タイトル</title>
  <meta name="description" content="サイトの説明を記載します">
  <link rel="icon" href="favicon.ico">
</head>
<body>
  <!-- ここにコンテンツを記載します -->
</body>
</html>
```

これをまずは覚えよう！！ 
困ったらこれをコピペしよね。

### もう少し詳しく
* `<!DOCTYPE html>` … HTMLのバージョンの宣言みたいなもの。詳しく知りたい人は「DOCTYPE」とか「DOCTYPE宣言」とかをググって下さい。
* `<head>` … ページのタイトルとか、検索エンジン向けの説明とかを書く場所。
  * `<link rel="icon" href="?????">` … タブとかに表示されるアイコン画像の指定。例えばGitHubだったら猫の画像が指定されている。
* `<body>` … ここにページの内容を書く。
  * `<!-- ????? -->` … コメントアウト。C言語で言うところの「//」みたいなやつ。

## 2. 覚えておくべきタグ

### h1, h2, h3, etc...
見出しには`<h1>`〜`<h6>`タグを使います。
`<h1>1番目に大きな見出し</h1>`
`<h2>2番目に大きな見出し</h2>`
`<h3>3番目に大きな見出し</h3>`
...
というように使います。

[練習してみよう（英語サイト）](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_headings2)

### p
`<p>`タグは文章の段落を表すときに使います。
`<p>春はあけぼの。</p>`
`<p>夏は、夜。</p>`

[練習してみよう（英語サイト）](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_paragraphs1)

### br
`<br>`で改行します。

```
あいうえお<br>かきくけこ
```
↓
あいうえお
かきくけこ

```
brタグが無かったら
改行されない
```
↓
brタグが無かったら 改行されない

### img, image
画像には`<img>`タグを使います。単独で使って、「どの画像を表示したいか」をsrc属性で指定します。
`<img src="画像名.jpg" alt="説明" width="幅（省略可能）" height="高さ（省略可能）">`

[練習してみよう（英語サイト）](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_images1)

### a
ハイパーリンクを貼るには`<a>`タグを使いましょう。
`<a href="https://cist-lt-group.web.app/">CistLT</a>`
というように、リンクさせたい部分をタグではさみます。

[練習してみよう（英語サイト）](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_links1)

### div
`<div>`〜`</div>`で囲んだ部分をひとまとまりにし、スタイルシートを適用させたいときなどに使います。
`<div>`
 `<p>`春は、あけぼの。`</p>`
`</div>`

### span
`<span>`〜`</span>`も囲んだ部分をひとまとまりにし、スタイルシートを適用させたいときなどに使います。
divとの違いとして、`<div>` はブロック要素(前後に改行がはいる)、` <span>`  はインライン要素(前後に改行が入らない)という違いがあります。

### ol, ul, li
`<ol>`,`<ul>`,`<li>`タグはリストを表します。
`<ol>`…番号付きの箇条書き
`<ul>`…番号のない箇条書き
`<li>`…リストの項目を記述

```
<ul>
  <li>ただの箇条書き</li>
  <li>ただの箇条書き</li>
</ul>

<ol>
  <li>番号が付いた箇条書き</li>
  <li>番号が付いた箇条書き</li>
</ol>
```

[練習してみよう（英語サイト）](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_lists1)

### table td th
`<table>` テーブル(表)をつくる
`<tr>` テーブルの列（row）を作る
`<td>` 表のデータセルを作成する
`<th>` テーブル（表）の見出しセルを作成する

[練習してみよう（英語サイト）](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_tables1)


[CSS Handsonへ進む](https://github.com/CIST-LT-CLUB/HTML_CSS_JavaScript_Handson/blob/master/CSS/css1.md)  
[最初に戻る](https://github.com/CIST-LT-CLUB/HTML_CSS_JavaScript_Handson/blob/master/README.md)  


