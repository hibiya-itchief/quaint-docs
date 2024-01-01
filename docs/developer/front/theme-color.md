# テーマカラーの設定

サイトのテーマカラーの設定の仕方を書いておきます。

## css の設定の変更

~/assets/css/main.css に主な css の設定がまとめられています。
![画像](images/main-css.png)
:root{}にある--theme-color の欄に設定したいテーマカラーのカラーコードを入力してください。

## vuetify の設定の変更

nuxt.config.ts にかかれている vuetify の設定を変更します。
![画像](images/vuetify-setting-theme-color.png)
theme_color にテーマカラーとして設定したいカラーコードを入力してください。

## ローディングバーのカラーの設定

ローディングバー（ロード中に表示されるページ上部の線）のカラーの設定をするには nuxt.config.ts の設定を変更します。
![画像](images/loading-bar.png)
赤線で示した color の設定にの部分に指定したいカラーのカラーコードを入力してください。
