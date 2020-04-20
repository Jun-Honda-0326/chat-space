# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|srring|null:false, add_index:true|
|e_mail|string|null:false, unique:true|
|password|string|null:false|
### Association
- has_many :messages
- has_many :groups, through: :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|string|-------|
|group_id|integer|null:false, foreign_key: true|
|user_id|integer|null:false, foreigh_key: true|
### Association
- belongs_to :users
- belongs_to :groups

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :groups

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null:false|

### Association

- has_many :messages
- has_many :users, through: :groups_users]





* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
