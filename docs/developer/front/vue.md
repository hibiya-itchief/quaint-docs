# 拡張子`.vue`のファイル
【現在加筆中】



.vueファイルの扱い方

拡張子がve
`.vue`ファイルでは、具体的なページ画面を設定します。
`layouts`フォルダ内のものは現在開いているページに関わらず表示されうるページ画面について、
`pages`フォルダ内のものは具体的なURLで開けるようなページについて、
`components`フォルダ内のものは繰り返し用いられる部品を作成しています。

前提として
quaint-appレポジトリの話
``` vue

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

`.vue`ファイルは大きくこの3つで構成されています。

`<template>`では、画面そのものを設定します。
!!! note "例"
    この位置にボタンを設置。この位置にテキストボックスを設置。
`HTML`と`Vuetify 2`を使って記述しています。
`Vuetify`とは、`Vue.js`のUIライブラリです。マテリアルデザインを重視したUIが簡単に実現できます。

`<script>`では、表示される画面の裏で動く処理を記述します。
!!! note "例"
    `<template>`のボタン1が押されたとき、`<script>`の処理1を行うように。

`JavaScript`の拡張版である`TypeScript`を基本として、`Vue.js`や`Nuxt.js`の独自の書き方も用いて記述します。

`<style>`では、画面のデザインを調整します。
??? note "例"
    この文章を中央寄せに。この文章の色を赤色に。
[2023年度](2023.seiryofes.com)においては、トップページ・ご案内ページなどに多く用いられています。対し、団体一覧ページなどのオンライン整理券に関わるページは`<style>`を用いずに、`Vuetify`のデザインそのままで作られているものが多いです。来年度以降は、わかりやすさをそのままに、これらのページでも`<style>`を使用していきたいと思っています。
`CSS`で記述します。これら3つの中では最も簡単に扱えると思います。

`<template>`の説明

`HTML`と`Vuetify`を使って記述する、と書きました。
そもそもHTMLとは、
また、`Vuetify`とは、

この`<template>`は最終的に完全に`HTML`のファイルに変換されます。


基本的な書き方は、
```vue:template構造例.vue
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


このように`<hogehoge>`と`</hogehoge>`という一対のタグで囲み、その中に新たな`<hogehoge></hogehoge>`が入るという、いわゆる入り子構造で成ります。各タグ間はインデント(改行をし、左側に空白を設ける)をするのが好ましいとされています。
また、親・子という表現を用いることがあり、たとえば上の構造例では、`<v-col>`は`<v-row>`に囲まれているため、`<v-row>`の子`component`であるということができます。


一番最初の`<v-app>`は必須です。`<v-app>`がないと`Vuetify`は使えません。

次の`<v-container>`は必須ではありませんが、基本記述すべきだと思われます。`<v-container>`中の内容は、両端に空白が挿入されるため、見やすくなります。対し、どうしても画面端のぎりぎりに何かを置きたい、例えば画面端から色を付けたい場合などは`<v-container>`外に設置することで実現できます。

`<v-container>`含め`<v-row>`と`<v-col>`は`grid system`を支配するためのものです。
[LINK] [LINK]


<br><br><br><br><br><br><br><br><br><br><br>


また、`grid system`的には`margin`や`padding`も大事な要素です。`<template>`の各`component`内や`<style>`内で設定することができます。<br><br><br>
`<v-spacer>`も
[LINK]

`<v-hogehoge>`




<br><br><br><br><br><br><br><br><br><br><br>







<v-app>

    みたいので囲う
    v-appで囲まれてる範囲内でvuetifyコンポーネントが使える
v-appをはがすことは全くないからOK
    途中でtemplateが挿入されることがある非常に限定的で詳しくはこのページで


grid関係は別枠、
<v-container
<v-row
<v-col


あとdivh2あたりの別枠

また、componentsを使える


<<aa> aa </aa> の形なこと


<span>,inlineなこともかくともしんせつだよね、なんいどとかかnnkeinaku

<!--
のくだり
-->

省略記法も、< />
e.g.<br> <br /> <v-divider></v-divider>

mustache


v-model
v-bind
v-on

classみぎ、全部ダブルクオーテーションがち、

id
style
hrefとか:toとか
nuxtlinkも？それは個別で？

全体の説明：lintfixについて；


あと、開発者ツールで各部分が見れる、




script

script lang="ts"
dta data⇨ここでグろーバル、templateでもつかえる　
Dataで片塩亭なこと、これ
typescriptの「TYPE・型」の概念書かないとかな…
後特別にconsole.logについて？
this

$axios
createdなど

methods


style

ただのcss

h2 {

}
の形式、ぜんぶにセミコロンが必要な感じ
#aiueo {
    これid
}
.hoge {
    これclass
}
ケバブケースでつなげないとだめ
また、@を使うタイプやhoverなどいろいろあるがそれは各ページの解説で。
ちなみにlintstyleが一番正確で丁寧,cssそのままだからか




