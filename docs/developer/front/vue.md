# Vueとは何か

## Vueとは何か

> Vue (発音は /vjuː/、view と同様) は、ユーザーインターフェースの構築のための JavaScript フレームワークです。標準的な HTML、CSS、JavaScript を土台とする、コンポーネントベースの宣言的なプログラミングモデルを提供します。シンプルなものから複雑なものまで、ユーザーインターフェースの開発を効率的に支えるフレームワークです。  
> [Vue 3の公式ドキュメント](https://ja.vuejs.org/guide/introduction.html#what-is-vue)より  

QUAINTのフロントエンドで用いている Nuxt.js (後述)のベースとなっている、JavaScript のフレームワークです。  
正式名称は Vue.js です。  

バージョンは Vue 2 です。そのため Vue 3 の書き方とは異なる部分が多々ありますので注意してください。  

ちなみに Vue.**js** の **js** とは、**J**ava**S**cript の略です。  
ただし、QUAINT では JavaScript ではなく TypeScript を主に用いています。  
詳しくは：[scriptについて詳しく](#script)

quaint-appレポジトリは、そのlanguageの9割以上をVueが占めているように、  
Vueのファイルである`.vue`ファイルが基本となっています。  
このページでも、vueファイルについてを主に記述します。

<br><br>

## ディレクトリ位置による違い
vueファイルは、pagesフォルダ配下、layoutフォルダ配下、componentsフォルダ配下に配置します。

pagesフォルダ配下のものは、seiryofes.comの各ページの中身にあたります。  
詳しくは：[ルーティング](nuxt.md/#_1)  
 
layoutsフォルダ配下のものは、seiryofes.comのどのページでも表示されうるもの、例えば左上のハンバーガーメニューや(layouts/default.vue)、存在しないURLに飛んだ時の画面など(layouts/error.vue)です。  
詳しくは：[fallbackについて](nuxt.md/#fallback)  

componentsフォルダ内には、どのページでも使える自作componentを記述したものを入れます。[2023年度](https://2023.seiryofes.com/)においてはあまり使いませんでしたが、もっと積極的に使うべきものです。  
  
このページでは基本的に、pagesフォルダ、layoutsフォルダ配下のvueファイルを想定しています。

<br><br>

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

<h3>template</h3>

`<template>`では、componentを用いて画面そのものを設定します。  
componentとは、画面上のボタンや検索バーなど、画面の構成部品のことです。  
例えば、この位置にボタンを設置し、この位置に検索バーを設置する、といったことを行います。  
HTML と Vue.js の独自の書き方、および Vuetify を使って記述します。  
[templateについて詳しく](#template)

<h3>script</h3>
`<script>`では、表示される画面の裏で動く処理、いわばページを「動かす」ための記述をします。  

例えば、`<template>`のボタン1が押されたとき、`<script>`の処理1を行うようにする、といったことを行います。  
JavaScript の拡張版である TypeScript を基本として、Vue.js や Nuxt.js の独自の書き方も用いて記述します。  
[scriptについて詳しく](#script)

<h3>style</h3>

`<style>`では、画面のデザインを調整します。  
例えば、この文章を中央寄せにして、この文章の色を赤色にする、といったことを行います。  
CSS で記述します。これら3つの中では最も単純だと思います。  
[styleについて詳しく](#style)

<br><br>
また、Node.js という言わば「JavaScriptの実行環境」がありますが、開発する上ではあまり気にしなくて結構です。  
詳しくは省きます。

<br><br>

## templateについて詳しく

> HTML と Vue.js の独自の書き方、および Vuetify を使って記述します。

そもそも HTML とは、WEBページを作成するための言語のことです。  
例えば、見出しや段落・表・リンクなどを設定します。  
詳しくはこちら：[初心者向けHTML入門](https://saruwakakun.com/html-css/basic/html)  
  
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

<br>

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

HTML の書き方についてはこちら：[初心者向けHTML入門](https://saruwakakun.com/html-css/basic/html)

コード全体をはさんでいる`<template>`が、HTML でいう`<html>`のようなものです。Vue 独自の書き方です。  
!!! warning "注意"
    状況は限られていますが、`<template>`の中に、また別に`<template>`タグが入ることがあります。詳しくは【工事中】

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

    しかし、`<v-container>`外に設置しなくても実装できたのではないかと今思っています。検証はまた今度。【工事中】

`<v-container>`に加え、`<v-row>`や`<v-col>`などがあります。主にこの3つを用いて Vuetify のグリッドを構成します。  
詳しくはこちら：[Vuetify Grid System](https://comfortdesignlab.github.io/about/vuetify/grid-system)  

またグリッドについては`<v-spacer>`も有用です。  
詳しくはこちら：[Grid system](https://v2.vuetifyjs.com/ja/components/grids/#v-spacer)  

また、少し話は逸れますが、グリッドという点では margin や padding も大事な要素です。  
詳しくはこちら：[marginやpaddingの調整がめっちゃ楽な件](https://qiita.com/00__/items/d5973c7dc79b95b08739)  
<br><br>
コメントアウトの方法は HTML のものと同じです。  

具体的な書き方は既存のvueファイルを見て学ぶのが良いと思います。

<br>

### その他のcomponent

<h4>NuxtLink</h4>

詳しくは【工事中】

<h4>client-only</h4>

詳しくは【工事中】

<br>

### 変数について

Vue では、データが更新されたときに自動で表示を更新します。  
(この表示のことをDOMと呼び、このことをリアクティブであると表現することがあります。)  

つまり、`<template>`と`<script>`の間で変数は共有されているということになります。  

ただし、ある意味当然ですが、`<template>`ではグローバル変数しか用いることができません。  
詳しくは：[スコープとthis](#this)

具体的に変数を用いるには、Mustache記法や`v-bind`等があります。  
Mustache記法について詳しくはこちら：[Mustashe（マスタッシュ）記法](https://johobase.com/vue-js-mustashe-notation/)  
`v-bind`等については次の[ディレクティブ](#_4)の項で説明します。

<br>

### ディレクティブ

ディレクティブについて：[主要なディレクティブ一覧](https://qiita.com/y-suzu/items/9b84da0a3a9ee4a5686b)  

いくつか補足します。

<h4>v-ifとv-show</h4>

seiryofes.comでは`v-show`の方が多く用いられています。  
詳しくはこちら：[Vue.jsのv-ifとv-showの違い](https://qiita.com/aqua_ix/items/61eac355f3c24d7676e1)  
[条件付きレンダリング](https://v2.ja.vuejs.org/v2/guide/conditional)

<h4>v-for</h4>

`v-for`を使う際は、必ず`:key="hogehoge"`も併記してください。  
この`hogehoge`には、例えば`v-for="item in items"`の場合は`:key="item.id"`のように、配列の各要素によって異なるものを指定する必要があります。  
詳しくはこちら：[key属性をつけ忘れないようにする](https://note.com/shift_tech/n/nbcae6c4ab442)

<h4>v-on</h4>

seiryofes.comでは`@click`で使用することが多いです。  
また、`@click.prevent`および`@click.stop`について、詳しくは【工事中】

<h4>v-model</h4>

> 双方向データバインディング

とは要するに、変数を`<script>`からも`<template>`からも更新できるということです。  

例えば、検索窓(`<v-text-field>`)で`v-model="hogehoge"`とすれば、検索窓の入力内容はそのまま変数`hogehoge`の値になり、`<script>`から`hogehoge`の値を変更すると検索窓の入力内容も変更される、といった具合です。  

また、`v-model="hogehoge"`の`hogehoge`がboolean型の場合、ふつうそれは「`hogehoge`がtrueのとき表示する」を意味します。  
この手法は`<v-snackbar>`や`<v-dialog>`で多く用いられています。  

<h4>v-bind</h4>

あまり難しく考えない方がよいです。  

例えば、`<NuxtLink to="/groups">`を押せば、[団体一覧のページ](https://2023.seiryofes.com/groups)に飛ぶことしかできません。  
ですが、これを`<NuxtLink v-bind:to="hogehoge">`とすると、`<script>`で`hogehoge`の値を`"/groups"`だとか`"/map"`だとかにすることで簡単にリンク先を変更できます。  

<br><br>

## scriptについて詳しく

> JavaScript の拡張版である TypeScript を基本として、Vue.js や Nuxt.js の独自の書き方も用いて記述します。

HTML や CSS がページの見た目を担当するのに対し、JavaScript は、ページを言わば「動かす」ための言語です。
???+ warning "注意"
    **Javaは全く別の言語です。**JavaScriptの名は、当時人気であったJavaの名にあやかりこう名付けたそうです。  
    前述のとおり、JSと略されることがあります。  
また、JavaScript の拡張版である TypeScript とは、JavaScript を基本にして、「型( Type )」に厳格にすることでエラーを未然に防ごうという言語です。TSと略されることがあります。
???+ tip "詳しく"
    TypeScript では、JavaScript と同じ構文などが使えます。なので、TypeScript 独自の内容以外は、JavaScript と同じと考えても良いと思います。  
    また、TypeScript で記述したコードは、JavaScript で記述されたコードに変換されます。  
    このことを**コンパイル**と呼びます。  
    例えば、JavaScript では全ての行の終わりにセミコロン**`;`**を付ける必要がありますが、TypeScript ではコンパイル時に自動で付けてくれるため必要ありません。  
    型( Type )について、詳しくはこちら：[値・型・変数](https://typescriptbook.jp/reference/values-types-variables)

JavaScript の書き方については、[MozillaのJavaScriptガイド](https://developer.mozilla.org/ja/docs/Web/JavaScript/Guide)に代表されるように、かなり多くの情報がネット上にあります。  
対して、TypeScript の日本語情報はそれほど多くはありません。  
その中では、[サバイバルTypeScript](https://typescriptbook.jp/)というサイトの、[読んで学ぶTypeScript](https://typescriptbook.jp/reference)の項の記事群が分かりやすいと思います。

Nuxt.js（ナクスト・ジェイエス）は、Vue.js をベースとして開発された JavaScript フレームワークです。

> Vue.js 自体が JavaScript の View (HTMLファイル) のフレームワークですが、Nuxt.js はその Vue.js ファイルを使ってURLのルーティングや API 処理をはじめとするアプリケーション開発に欠かせない機能の実装を想定した仕様になっており、より開発がしやすくなっています。  
> [Nuxt.jsとは？](https://techmania.jp/blog/javascript0009/)より

詳しくは：[Nuxtについて詳しく](nuxt.md)    

とにかく、seiryofes.comをよりよくしてくれるフレームワークという認識で結構です。

また、SEO対策も`<script>`で行います。  
詳しくは【工事中】

<br>

### 具体的な書き方

2023/10/25時点の[groups/index.vue](https://github.com/hibiya-itchief/quaint-app/blob/develop/pages/groups/index.vue)より抜粋しました。

``` ts linenums="1"

<script lang="ts">
import { Group, Tag } from 'types/quaint'
import Vue from 'vue'

type Data = {
  nowloading: boolean
  tags: Tag[]
}

export default Vue.extend({
  name: 'GroupsPage',
  auth: false,
  async asyncData({ $axios, payload }): Promise<Partial<Data>> {
    if (payload !== undefined) {
      return { groups: payload.groups, tags: payload.tags }
    }
    const task = [$axios.$get('/groups'), $axios.$get('/tags')]
    const res = await Promise.all(task)
    return { groups: res[0], tags: res[1] }
  },
  data(): Data {
    return {
      nowloading: true,
      tags: [],
    }
  },
  head() {
    return {
      title: '探す (団体一覧)',
      meta: [ //省略
      ],
    }
  },
  created() {
    // 内容
  },

  methods: {
    SearchGroups() {
        // 内容
    },
    FilterGroups(group: Group) {
        // 内容
    },
  }
  })
</script>

```

順に説明します。

``` ts linenums="1"
<script lang="ts">
import { Group, Tag } from 'types/quaint'
import Vue from 'vue'
```

あまり気にしなくて結構です。   
2行目では、 [types/quaint.ts](https://github.com/hibiya-itchief/quaint-app/blob/develop/types/quaint.ts)でまとめて定義している型( Type )のうち2つを`import`しています。各ページ、使うものだけを`import`してください。  

???+ note "詳しく"
    例えば、`Tag`についてはこのようになっています。

    ``` ts linenums="1"
    export type Tag = {
      id: string
      tagname: string
    }
    ```
    これにより、型が`Tag`の変数は、必ずそのプロパティに型が`string`である`id`と、同じく型が`string`である`tagname`を持つということになります。  
    また、このファイルで定義されている型はすべて大文字から始まります。  
    参考：[型エイリアス](https://typescriptbook.jp/reference/values-types-variables/type-alias)  

``` ts linenums="5"
type Data = {
  nowloading: boolean
  tags: Tag[]
}
```

このページで使われるグローバル変数の型を定義しています。  
グローバル変数について：[スコープとthis](#this)  
必ずしも必須というわけではなく、型を定義せず使っているページもあります。  
`Tag[]`というのはすべての要素が`Tag`型の配列のことです。  

変数名はsnake_caseとlowerCamelCaseのどちらかで命名しています。

``` ts linenums="10"
export default Vue.extend({
  name: 'GroupsPage',
  auth: false,
```

12行目の記述は、このページはログインしなくても閲覧できるということを意味します。  
`auth`のデフォルトはtrueとなっています。

``` ts linenums="13"
  async asyncData({ $axios, payload }): Promise<Partial<Data>> {
    if (payload !== undefined) {
      return { groups: payload.groups, tags: payload.tags }
    }
    const task = [$axios.$get('/groups'), $axios.$get('/tags')]
    const res = await Promise.all(task)
    return { groups: res[0], tags: res[1] }
  },
```

この部分の記述について、【工事中】  
詳しくは：[レンダリング](nuxt.md/#_2)     

``` ts linenums="21"
  data(): Data {
    return {
      nowloading: true,
      tags: [],
    }
  },
```

この部分では、先ほど用意したグローバル変数の初期値を設定します。

``` ts linenums="27"
  head() {
    return {
      title: '探す (団体一覧)',
      meta: [ //省略
      ],
    }
  },
```

29行目では、ページのタイトルを設定します。  
![画像](images/vue-title.png)  
30行目付近ではSEO対策の文言を入力します。  
詳しくは：【工事中】

``` ts linenums="34"
  created() {
    // 内容
  },
```

createdの部分に記述した内容は、ページが開かれたときに実行されます。  
また、ほぼ同じ挙動を示すmountedというものもあります。  
詳しくは：[レンダリング](nuxt.md/#_2)     

``` ts linenums="38"
  methods: {
    SearchGroups() {
        // 内容
    },
    FilterGroups(group: Group) {
        // 内容
    },
  }
  })
</script>
```

methodsについて：[メソッドの書き方と呼び出す方法](https://progtext.net/programming/vue-method/)

また、method(関数)内でreturnすると、値を返すことができます。

???+ note "例"
    ``` vue linenums="1"
    <template>
        <!---->
            <v-btn v-show="HogeHoge()">Hoge</v-btn>
        <!---->
    </template>

    <script lang="ts">
    // 省略
    methods: {
        HogeHoge() {
            return true
            }
    }
    </script>
    ```
    `<v-btn>`は`HogeHoge()`を実行します。その結果trueが帰ってきたので、結果的に`v-show="true"`となります。

ただし、returnすると強制的にそこで関数が終わるので注意です。

thisについては[次の項](#this)で説明します。

関数名はUpperCamelCaseで命名するようにしています。

<br>

### スコープとthis

スコープについて：[変数のスコープ](https://typescriptbook.jp/reference/statements/variable-scope)

`<script>`においては、グローバル変数を指定するときに`this.`という記法を用います。

!!! note "例"
    変数`hogehoge`であれば、`this.hogehoge`

それ以外はそのままです。

ただし、`<template>`で変数を呼び出す際には、`this.`は不要です。  
そもそも、グローバル変数しか呼び出すことはできません。  

<br>

### template内で記述する

``` vue linenums="1"
<template>
    <!---->
        <v-btn @click="HogeHoge()">Hoge</v-btn>
        <v-btn @click="hogehoge = 5">Hoge</v-btn>
        <!-- この二つは同じ挙動 -->
    <!---->
</template>

<script lang="ts">
// 省略
methods: {
    HogeHoge() {
        this.hogehoge = 5
        }
}
</script>

```

このように、関数を実行するはずだったところをそのまま記述することで、同じ挙動を実現できます。  
また、2つ以上の処理を行う場合、セミコロン**`;`**を使って実現できます。単に改行でもかまいません。
``` vue linenums="1"
<v-btn @click="hoge = 5; hogehoge = 10">Hoge</v-btn>
<v-btn @click="
  hoge = 5
  hogehoge = 10
  ">Hoge</v-btn>
<!-- この二つは同じ挙動 -->
```

<br>

### その他有用なもの

<h4>console.log</h4>

デバッグの際に重宝するメソッドです。  
適宜変数や配列の値を出力することができるので、エラーの起きている原因を簡単に調査できます。  
詳しくは：[コンソールにログを出力する](https://www.javadrive.jp/javascript/console_obj/index1.html)

ただし、一般に製品版では使うべきではないとされています。あくまでも開発ツールの一つだということですね。

<h4>Playground</h4>

Playgroundとは、手軽にコードの試し書きができる開発環境です。  

例としてTypeScript公式：[Playground](https://www.typescriptlang.org/ja/play)

関数やメソッドの動作やコンポーネントの表示などをチェックできます。

検索すれば、HTML・CSS・Vue・VuetifyなどもPlaygroundがあります。

<br><br>

## styleについて詳しく

> CSS で記述します。

CSS とは、Webページの文字の色や大きさ、背景、配置といったスタイル（見た目）を設定する言語です。  
詳しくはこちら：[初心者向けCSS（スタイルシート）入門](https://saruwakakun.com/html-css/basic/css)

また、より高度な書き方に**`@`**を使うものや`hover`といったものがあります。  
詳しくは【工事中】  

<br>

### 具体的な書き方

CSS の書き方そのままです。

``` vue linenums="1"
<script>
/*
CSSの書き方
*/
</script>
```

[2023年度](https://2023.seiryofes.com)ではトップページや「ご案内」の6項目のページに多く用いられていました。

書き方についてはこちら：[初心者向けCSS（スタイルシート）入門](https://saruwakakun.com/html-css/basic/css)

class名などはkebab-caseで命名します。

<br>

### template内で設定する

``` vue linenums="1"

<template>
    <!---->
        <span class="hogehoge"> hogehoge </span>
        <span style="color: #F00;"> hogehoge </span>
        <!-- この二つは同じ表示 -->
    <!---->
</template>

<style>
.hogehoge {
    color: #F00;
}
</style>
```

このように、本来`<style>`で書くべきものを、`style=" "`で記述することで同じ表示を実現できます。  
単発的に色を変更するときなど、時にこの手法の方が見やすいコードになることがあるので、積極的に活用しましょう。

<br><br>

## 【工事中】

`<template>`において、`<v-icon>`にはマテリアルデザインのアイコンを使用しています。
一覧：[Material Design Icons](https://pictogrammers.com/library/mdi/)