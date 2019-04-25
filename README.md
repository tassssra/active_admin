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

このままだとユーザー追加はまだできないので`admin/users.rb`にパラメーターの追加を許可する

permit_paramsの右に許可するパラメーターを記述(migrationファイル参照)
`permit_params :name, :age, :address`

#### 日本語化

gem 'rails-i18n'

`config/application.rb`

`class Application < Rails::Application`に以下を追記

`config.i18n.default_locale = :ja`

gemを追加したのでサーバー再起動。一部日本語化される

`config/locales/ja.yml`を新規作成

以下のように書く
```
ja:
  activerecord:
    models:
      user: 'ユーザー'
      comment: 'コメント'
      admin_user: '管理者'
    attributes:
      user:
        name: '名前'
        age: '年齢'
        address: '住所'
```

`Admin Users`はスネークケースで表記。modelなので単数形にする。












