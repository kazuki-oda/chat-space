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
|id|integer|null: false, index|
|email|string|null: false| 
|password|string|null: false| 
|name|string|null: false| 

### Association
- belongs_to :group

## groups＿usersテーブル
has_many :groups_users
has_many :users, through: :groups_users
|Column|Type|Options|
|------|----|-------|
|groups_id|integer|null: false, foreign_key: true, index|
|user_id|integer|null: false, foreign_key: true, index|

### Association
- belongs_to :user
- belongs_to :group

## usersテーブル
has_many :groups_users
has_many :users, through: :groups_users
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, index|
|name|string|null: false|
|user_id|integer|null: false, foreign_key: true, index|

### Association
- belongs_to :user

## groups_messagesテーブル
has_many :groups_messages
has_many :groups, through: :groups_messages
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true, index|
|message_id|integer|null: false, foreign_key: true, index|

### Association
- belongs_to :group
- belongs_to :message

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, index|
|body|text
|image|string
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



