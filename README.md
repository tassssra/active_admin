# README

## 手順

`bin/rails db:create`

`bin/rails g model User name:string age:integer address:string`

`bin/rails db:migrate`

Gemfileに以下のgemを追加

gem `active_admin`

gem `devise`

`bundle install --path vendor/bundle`

active_adminに必要なファイルをインストール
`bin/rails g active_admin:install`

`bin/rails db:migrate`

AdminUserのseedデータをDBに入れて管理者ログインできるようにする
`bin/rails db:seed`

サーバー起動

`bin/rails s`

`localhost:3000/admin`

`db/seeds.rb`に書いてある`admin@example.com`, `password` でログイン

`New Admin User`ボタンから新しい管理者を作成

最初の管理者を削除してログインし直す

`bin/rails g active_admin:resource user`









