# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string |null: false|
|e-mail|string |null: false|
|password|string |null: false|
### Association
- has_many : groups, through: :user_groups
- has_many : user_groups
- has_many : messages


## user_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|group_id|integer|null: false|
### Association
- belongs_to : user
- belongs_to : group


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many : users, through: :user_groups
- has_many : messages
- has_many : user_groups


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to : user
- belongs_to : group


* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
