## これはなんなの？

D言語の入門記事を目指しているドキュメントです。  
対象を「全くプログラミングをしたことがない人」にしたいですが、
k3kaimuの文章がわかりにくいために、「C言語がある程度使える人向け」な記事になっています。
(この問題は後ほど修正されます！！)


## おねがい

* おかしな点、説明が難しすぎるなど、気づいた点があればIssueを立ててください。  
* 誤字などの訂正も含めた修正はPull Requestを送っていただければMergeします。


## 執筆時の注意

* 新しい記事(章)を書く場合には、Issueを確認して事前に誰かが記事を書いていないか確認して、誰も記事を書くことを表明していなければIssueを立ててください。
また、そのIssueには`contribute`タグを付けてください。そして、記事が書き終わったのならば立てたIssueをCloseしてください
これらを行う理由は「せっかく書いてたのに先を越された」という状況を回避するためです。  

* このページの下部の掲載リストに乗っている記事を新しく書く場合には、掲載リストの通りに書く必要はありません。
リストはあくまでも目安なので、タイトルや節などの名前も自由に書いてください。
その場合には、このreadmeの更新もお願いします。

* 現在はgithubでmarkdownの表示を行っていますが、近々pandocでhtmlを生成する方式に変える可能性があります。
ローカルでmarkdownのプレビューを行う場合には、pandocでHTMLの生成を推奨します。

pandocの拡張されたmarkdownの仕様とGFMとの差をある程度解消するために、Ddocのマクロが定義されたファイルを`ddoc/markdown.ddoc`に用意しています。
そのため、もっとも推奨する書き方はdd(Ddoc)ファイルで執筆、dmdでDdocマクロの展開を行ってmarkdownを作るという方法です。
dmdでマクロ展開を行う`ddoc/dd2md.d`というソースコードも公開しているので参考にしてください。

将来的には、現在開発中のdekyllを使ってhtmlにし、github pagesで公開することを考えています。
dekyllは、jekyllやHakyllに似た静的サイト生成ツールで、マクロなどはD言語で記述します。


## ライセンス

このページを含め、原則としてd-manualのすべての記事(ソースコードを含む)にはCC BY-NC-SAを適用します。  

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/deed.ja"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="http://i.creativecommons.org/l/by-nc-sa/3.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">d-manual</span> は <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/deed.ja">クリエイティブ・コモンズ 表示 - 非営利 - 継承 3.0 非移植 ライセンスの下で提供されています。</a>.

プログラムのソースコードとは違い、ドキュメントはある程度厳しいライセンスであったほうがよいと判断しました。


## 執筆者リスト

* けーさん(twitter: k3_kaimu, github: k3kaimu)


## 執筆協力者

以下に記載しているのは、監修や推敲などで記事の執筆を協力してくださった方々

* きょんたん (twitter: kyonfuee, github: kyontan)
* github: majiang
* github: shirataki
* tom tan (twitter: tm_tn, github: tom-tan)


## 掲載リスト(予定含む)

### [001 D言語入門-Hello, World!](https://github.com/k3kaimu/d-manual/blob/master/hello_world.md)
    Hello, world!---その前に
    Hello, world!
    Hello, world!を詳しくみてみる
    write, writelnと型について
    関数について
    writef, writefln
    コメント

### [002 変数と型](https://github.com/k3kaimu/d-manual/blob/master/variable_type.md)
    式(Expression)と文(Statement)とは？
    変数(Variable)
        変数の宣言(Declaration)
        変数の寿命とスコープ
        左辺値(lvalue)と右辺値(rvalue)
    いろいろな型(Type)
        リテラル(Literal)とシンボル(Symbol)
        デフォルト初期化値(Default Initializer; Type.init)
        void
        論理型(Boolean)
        整数型(Decimal Number)
        浮動小数点型(Floating-Point Number)
        虚数浮動小数点型(Imaginary Floating-Point Number)
        複素浮動小数点型(Complex Floating-Point Number)
        文字型(Charactor)
        文字列型(String)
        派生型(Derived Data Type)
        ユーザー定義型(User Defined Type)
    型修飾子(Type Qualifiers)
        const
        immutable
        shared
    記憶域クラス(Storage Class)
        const
        immutable
        shared
        scope
        関数でのみ有効となる記憶域クラス
    型推論(Type Inference)

### [003 式と演算子](https://github.com/k3kaimu/d-manual/blob/master/expr_operator.md)
    式と演算子
    演算子と暗黙の数値型変換
    数値型に対する演算子
        括弧(bracket)
        単項プラス(unary plus), 単項マイナス(unary minus)
        インクリメント(increment), デクリメント(decrement)
        算術演算子
        ビット演算子(Bitwise operators)
        代入演算子(Assignment operator), 複合代入演算子(Compound assignment operators)
        同値テスト(Equal to), 非同値テスト(Not equal to)
        比較(Compare)
        論理演算子(Logical operators)
        コンマ演算子
    付録 演算子の優先順位と結合規則

### [004 標準入力と文字と文字列](https://github.com/k3kaimu/d-manual/blob/master/standardinput.md)
    std.stdio.readln
        まずは使ってみる
        readlnの詳細
    文字と文字列とは？
        文字コード
        改行文字と制御文字
        文字列の簡単な操作をする
    readf
        まずは使ってみる
        ポインタとは？
    これら以外の標準入力からの取得

### [005 条件分岐](https://github.com/k3kaimu/d-manual/blob/master/if.md)
    文のいろいろ
    条件分岐とは？
    if文
    boolと評価される式
    if(宣言)な文
    &&(且つ)と||(又は)

### [006 ループ](https://github.com/k3kaimu/d-manual/blob/master/loop.md)
    while文
    無限ループ
    do文
    for文
    foreach range文
        foreach_reverse
    ループを抜ける, 次に進める
        ループから抜け出す
        ループを次に進める

### [007 その他の制御文](https://github.com/k3kaimu/d-manual/blob/master/other_statements.md)
    goto文とラベル
    switch文とcase文

### [008 配列](https://github.com/k3kaimu/d-manual/blob/master/array.md)
    配列(Array)とは？
    スタックとヒープ
    静的配列(Static Array)
    配列とポインタのお話
    スライス
        ヒープ上のメモリの確保
        要素の追加とスライス同士の結合、大きさの拡大縮小
        ガベージコレクタ
        スライス演算子
        スライスを使ったベクトル演算
        スライスの独立性
    スライスや配列の等価テスト(同値テスト)
    スライスや配列の大小比較
    foreachと配列
    Rangeとスライス
    静的配列やスライスのプロパティとメソッド
    多次元配列(配列の配列)
    配列操作のまとめ

### [009 連想配列](https://github.com/k3kaimu/d-manual/blob/master/associative_array.md)
    連想配列(Associative Array)とは？
    基本操作
        in演算子
        同値テスト(`==`, `is`)
    プロパティ
        `size_t aa.length`
        `V[K] aa.dup`
        `V aa.get(K key, lazy V defValue)`
        `K[] aa.keys`
        `V[] aa.values`
        `auto aa.byKey`
        `auto aa.byValue`
        `V[K] aa.rehash()`
    foreach
        ベーシックな方法
        `aa.keys`を使った方法
        `aa.byKey`を使った場合
        `aa.values`を使った場合
        `aa.byValue()`を使った場合
    クラスをキーとして使うには(高度)

### [010 ポインタ](https://github.com/k3kaimu/d-manual/blob/master/pointer.md)
    ポインタとは(復習)
        アドレスってなんやねん！
        アドレスとポインタってなにがどうやねん！
        変数のアドレスってどこやねん！
    ポインタの使い方
        ポインタと配列とインデックス演算子とポインタへの加算
        ポインタと左辺値
        ポインタの初期値とゼロ値
        特別なポインタ`void*`とスライス`void[]`

### [011 関数](https://github.com/k3kaimu/d-manual/blob/master/function.md)
    関数とは？
        関数による処理のまとめ
    関数の基礎
        宣言の書き方と関数本体
        関数の引数
    デフォルト引数
    引数の記憶域クラス
    可変個引数関数
    オブジェクトを形成する引数
    返値型推論
    関数の属性
        プロパティ関数`@property`
        関数のメモリ安全性
        純粋関数`pure`
        例外を投げない関数`nothrow`
        UDA(User Defined Attribute)
        `const`, `immutable`, `inout`, `abstract`, `final`
    関数オーバーロード(多重定義, overload)
    ローカル`static`変数
    ネスト関数
    関数ポインタ
    デリゲート`delegate`
    関数のリテラルとラムダ
    UFCS(Uniform Function Call Syntax)
    CTFE(Compile Time Function Execution)

### 構造体
    構造体とは？
    構造体のプロパティ
    コンストラクタとデストラクタ
    Postblitsコンストラクタ
    `@disable`
    メンバ関数(メソッド)
    `static`メンバ
    デフォルトpublic
    演算子オーバーロード
    `invariant`
    `alias this`
    ネスト構造体
    Voldemort Type
    無名構造体と`std.typecons.Tuple`
    構造体へのポインタ

### 共用体
    共用体とは？
    危険な共用体
    代わりに`std.variant`

### 列挙体
    列挙体とは？
        TODO:
    名前付きと無名
    `enum`のベース型
    `enum`のデフォルト初期化値
    final switch
    コンパイル時定数

### クラスとインターフェース
    クラスとは？
    基本は構造体と同じ！
    `scope`クラス
    クラス内でネストされたクラス
    継承とオーバーライド
    `abstract`クラス
    `final`クラス
    インターフェースとは？
    無名クラス
    `std.typecons.wrap`, `std.typecons.unwrap`

### constとimmutable
    `immutable`とは？
    `const`とは？
    `inout`
    関数引数での`in`

### 例外
    積極的に投げてけ
    エラーと例外
    `try`, `catch`, `finally`
    `scope`文
    `assert`式と`std.exception.enforce`

### 単体テスト
    テストは重要
    どこにでも書ける
    `-unittest`
        `-main`

### 契約プログラミング
    関数での契約
    構造体やクラスでの契約

### モジュールと名前空間
    モジュールとパッケージ
    パッケージと`package.d`
    名前空間とは？
    アクセス修飾子
    `.`演算子

### テンプレートとコンパイル時編
#### テンプレートの基本
#### Eponymous Template
#### 可変長引数テンプレート
#### is式と__traits
#### static if
#### string-mixin
#### template mixin
#### pragma(msg, )
#### CTFE
#### Compile Time (Meta) Programming
#### Range
#### 演算子オーバーロード


## 主な情報源

* [D Programming Language](http://dlang.org/)
* [プログラミング言語 D 2.0](http://www.kmonos.net/alang/d/)
* [プログラミング言語D](http://www.amazon.co.jp/%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E8%A8%80%E8%AA%9ED-Andrei-Alexandrescu/dp/4798131105) 翔泳社, 2013/04, Andrei Alexandrescu(著), 中川真宏(監修), 原健治(監修), 長尾高弘(翻訳)
* 各章の執筆者の頭
