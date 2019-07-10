# Debug  

## ブレイクポイント「BreakPoint」

ブレイクポイントとはデバッガーの実行を一時停止したい場所(行)にブレイクポイントを設定し一時停止した時点の変数などの状態を確認することができる機能のことである。  

ソースコードにブレイクポイントを設定するには二つの方法があり、ブレイクポイントを設定した場所(行)には下のような(5行目)赤い丸がつく。  

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug1-BreakPoint.png)

## Step over,Step in,Step out
まずこの「Step over」,「Step in」,「Step out」の三つはステップ実行と呼ばれるもので一行ずつ実行することができ、実行されるごとに変わる変数の挙動を見るためのデバッグの方法です。  

|||
|:-:|:-:|
|「Step over」|[F10]|
|「Step in」|[F11]|
|「Step out」|[Shift + F11]|

で使うことができる。  

- 「Step over」  
「Step over」 は一行ずつ実行されるが関数があった場合、その関数を実行して次の行に移行します。  
メリットは実行の順番を関数を飛ばして見ることができる点です。

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug2-F10.gif)  

F10を毎回押して進めています。

- 「Step in」  
「Step in」は「Step over」とは逆に関数の内部に入っていきます。　　
メリットは実行の順番をすべて見ることができる点です。

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug3-F11.gif)  

F11を毎回押して進めてます。

- 「Step out」  
「Step out」は実行している関数の呼び出し元までプログラムを進める機能です。

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug4-SHIFT%20%2B%20F11.gif)  

F11を押して進めていって21行目で[SHIFT + F11]を押しています。

## 自動変数・ローカル変数ウィンドウ「Automatic Variable · Local Variable Window」
変数の値を見ることができる機能です。

自動変数ウィンドウは実行し終わった変数を見ることができる

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug11-Local%20VariableWindow.gif)

ローカル変数は関数内の変数の値をすべて見ることができる

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug10-AutomaticVariableWindow.gif)

メリットは、変数の値をわかりやすく見ることができる点です。

## ウォッチ式「Watch Expression」
ウォッチ式はデバッグ中に値の変化を見続けたい変数などを見続けるようにする機能です。

ウォッチ式の表示方法は
[***ツールのデバッグ***]→[***ウィンドウ***(***W***)]→[***ウォッチ***(***W***)]→[***ウォッチ1~4***(***1~4***)]

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug8-WatchExpression.gif)

上のように、選択した変数の値が書き換わるたびにウォッチ１の中にある値も変わります。  

メリットは、バグの原因だと思う変数などを設定することによりバグの発見を早くすることができる。

## データブレイクポイント「Data Break Point」
データブレイクポイントは指定されたアドレスがどこでどう書き換わったのかを簡単に見ることができる機能です。

データブレイクポイントの方法n 
[***ツールのデバッグ***]→[***ブレークポイントの作成***]→[***データブレイクポイント***]→[***アドレスと、条件などを入力***]→[***OK***]

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug9-DataBreakPoint.gif)

メリットは、書き換わってほしくない変数が書き換わっているところを見つけたりするのに便利です。

## メモリウィンドウ「Memory Window」
メモリウィンドウとはメモリのどこを何で使っているかという情報を見ることができるデバッグ機能です。  
特に動的に確保される変数などの値を見るのに便利で、基本16進数か10進数で見ることができます。  

メモリウィンドウに表示の方法は  
[***ツールのデバッグ***]→[***全般***]→[***アドレスレベルのデバッグを有効にする***]→[***F9で一時停止をする***]→[***デバッグ***]→[***ウィンドウ***(***W***)]→[***メモリ***]→[***メモリ1~4***]

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug5-MemoryWindow.gif)

上のように、メモリウィンドウのアドレスのところにアドレスを渡すとint型なので４つ初期化されています。  

メリットは、アドレスと中身を見るっことができるので間違ったメモリの書き換えなどを見つけることができる点です。

## コールスタック「CallStack」
コールスタックとは関数の呼び出し履歴を表示するものです。

コールスタックの表示の方法は  
[***ツールのデバッグ***]→→[***ウィンドウ***(***W***)]→[***呼び出し履歴***]

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug7-CallStack.gif)

上のように、どの関数のなかに入っているのかを見ることができる。
メリットは今どの関数の中にいるかがわかるとどこで何をする関数なのかわかりやすい点です。

## イミディエイトウィンドウ「Immediate Window」
イミディエイトウィンドウはコマンドを入力することによって瞬時に計算などを行ってくれる機能です。

イミディエイトウィンドウの表示は  
[***ツールのデバッグ***]→→[***ウィンドウ***(***W***)]→[***イミディエイト***]

![](https://github.com/ShoumaNakajima/Texture/blob/master/Debug6-ImmediateWindow.gif)

上では、aと入力するとaの値が出力され、a = 4と入力するとaの値が4になり、またaと入力すると4に代わっています。しかし、元のコードでは変わりません。  

メリットは、計算などの答えをすぐに出すことができる点。
