# JavaScript

## 目標

基礎的な知識を身につける  
信頼できる情報を探せるようになる  
信頼できるサイトを見つけておく(これは目標ではないミニ課題)

JavaScript について、自分で調べて学習するための基礎知識を身につけられるようになろう！

リファレンスをひけば良い部分は覚えない！

※ブラウザは chrome を想定

## JavaScript とは

基本的にはブラウザ上の処理を行う  
Web アプリケーションにはほぼ必須  
動的、静的という表現では動的になる。  
ブラウザでは画像スライドショーとか click されたら変わるとか...etc  
最近では色んな所で使われている  
サーバーサイド (Node.js)  
npm, gulp などの開発ツール (Node.js)  
デスクトップアプリ (Electron)  
スマホアプリ (Windows Phone, React Native, Titanium 等)  
今回は基本的にブラウザ上で動作する JS を対象にします。

## print デバッグ

console.log()  
オブジェクトの中身まで見れて便利  
本講義では基本的にこれを使う

ブラウザで右クリック検証 console で

```JS
console.log('富岡義勇');
```

console に富岡義勇が表示される

```JS
console.log(2+1);
```

console に 3 が表示される

## HTML に直接記述しよう

つくった html ファイルの</body>の上に

```HTML
<script>console.log('壱の型');</script>
```

console を見て壱の型を確認

## JavaScript ファイルを HTML に読み込ませる

html ファイルと同じところに script.js をつくる  
-test.html  
-script.js  
.js という拡張子が JavaScript のファイル

html の中

```HTML
<script src="script.js"></script>
<script>console.log('壱の型');</script>
```

script.js の中

```JS
console.log('凪')
```

このように JavaScript は外部ファイルに読み込ませるのが一般的

## アラートを出してみよう

```HTML
<html>
<head>
<title>TAG index Webサイト</title>

<script type="text/javascript">

function disp(){

	window.alert('アラートの表示');

}

</script>

</head>
<body>

<p><input type="button" value="警告ダイアログ" onClick="disp()"></p>

</body>
</html>

```

## 簡単な DOM 操作

HTML ドキュメントの中身を操作しよう  
ブラウザの API を知ろう

DOM とは？  
Document Object Model の略  
HTML 文書を JS で操作する API を定めたもの  
API: メソッドや定数といったインターフェイス

DOM 操作大変だから React.js とか jQuery 等ライブラリを使うと DOM を直接操作する機会は減るが、知っておく必要はある

DOM API をひとつだけ紹介!

document.getElementById('id')  
ブラウザの画面の部分を document オブジェクトという

html ファイルの p タグに id を追加

```HTML
<p id="choice">Gong cha</p>
```

script.js に以下を追加

```JS
document.getElementById('choice').textContent = new Date();
```

ブラウザをリロード！
Gong cha が時間に変わっている！
これが DOM 操作的な感じ

### 毎秒更新して時計を作ろう

```JS
function showClock1() {
   var nowTime = new Date();
   var nowHour = nowTime.getHours();
   var nowMin  = nowTime.getMinutes();
   var nowSec  = nowTime.getSeconds();
   var msg = "現在時刻は、" + nowHour + ":" + nowMin + ":" + nowSec + " です。";
   document.getElementById("RealtimeClockArea").innerHTML = msg;
}
setInterval('showClock1()',1000);//1秒停止

```

```HTML
<p id="RealtimeClockArea2">※ここに時計(2桁固定版)が表示されます。</p>
```

## コメント

```JS
// 一行コメント
```

```JS
/*
複数行コメント
*/
```

## 変数

const  
再宣言、再代入が不可

let  
再宣言は不可、再代入は可能

var  
再宣言・再代入が可能

型がなく Java や C と違う

古い環境では var しか動かないとかあるげど  
最近の環境なら let, const を使おう  
最近とは、Babel, TypeScript が使えるとか ES6 とか  
const の使用に固執し、let を使用してください。  
※宣言はハマりやすいので注意

html ファイルに

```JS
const a = 'ぴちゃい'
console.log(a)
```

ぴちゃいって console にでるはず

## if else

C や Java と同じ

```JS
if(){

}else if(){

}else{

}
```

html ファイルの中

```JS
const num = Math.floor(Math.random()*5)
let mes;
if( 4 === num){
    mes = '4'
}else if(3 === num){
    mes = '3'
}
else {
  mes = 'ざこ'
}
console.log(mes)
```

console で結果を確認  
4 なら 4 3 なら 3 それ以外はざこ

switch 文もある

## for

html ファイルの中

```JS
for(var i=1;i<=10;i++){
  console.log(i);
}
```

console で結果を確認  
1~10 まででるよ

while 文もある

## 配列

```JS
const t = [1, -1, 3]

t.push(5)

console.log(t.length) // 4 is printed
console.log(t[1])     // -1 is printed

t.forEach(value => {
  console.log(value)  // numbers 1, -1, 3, 5 are printed, each to own line
})
```

配列の内容が const として定義されている場合でも、配列の内容を変更できることです。配列はオブジェクトであるため、変数は常に同じオブジェクトを指します。ただし、新しい項目が追加されると、配列の内容は変化します。

配列の項目を反復処理する 1 つの方法は、例にあるように forEach を使用することです。forEach は、矢印構文をパラメーターとして使用して定義された関数を受け取ります。

```JS
value => {
  console.log(value)
}
```

### map

配列に対して定義されている便利なメソッドがたくさんあります。map メソッドを使用する短い例を見てみましょう。

```JS
const t = [1, 2, 3]

const m1 = t.map(value => value * 2)
console.log(m1)   // [2, 4, 6] is printed
```

古い配列に基づいて、map は新しい配列を作成します。パラメーターとして指定された関数を使用して、項目が作成されます。この例の場合、元の値は 2 倍されます

## 関数

アロー関数の定義については、すでによく知っています。矢印関数を定義するための、手抜きなしの完全なプロセスは次のとおりです。

```JS
// 基本形
var add = (x, y) => {
    return x + y;
};
```

```JS
const sum = (p1, p2) => {
  console.log(p1) // 1
  console.log(p2) // 5
  return p1 + p2
}

//関数を呼び出す
const result = sum(1, 5)
console.log(result)// 6
```

パラメータが一つの場合()省略

```JS
const sum = p1 =>{

}
```

この形式は、配列を操作する場合に特に便利です。たとえば、map メソッドを使用する場合などです。

```JS
const t = [1, 2, 3]
const tSquared = t.map(p => p * p)
// tSquared is now [1, 4, 9]
```

arrow 関数機能は、ほんの数年前にバージョン ES6 で JavaScript に追加されました。以前は、関数を定義する唯一の方法は、キーワード function を使用することでした。

### function

関数を参照する方法は 2 つあります。1 つは関数宣言で名前を付けることです。(先ほど出たやつ)

```JS
function product(a, b) {
  return a * b
}

const result = product(2, 6)
// result is now 12
```

関数を定義するもう 1 つの方法は、関数式を使用することです。この場合、関数に名前を付ける必要はなく、定義はコードの残りの部分に存在します。

```JS
const average = function(a, b) {
  return (a + b) / 2
}

const result = average(2, 5)
// result is now 3.5
```

矢印構文=>を使用してすべての関数を定義しよう!

## this

ごめん var 使ってます

```JS
//基本形
var a = {
    foo : function () {
        console.log(this === a);
    } ,
};
a.foo();        // true  (this は a を指す)
a.foo.call({}); // false (this は {} を指す)
```

コンストラクタの場合

```JS
function Human( name, age ) {

    this.name = name;
    this.age = age;

}

var taro = new Human( '太郎', 30 );

console.log( taro );
```

また、this を含む関数がグローバルスコープで呼ばれた場合、this はグローバルオブジェクトを参照します。次の例を見てみましょう。

```JS
var hello = "Hello";

var greet = function(){
    console.log(this.hello);
};

greet();            //Hello（window.helloと同義）

```

## クラス

```JS
const fooclass = class {
  constructor(x, y) { /* コンストラクタ */
    this.x = x
    this.y = y
  }
calc() {  /* メソッド */
    return this.x + this.y  /* x と y を足した値を返却する */
  }
}
```

## 画像をスライドさせる

```HTML
<img id="mypic" data-src="https://i.pinimg.com/236x/ec/68/78/ec68785dbfbb1f715cf506b2d1f9fdd8.jpg" width="400" height="300" class="lazyload">
  <script>
const pics_src = ["https://i.pinimg.com/236x/ec/68/78/ec68785dbfbb1f715cf506b2d1f9fdd8.jpg",
                  "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQxKmiHnSqBC98-yVeVrtGO8OV-Pfp2DylzgA&usqp=CAU",
                  "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSje_3K-IG-MGDBGwvGH498oqN3qoLnixKwaQ&usqp=CAU"];
let num = -1;


function slideshow_timer(){
  if (num === 2){
    num = 0;
  }
  else {
    num ++;
  }
  document.getElementById("mypic").src = pics_src[num];
}

setInterval(slideshow_timer, 1000);
  </script>
```

画像スライドを確認する

## 外部 API 使う

鉄道遅延情報の json を表示させる以下のやつ  
https://rti-giken.jp/fhc/api/train_tetsudo/

コードの内容はわからなくてよいです  
外部 API をためそうコピペの会

```JS
window.addEventListener('load', function() {
  getTrainList();
});

function getTrainList() {
  var url = 'https://tetsudo.rti-giken.jp/free/delay.json'; //遅延情報のJSON
  fetch(url)
  .then(function (data) {
    return data.json(); // 読み込むデータをJSONに設定
  })
  .then(function (json) {
    for (var i = 0; i < json.length; i++) {
      var train = json[i].name;
      var company = json[i].company;

      //表形式で遅延路線を表示する
      var row = document.getElementById('train-list').insertRow();
      row.insertCell().textContent = i + 1;
      row.insertCell().textContent = train;
      row.insertCell().textContent = company;
    }
  });
}
```

```HTML
 <h1>遅延路線</h1>
      <table id="train-list">
      </table>
```

結果

```
遅延路線
1	中央･総武各駅停車	JR東日本
2	内房線	JR東日本
3	高崎線	JR東日本
4	SL	東武鉄道
5	DL大樹	東武鉄道
6	肥薩おれんじ鉄道線	肥薩おれんじ鉄道
7	肥薩線	JR九州
8	久大本線	JR九州
9	姫新線	JR西日本
10	大阪線	近畿日本鉄道
11	奈良線	近畿日本鉄道
12	特急ラピート	南海電気鉄道
13	特急サザン	南海電気鉄道
14	飯田線	JR東海
15	大井川本線	大井川鐵道
16	木次線	JR西日本
17	磐越東線	JR東日本
18	八戸線	JR東日本
19	阿武隈急行線	阿武隈急行
```

## 外部 API 使う 2

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script>
        const callApi = async () => {
  const id = (() => Math.floor(Math.random() * 899))();
  //今のポケモンは898種類いるらしいです

  const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${id}/`);
  const poke = await response.json();

  document.write(`<h1>${poke.name}</h1><img src=${poke.sprites.front_default} />`);
};

callApi();
    </script>
</body>
</html>

```

駆け足でごめんなさい  
お疲れ様です！  
ありがとうございました。

[React Handson へ進む(coming soon...)](a)  
[最初に戻る](https://github.com/CIST-LT-CLUB/HTML_CSS_JavaScript_Handson)
