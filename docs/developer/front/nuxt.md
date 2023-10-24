# Nuxt について詳しく

## Nuxt とは

Nuxt.js（ナクスト・ジェイエス）は、Vue.js をベースとして開発された JavaScript フレームワークです。

> Vue.js 自体が JavaScript の View (HTMLファイル) のフレームワークですが、Nuxt.js はその Vue.js ファイルを使ってURLのルーティングや API 処理をはじめとするアプリケーション開発に欠かせない機能の実装を想定した仕様になっており、より開発がしやすくなっています。  
> [Nuxt.jsとは？](https://techmania.jp/blog/javascript0009/)より

## ルーティング

ここではこう定義します。(誤用だったらごめんです)  

<h4>ルーティング</h4>

pagesフォルダのvueファイルがそれぞれseiryofes.comのどのページ、どのURLに対応するかについての設定のこと。

> Nuxt では通常、ルーティングはディレクトリ構造から自動的に算出される。  
> [Nuxtで独自のルーティングを追加・拡張する](https://vlike-vlife.netlify.app/posts/nuxt_routing_extend)より

!!! note "例1"
    pages/index.vue  
    [seiryofes.com](https://2023.seiryofes.com)

!!! note "例2"
    pages/map.vue  
    [seiryofes.com/map](https://2023.seiryofes.com/map)

!!! note "例3"
    pages/groups/index.vue  
    [seiryofes.com/groups](https://2023.seiryofes.com/groups)

このように、各フォルダの`index.vue`はそのフォルダ内でのトップページのような扱いとなります。  
また、[seiryofes.com/map](https://2023.seiryofes.com/map)のように子ページを作らないページについては、そのまま`map.vue`を作ることでスマートにページを連ねることができます。  

ただし、フォルダ名の最初にアンダーバー**`_`**がついているものは扱いが特殊となります。

!!! note "例4"
    pages/groups/_groupId/index.vue  
    [seiryofes.com/groups/testgroup](https://2023.seiryofes.com/groups/testgroup)

!!! note "例5"
    pages/groups/_groupId/index.vue  
    [seiryofes.com/groups/35r](https://2023.seiryofes.com/groups/35r)

このように、APIにある団体のIDから自由に決められるようになっています。
（動的ルーティングと言います。）

!!! note "例6"
    pages/groups/_groupId/data.vue  
    [seiryofes.com/groups/testgroup/data](https://2023.seiryofes.com/groups/testgroup/data)

残念ながらこの`/data`はAdminしか見ることができないのですが、このように、動的ルーティングであっても配下のディレクトリ構造に応じて正しくURLが用意されます。  


### fallbackについて【工事中】

存在しないURLに飛ぶと404ページを表示するようにしています。  
（厳密にいうと嘘かも.ここで、layouts/error.vueとの違いも記述する）  
（nuxtconfig解説ページ？fallbackの200と404のくだり、nuxt generateの話）





## レンダリング方法について【工事中】

SSR CSRなど。

## 工事中

APIって何の話…？？  

[リンク](https://develop365.gitlab.io/nuxtjs-2.8.X-doc/ja/guide/routing/)  

NuxtLinkについてはこちら：https://v2.nuxt.com/ja/docs/get-started/routing/  

