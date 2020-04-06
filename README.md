# README

# 名前
Match App

# 概要
マッチングアプリケーション。
社会的なつながりを作り出すサービスです。

# 制作背景
共通の趣味、目標を持った人たちのつながりを作り出すサービスがあれば便利だと思い作成致しました。
これからマッチングサービスの需要も上がると思い作成致しました。

# DEMO
プロフィール
<img width="1440" alt="スクリーンショット 2020-04-05 22 29 05" src="https://user-images.githubusercontent.com/60652767/78499825-e8ea8880-778d-11ea-9d9c-cb3417ef25f4.png">

プロフィール編集
<img width="1440" alt="スクリーンショット 2020-04-05 22 30 12" src="https://user-images.githubusercontent.com/60652767/78499737-5b0e9d80-778d-11ea-98b2-d901f5d49d0c.png">

スワイプ機能
<img width="1439" alt="スクリーンショット 2020-04-05 22 29 29" src="https://user-images.githubusercontent.com/60652767/78499813-cfe1d780-778d-11ea-81e7-ea7eab179028.png">

メッセージ機能
<img width="1440" alt="スクリーンショット 2020-04-06 17 21 01" src="https://user-images.githubusercontent.com/60652767/78537848-146f8080-782b-11ea-9558-601adee93187.png">

# 開発環境
  * Html
  * SCSS
  * Ruby
  * Ruby on Rails
  * JavaScript
  * jQuery
  * gem devise
  * gem carrierwave
  * gem bootstrap

# usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|e-mail|string|null: false, unique: true|
|password|string|null: false, unique: true|
|self_introduction|string|
|sex|integer|null: false|
|img_name|string|null: false|
### Association
- has_many :chat_messages
- has_many :chat_room_users

# reactionsテーブル
|Column|Type|Options|
|------|----|-------|
|to_user_id|integer|null: false|
|from_user_id|integer|null: false|
|status|integer|null: false|
### Association
- belongs_to :to_user
- belongs_to :from_user

# chat_roomsテーブル
|Column|Type|Options|
|------|----|-------|
### Association
- has_many :chat_messages
- has_many :chat_room_users

# chat_messagesテーブル
|Column|Type|Options|
|------|----|-------|
|chat_room_id|integer|null: false,|
|user_id|integer|null: false|
|message|string|null: false|
### Association
- belongs_to :chat_room
- belongs_to :user

# chat_room_usersテーブル
|Column|Type|Options|
|------|----|-------|
|chat_room_id|integer|null: false,|
|user_id|integer|null: false|
### Association
- belongs_to :chat_room
- belongs_to :user
