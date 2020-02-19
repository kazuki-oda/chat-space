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
|username|integer|null: false| 

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, index|
|groupname|integer|null: false|
|user_id|integer|null: false, foreign_key: true, index|

### Association
- belongs_to :user

## groups_messagesテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true, index|
|message_id|integer|null: false, foreign_key: true, index|

### Association
- belongs_to :group
- belongs_to :message

## gmessagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, index|
|body|text|null: false, index|
|image|string|index|
|group_id|integer|null: false, foreign_key: true, index|
|user_id|integer|null: false, foreign_key: true, index|

### Association
- belongs_to :group
- belongs_to :user



