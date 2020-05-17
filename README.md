# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false, add_index :users,  :name|
|password|string|null: false|
|email|string|null: false, unique: true|
|created_at|integer| |
### Association
- has_many :messages
- has_many :groups, through: :group_user

##messagesテーブル
|Column|Type|Options|
|------|----|-------|
|messages|string|null: false|
|image|text||
|created_at|integer||
|user_id|integer||
### Association
- belongs_to :user

##groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groups|integer|null: false|
|groups_users|integer||
### Association
- has_many :users, through: :group_user

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user
