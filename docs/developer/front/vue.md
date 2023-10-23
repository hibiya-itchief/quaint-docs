# 拡張子vueのファイルについて(仮)


## ディレクトリ位置による違い
vueファイルは、pagesフォルダ配下、layoutフォルダ配下、componentsフォルダ配下に配置します。

pagesフォルダ配下のものは、seiryofes.comの各ページの中身にあたります。  
layoutsフォルダ配下のものは、seiryofes.comのどのページでも表示されうるもの、例えば左上のハンバーガーメニューや(layouts/default.vue)、存在しないURLに飛んだ時の画面など(layouts/error.vue)です。  
componentsフォルダ内には、どのページでも使える自作componentを記述したものを入れます。[2023年度](https://2023.seiryofes.com/)においてはあまり使いませんでしたが、もっと積極的に使うべきものです。  
  
このページでは基本的に、pagesフォルダ、layoutsフォルダ配下のvueファイルを想定しています。


## Vueとは何か

> Vue (発音は /vjuː/、view と同様) は、ユーザーインターフェースの構築のための JavaScript フレームワークです。標準的な HTML、CSS、JavaScript を土台とする、コンポーネントベースの宣言的なプログラミングモデルを提供します。シンプルなものから複雑なものまで、ユーザーインターフェースの開発を効率的に支えるフレームワークです。  
> [Vue 3の公式ドキュメント](https://ja.vuejs.org/guide/introduction.html#what-is-vue)より  

QUAINT のフロントエンドで用いている JavaScript のフレームワークです。正式名称は Vue.js です。  

バージョンは Vue 2 です。そのため Vue 3 の書き方とは異なる部分が多々ありますので注意してください。  

ちなみに Vue.**js** の **js** とは、**J**ava**S**cript の略です。  
ただし、QUAINT では JavaScript ではなく TypeScript を主に用いています。  
詳しくは：[scriptについて詳しく](#script)


## vueファイルの構造

vueファイルの大まかな構造は次のようになっています。

``` vue linenums="1"

<template>
    <!--
    内容 
    -->
</template>

<script>
    // 内容
    /*
    内容
    */
</script>

<style>
    /* 内容 */
</style>

```

大きく分けると、以下の3つのセクションで構成されます。

### 1. template
`<template>`では、componentを用いて画面そのものを設定します。  
componentとは、画面上のボタンや検索バーなど、画面の構成部品のことです。  
例えば、この位置にボタンを設置し、この位置に検索バーを設置する、といったことを行います。  
HTML と Vue.js の独自の書き方、および Vuetify を使って記述します。  
[templateについて詳しく](#template)

### 2. script
`<script>`では、表示される画面の裏で動く処理、いわばページを「動かす」ための記述をします。  
例えば、`<template>`のボタン1が押されたとき、`<script>`の処理1を行うようにする、といったことを行います。  
JavaScript の拡張版である TypeScript を基本として、Vue.js や Nuxt.js の独自の書き方も用いて記述します。  
[scriptについて詳しく](#script)

### 3. style
`<style>`では、画面のデザインを調整します。  
例えば、この文章を中央寄せにして、この文章の色を赤色にする、といったことを行います。  
CSS で記述します。これら3つの中では最も単純だと思います。  
[styleについて詳しく](#style)

<br><br>
また、開発環境での動作チェックその他もろもろを担っているのが Node.js です。  
詳しくは【工事中】別ページ
























---
## templateについて詳しく

> HTML と Vue.js の独自の書き方、および Vuetify を使って記述します。

そもそも HTML とは、WEBページを作成するための言語のことです。  
例えば、見出しや段落・表・リンクなどを設定します。  
詳しくはこちらのリンクをご覧ください：[初心者向けHTML入門](https://saruwakakun.com/html-css/basic/html)  
  
では、Vuetify とは何でしょう。  

> Vue の CSSフレームワークの一つです。正式名称は Vuetify.js です。  
> Vuetify を使うと、CSSファイルを作成せずにレイアウトを整えることができます。とても便利です。  
> 指定のタグを記述するだけで、デザイン込みのステキなパーツを表示することができます。  
> なお、デザインは2014年にGoogleが発表したマテリアルデザインというオシャレな概念を元に作成されています。  
> [Vuetify（ビューティファイ）とは何か？](https://prograshi.com/language/vue-js/how-to-use-vuetify/)より

ドキュメントが充実しています。  
([ドキュメントのリンク](https://v2.vuetifyjs.com/ja/components/buttons/))  

バージョンは Vuetify 2 です。Vuetify 3 のドキュメントは仕様が違う箇所があるので注意してください。  
(Vuetify 2 のドキュメントは日本語対応していますが Vuetify 3 は対応していないという違いもあります)  

この`<template>`の記述は、最終的に完全に HTML のファイルに変換されます。

---
### 具体的な書き方

HTML と同じように、入り子構造で成ります。

``` vue linenums="1"
<template>
    <v-app>
        <v-container>
            <v-row>
                <v-col>
                    <v-hogehoge>hogehoge1</v-hogehoge>
                    <v-hogehoge>hogehoge2</v-hogehoge>
                </v-col>
            </v-row>
        </v-container>
    </v-app>
</template>
```

HTML の書き方についてはこちらのリンクをご覧ください：[初心者向けHTML入門](https://saruwakakun.com/html-css/basic/html)

コード全体をはさんでいる`<template>`が、HTML でいう`<html>`のようなものです。Vue 独自の書き方です。  
!!! warning "注意"
    `<template>`の中に、また別に`<template>`タグが入ることがあります。詳しくは【工事中】

`<v-hogehoge>`のように、`v-`から始まっているタグは Vuetify のコンポーネントです。  
また、Vuetify のものは基本的にすべて終了タグを必要とします。ですが実質的に意味をなしていないもの、例えば`<v-spacer>`などのために、`<v-spacer></v-spacer>`のことを  
`<v-spacer />`と略記することができます。  
`<br>`なども`<br />`と表記することがあります。  

一番最初の`<v-app>`は必須です。`<v-app>`がないと Vuetify は使えません。  

次の`<v-container>`は必須ではありませんが、基本記述するものという認識で良いです。
??? tip "詳しく"  
    `<v-container>`中の内容は、両端に空白が挿入されるため、見やすくなります。中央寄せもされます。  
    対し、どうしても画面端のぎりぎりに何かを置きたい場合などは、`<v-container>`外に設置することで実現できます。  
    [2023年度のトップページ](https://2023.seiryofes.com)の右端まで色をつけている部分がその代表例です。   

    しかし、`<v-container>`外に設置しなくても実装できたのではないかと今思っています。検証はまた今度。

`<v-container>`に加え、`<v-row>`や`<v-col>`などがあります。主にこの3つを用いて Vuetify のグリッドを構成します。  
詳しくはこちら：[Vuetify Grid System](https://comfortdesignlab.github.io/about/vuetify/grid-system)  

またグリッドについては`<v-spacer>`も有用です。  
詳しくはこちら：[Grid system](https://v2.vuetifyjs.com/ja/components/grids/#v-spacer)  

また、少し話は逸れますが、グリッドという点では margin や padding も大事な要素です。  
詳しくはこちら：[marginやpaddingの調整がめっちゃ楽な件](https://qiita.com/00__/items/d5973c7dc79b95b08739)  
<br><br>
コメントアウトの方法は HTML のものと同じです。  





---
### 変数などについて【工事中】

あと、@click="~~"
のscriptについても。Method呼び出しも。

@clickの説明のためにここでv-bindとv-model


 mustache
{{}}
[mustache記法](https://johobase.com/vue-js-mustashe-notation/)

 リアクティブ

 v-bind

href :to

 v-model

this.についても

また、特徴として、
リアクティビティー: Vue は JavaScript の状態の変化を自動的に追跡し、変化が起きると効率的に DOM を更新します。
https://v2.ja.vuejs.org/v2/guide/
りアクティビテーのくだりに使えるかもしれないリンク：[これ](https://ja.vuejs.org/guide/introduction.html#the-progressive-framework)

https://mid-works.com/columns/language/javascript/1138064


 v-on

[on](https://qiita.com/terufumi1122/items/9af94f1fab17a24d7110)

v-onは正味@clickでしか見ないからOK
 v-for v-if v-else v-show

[for](https://qiita.com/JetNel0/items/1f618683e4acce5f9aa6)
[if,else,show](https://qiita.com/aqua_ix/items/61eac355f3c24d7676e1)
追加で、v-else-ifも使えるよっていう

`<p style="font-weight: bold;">`
という書き方




## scriptについて詳しく

> JavaScript の拡張版である TypeScript を基本として、Vue.js や Nuxt.js の独自の書き方も用いて記述します。

HTML や CSS がページの見た目を担当するのに対し、JavaScript は、ページを言わば「動かす」ための言語です。
???+ warning "注意"
    **Javaは全く別の言語です。**JavaScriptの名は、当時人気であったJavaの名にあやかりこう名付けたそうです。前述のとおり、JSと略されることがあります。
また、JavaScript の拡張版である TypeScript とは、JavaScript を基本にして、「型( Type )」に厳格にすることでエラーを未然に防ごうという言語です。TSと略されることがあります。
???+ tip "詳しく"
    TypeScript では、JavaScript と同じ構文などが使えます。なので、TypeScript 独自の内容以外は、JavaScript と同じ書き方です。  
    また、TypeScript で記述したコードは、JavaScript で記述されたコードに変換されます。  
    このことを**コンパイル**と呼びます。  
    例えば、JavaScript では全ての行の終わりにセミコロン**`;`**を付ける必要がありますが、TypeScript ではコンパイル時に自動で付けてくれるため必要ありません。  
    公式の[Playground](https://www.typescriptlang.org/ja/play)では、コンパイル前後のコードの違いも見ることができます。  
    このように、TypeScript は JavaScript と非常に互換性が高い言語です。  
    型( Type )について、詳しくは【工事中】

JavaScript の書き方については、[MozillaのJavaScriptガイド](https://developer.mozilla.org/ja/docs/Web/JavaScript/Guide)に代表されるように、かなり多くの情報がネット上にあります。  
対して、TypeScript の日本語情報はそれほど多くはありません。  
その中では、[サバイバルTypeScript](https://typescriptbook.jp/)というサイトの、[読んで学ぶTypeScript](https://typescriptbook.jp/reference)の項の記事群が分かりやすいと思います。

Nuxt.js（ナクスト・ジェイエス）は、Vue.js をベースとして開発された JavaScript フレームワークです。

> Vue.js 自体が JavaScript の View (HTMLファイル) のフレームワークですが、Nuxt.js はその Vue.js ファイルを使ってURLのルーティングや API 処理をはじめとするアプリケーション開発に欠かせない機能の実装を想定した仕様になっており、より開発がしやすくなっています。  
> [Nuxt.jsとは？](https://techmania.jp/blog/javascript0009/)より

ルーティングやAPI処理などについては後述します。詳しくは【工事中】別ページ    
とにかく、seiryofes.comをよりよくしてくれるフレームワークという認識で結構です。



### 具体的な書き方【工事中】

``` vue linenums="1"
<script lang="ts">

いえあ

</script>
```




dta data⇨ここでグろーバル、templateでもつかえる　
Dataで片塩亭なこと、これ

`$axios`


Typeについて



・methods
引数についても、

・createdなど

SSR/CSRへのリンクもとばす

・this.
v-modelとちょっとからむね
スコープの話
前提となるスコープの話：https://typescriptbook.jp/reference/statements/variable-scope
に加えて、script内ではグローバル関数が呼び出せない、this.をつけて、this.関数名とすることで呼び出せる
template内では逆にグローバル関数しか呼び出せません
・console.log

for文　if文











nuxtlinkも？それは個別で？



nuxtについて、SSrとか理解しなきゃ
https://devlog.grapecity.co.jp/nuxtjs-quickstart/



























## styleについて詳しく【工事中】

> CSS で記述します。
CSS とは、Webページの文字の色や大きさ、背景、配置といったスタイル（見た目）を設定する言語です。  
詳しくはこちらのリンクをご覧ください：[初心者向けCSS（スタイルシート）入門](https://saruwakakun.com/html-css/basic/css)

また、idやclassの名前はkebab-caseでお願いします。
snake_case
camelCase


また、@を使うタイプやhoverなどいろいろあるがそれは各ページの解説で。
ちなみにlintstyleが一番正確で丁寧,cssそのままだからか

















エラーについてのページ欲しいね；e.g.SyntaxError


templteの説明で、例としてなんかあげて、なぜなら`<v-hoge hoge hoge="">`みたいな書き方
行が湧けられるのはlintfixだよー⇨リンク飛ばす
, もそう、別にスペース無くてもいいけどそうしてる
スペース必要な場合もある、感覚で。改行も見やすくするためのやつと
scriptの場合、;を使えば改行しなくていいよね、あとtemplateのなかでscript記述できるよね


