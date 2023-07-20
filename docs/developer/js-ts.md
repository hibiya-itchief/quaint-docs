# `JavaScript` / `TypeScript`

**`JavaScript`**とは、ブラウザを動かすための言語です。<br>
**`HTML`**だけでは用意された文字や画像がそこにあるだけですが、それが具体的に「動作」するようになるのは **`JavaScript`** のおかげです。<br>
**`Java`とは違う言語です。**<br>
<br>

**`TypeScript`**とは、【要加筆】。<br>
ただし、あまり細かいことは気にせずに「そういう言語があるんだ」ぐらいの気持ちで良いと思います。<br>

[Vue.js](https://hibiya-itchief.github.io/quaint-docs/developer/vue-js/#script)の **`.vue`** ファイルの `<script>`が **`TypeScript`** で書かれています。<br>
<br>

**`TypeScript`**は参考にできるサイトが多いです。
[これ](https://typescriptbook.jp/overview)や[これ](https://typescript-jp.gitbook.io/deep-dive/getting-started)などが参考になると思います(基本的に文法に関わるところだけで構いません)。<br>

でも0から学ぶのも大変ですから、<br>
先輩たちの手がけたソースコードを軸にして、わからないところだけ参考サイトを参照したり調べたりというのがおすすめです。<br>

最初は分からないものだらけで大変だと思いますが、<br>
一つのソースコードを例にしてそのすべてを説明すれば他のソースコードの労力はかなり少なくなるのではないか、と思っています。いつか作る予定です。<br>
<br>

最小限のコードを書いて『それがどのように動くのか』確認したい場合には、<br>
公式Playground(いわばプチ開発環境)の[英語版](https://www.typescriptlang.org/play)か[日本語版](https://www.typescriptlang.org/ja/play)を使うのがよいです。
<br><br><br><br>

【以降要加筆】
<br><br><br><br>
<br><br><br><br>
<br><br><br><br>
<br><br><br><br>
<br><br><br><br>
<br><br><br><br>
<br><br><br><br>
<br><br><br><br>

### console.log
console.log()とは
開発者ツール内のコンソールにログを出す操作です。
```javascript
hoge = 5
console.log(hoge)
console.log('hoge')
(結果コンソール)
5
hoge
```
これは意図する操作ができているのか確認するのに非常に役立ちます。<br>
特に、原因不明のエラーが出ている際に、これを細かく使うことで<br>
どこが誤っているのか判明することが多くあります。<br>

## localStorage
getなど






## this
グローバル関数とローカル関数という認識




## `<script>`内でのTypeScript
---
### return
vue.jsで用いられるmethodsの中身に`return`を用いる際に注意があります。<br>
`return`の指示があった時点でその関数は終わります。<br>

```vue

methods: {
  Functon1(hoge: number) {
    return hoge+5
  },
  Functon2(hoge: number) {
    return hoge+5;
    console.log('aiueo')
  },
  Functon3(hoge: number) {
    console.log('aiueo');
    return hoge+5
  }
}
```
つまり、このようなとき、`Function1`と`Function2`が同じ動作をするということです。<br>
`Function3`のみ`return`より先に`console.log('aiueo');`があるためです。<br>



### axios

Node.jsとのコラボ
async/awaitはJS、だけど$axois.$get等はnode.jsなのかな？
Nodeの方に書いて…methodもそうする？？

シングルクオーテーションとダブルクオーテーションは同じ

APIからもらってくるデータは`object`型。<br><br><br><br>

## 補足

<br><br><br><br>