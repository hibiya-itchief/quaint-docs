# フロントエンドのデプロイ

## デプロイとは

> システム開発におけるデプロイとは、開発したアプリケーション（機能やサービス）をサーバー上に展開・配置して利用できるようにすることです。  
> ビルドとは、デプロイに必要な実行ファイルを作ることです。  
> [デプロイとは？](https://www.bold.ne.jp/engineer-club/deploy)より

デプロイとはつまり、GitHub上のソースコードを実際のサイト上で動かせるようにすることです。

また、デプロイする際にビルドを行います。  
ビルドでは、ソースコードから静的ファイル(HTML)を作成します。

Nuxt generateすることで確認することができます。  
参考：[【Nuxt.js】buildとgenerateの違い](https://blog.mktia.com/diffrences-between-build-and-generate-in-nuxt/)

## Cloudflare Pages

Cloudflare Pagesという静的Webサイトホスティングサービスを利用しています。  
いかに優れているかについては省きます。

## デプロイ設定について

参考：[quaint-waレポジトリ作成手順書](deploy.pdf)



