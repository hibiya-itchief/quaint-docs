# GitHubの使い方
星陵祭オンライン整理券システムでは、GitHubというweb上のサービスを使って開発を行います。<br>

![画像](images/github-1.png)

## GitHubとは
---
複数人で[ソースコード](#_3)を編集できる、共同開発のための後述する様々な機能を持ったサービスです。<br>
しかも基本無料となっているのに加え、<br>
[ローカル環境を整備しなくとも](#_3)使うことができます！<br>

現在動いている星陵祭のサイト(<https://seiryofes.com>)や、<br>
このページ(<https://hibiya-itchief.github.io/quaint-docs/developer/github/>)も<br>
GitHub上にソースコードがあります。<br>
<br>

このページでは、そんなGitHubの具体的な使い方について記します。<br>
(以下、IT委員会のGitHubに入っていることを前提とします。)<br><br><br><br>

## Repository
---
レポジトリと読みます。<br>
フォルダと同じようなものというイメージでよいと思います。<br>
この中にたくさんのファイルやフォルダが入っています。<br>

IT委員会のGitHubの [Overview](https://github.com/hibiya-itchief) ではレポジトリの一覧が表示されます。<br>
レポジトリ名の横にPublicと書かれている場合、外部の人が中身を見ることができます。個人情報に注意しましょう。<br>
<br>

各レポジトリについては以下の通りです。<dl>
<dt>quaint-app</dt>
<dd>フロントエンドの中身です。</dd>
<dt>quaint-api</dt>
<dd>バックエンドのAPIの中身です。</dd>
<dt>quaint-docs</dt>
<dd>現在開いているこのサイトの中身です。多くのファイルが .md 形式で、1つ1つが1ページに対応しています。</dd>
<dt>general</dt>
<dd>唯一Privateレポジトリ(非公開)で、IT委員会内部についての情報などを入れる予定となっています。</dd>
</dl>
<br>

ここでは例として [quaint-app](https://github.com/hibiya-itchief/quaint-app/tree/develop) レポジトリのdevelop[ブランチ](#branch)(後述)を使って説明します。<br>

![画像](images/github-2.png)
赤枠の内容を上から順に説明します。<br>

検索ボックスでは、<br>

* IT委員会という組織(Organization)の中<br>
* 現在開いているレポジトリの中<br>

のどちらで検索するのか決めることができます。<br>
ただし、この検索はあまりヒットしない(検索が厳しい)イメージなので気を付けてください。<br>
<br>

次に、一番左の[Code](https://github.com/hibiya-itchief/quaint-app/tree/develop)ではソースコードの一覧が表示されます。<br>

[Issues](https://github.com/hibiya-itchief/quaint-app/issues)では、このレポジトリ内のissue一覧が表示されます。後で詳しくやります。<br>

[Pull requests](https://github.com/hibiya-itchief/quaint-app/pulls)では、このレポジトリ内のプルリクエスト一覧が表示されます。後で詳しくやります。<br>
<br>

次の赤枠は、現在開いている[branch](#branch-commit)を示しています。<br>

その右には現在このレポジトリにあるbranchの数が示され、押すとbranch一覧のページに飛びます。後で詳しくやります。<br>

右から2番目のAdd fileではファイルを追加することができます。<br>

右端のCodeというのは[Codespace](#codespace)を作るためのボタンです。後で詳しくやります。<br>
<br>

また、画面外下方には **`README.md`** が表示されています。<br>
<br>

次に、[pages/index.vue](#_3)を例にして、ファイルの編集画面を説明します。<br>

![画像](images/github-3.png)

このように、ソースコードには色が付けられています。<br>

この画像は閲覧モードとなっています。<br>
右の鉛筆マークを押すと編集(Edit)モードになれます。<br>

内容を編集して、[Commit](#branch-commit)をします(Ctrl + Sでも可)。後で詳しくやります。<br>

ただし、この画面で編集することはまれで、[Codespace](#codespace)で行うことが多いです。<br><br><br><br>

## Branch / Commit
---
branchとは「枝」を意味します。<br>

GitHubでは、本流を直接変更するとリスクが大きいため、<br>
内容の全く同じbranch(枝)を作り、そこで編集・動作確認をして、<br>
本流に変更箇所を結合させるという仕組みとなっています。<br>

issueを解決するために作ることが多いです。<br>

![画像](images/github-4.png)
branch一覧のページです。<br>

Default Branchはmainとなっていますが、<br>
実質本流にあたるのはmainブランチ、developブランチの2つです。<br>
この2つは直接編集ができないようになっています。<br>

mainは[seiryofes.com](#_3)の中身にあたります。<br>

developは開発における本流で、<br>
ほとんどのbranchはdevelopから分流され、<br>
developにプルリクエストします。<br>
mainをdevelopと同じにすることで、seiryofes.comの内容が最新版になるということになります。<br>


Active branchesは３か月以内にcommitがあったbranchで、<br>
Stale Branchesはそれより古いもののことです。特に語ることはありません。<br>

![画像](images/github-5.png)
branchを作る際は、名前と、源流を指定されます。<br>
ふつう源流はdevelopでよいと思います(ふつう変更箇所をdevelopに結合するため)。<br>
ただし、Default Branchがmainブランチなので、新しく作った時点ではmainがプルリクエスト先となっています。<br>
注意しましょう。<br>
私[@hibiyahibiyahibiya](https://github.com/orgs/hibiya-itchief/people/hibiyahibiyahibiya)は、ブランチ名を基本 **`#(issueの番号)-内容`** としています。<br>

また、[issue](#issue)の方からもbranchをつくることができます。<br>

![画像](images/github-6.png)<br>
この赤枠部分を押します。<br>

![画像](images/github-7.png)<br>
そうすると、このように最初から<br>
**`(issueの番号)-(issueの題名)`**<br>
という名前でつくることができます。<br>

![画像](images/github-8.png)<br>
また、ファイル編集画面で編集後、右上の「Commit changes...」というボタンを押すか「Ctrl+S」を押すと、Commitができます。<br>
(ファイルの内容がひとつも変わっていないと、押しても出てきません)<br>

Commitとは、branch内で編集内容を更新することです。<br>

commitにはどのような変更を行ったのかを書いておきます。<br>
また、commitは「編集」とは違い、軌跡を残すというイメージの方がよいです。<br>

![画像](images/github-9.png)
編集のつもりでcommitを使っていたときの画像です。<br>
同じ轍は踏まないようお願いします。<br>
代わりに、後に記述する[Codespace](#codespace)内で編集を行いましょう。<br>

また、mainブランチ・developブランチではcommitはできず、代わりに「 *Propose changes* 」となります。<br>
この両branchを編集したいなら、新しくbranchを作って、そこでcommitしてプルリクエストしてくださいということです。<br><br><br><br>

## Issue
---
Issueとは、いわゆるタスク一覧、To Doリストのことです。<br>
修正点や追加したい要素を記入します。<br>

[issue一覧](https://github.com/hibiya-itchief/quaint-app/issues)のページでは、<br>
右上のNew Issueで新しくissueを作ることができます。<br>
また、**Open**には現在あるissue、**Closed**にはすでに解決したissueが並んでいます。<br>

![画像](images/github-6.png)
issueを見る画面です（再掲）。


赤枠上方のAssigneesは、誰が問題を担当するのかを分かりやすくするための機能です。<br>
この画像のissueは **`@hibiyahibiyahibiya`** が担当するということです。<br>
また、誰もいないときには *assign yourself* というテキストがあるので、そちらを押すと自分自身をアサインできます。<br>

プルリクエストで問題が解決するなどしたときには、issueをClosedにしてください。<br>





<br><br><br><br>
## Pull request
---
プルリクエストとは、本流とbranchの間の変更箇所を結合して本流の一部にする機能のことです。<br>
長いのでPRと略すこともあります。<br>


<br><br>
【メモ・要加筆】<br>

[プルリクエストのページ](https://github.com/hibiya-itchief/quaint-app/pulls)(quaint-app)<br>

Openの方には緑色のマークのプルリクエストがあり、これは結合待ちであることを示している。<br>
Closedの方に紫色・赤色のマークのものがあり、前者は無事結合されたこと、後者は何らかの理由があって結合されず閉じられたものであることを示しています。<br>

名前の右についている緑色のチェックやオレンジ色の丸、赤色のバツは確認してくれるbotによるもの。<br>
詳しくは要加筆。<br>

プルリクエスト内では、<br>
Review … プルリクエストを精査する人のこと。指定できる。<br>
Reviewの仕方については要加筆。<br><br><br><br>




## Codespace

Codespaceとは、編集しながら、実際にプログラムがどう動作するのか確認できるツールです。<br>

<br><br>
【メモ・要加筆】<br>

前述のとおりCodeボタンでつくります。<br>

デフォルトではVisual Studio Code(以下VSCode)のweb版が開くようになっています。<br>
開いて少し待つと、VSCode(Web)の画面が開きます。<br>
これがエクスプローラー、これがエディター、これがコンソール、といった風に説明します。<br>

また、設定でVSCode(アプリ)が開くようにもできます。<br>
最初にVSCode(アプリ)をインストールします（説明を省くか要検討）。<br>
ここの設定で変えられます（要加筆）。<br>

VSCode(アプリ)で **`quaint-app`** レポジトリを開発する場合、アドレスバーを127.0.0.1:3000からlocalhost:3000に変更しましょう。<br>
そうすることでログイン処理ができます(どこで指定しているのか要加筆)<br>

* 最初にyarnを入れること(終了コード127)
* yarn run devあるいはエクスプローラーのdevを押してプレビュー(同時に[GitHub Pages](#github-actions)の軽い説明)
* yarn run lintfixあるいはエクスプローラーlintfixで整形
(lintエラーを紹介)
* docsの場合はCtrl+F5(Surfaceの場合、キーボード左下のFnボタンを押して光らせてから。要加筆)

<br><br><br><br>

## GitHub Actions など
---
GitHub ActionsやDependabot、GitHub Pagesなどについて説明する予定です。<br>

【要加筆】<br><br><br><br>

## その他
---
学割や環境構築についても説明を入れる予定です。
ただし、Surfaceでは本格的な環境構築の必要性は薄いと思います。
最低でも10GB以上の空きが必要とされるのが主な理由です。

【要加筆】<br><br><br><br>


## 通知について
---
初期設定時、GitHubの通知は非常に多いです。

【メモ・要加筆】<br>
ただし、通知そのものは必要。<br>
Line等で知らせる必要のないように、issueやプルリクエストに気づける通知設定に。<br>
Gmail設定がおすすめ(スマホで気づけるため)。<br>



## 補足
---	
* **ソースコード** … 「そのプログラムにどんな動作をしてほしいか」を記述したテキストファイルのこと。<br>
PythonやJavaScriptなどのプログラミング言語で記述する。
* **ローカル環境を整備しなくとも** … 何もダウンロードする必要はないということ。
* すべてWeb上で完結させることができる。
* **seiryofes.com** … 正確には、2023.seiryofes.com(2023年度の場合)。<br>
現在はseiryofes.comに飛ぶと20**.seiryofes.comにリダイレクト(飛ばす)するようになっている。
* **pages/index.vue** … 「(**`quaint-app`**レポジトリ内の)**`pages`**フォルダの中の **`index.vue`** ファイル」という意味。<br>
このようなファイルの位置の示し方をpathという。

<br><br><br><br>


