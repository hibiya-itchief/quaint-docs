
【メモ・要加筆】
でも0から学ぶのも大変ですから、<br>
先輩たちの手がけたソースコードを軸にして、わからないところだけ参考サイトを参照したり調べたりというのがおすすめです。<br>

最初は分からないものだらけで大変だと思いますが、<br>
一つのソースコードを例にしてそのすべてを説明すれば他のソースコードの労力はかなり少なくなるのではないか、と思っています。いつか作る予定です。<br>
<br>
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


