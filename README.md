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
|email|string|null: false|
|password|string|null: false|
|name|string|null: false,index: true|

## association
- has_many :group
- has_many :comments
- has_many :groups_user
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false,foreign_key: true|

## association
- belong_to :group
- belong_to :user

## groupsテーブル
|Column|Type|Options|
|text|text||
|user|references|null: false, foreign_key: true|
## association
- belong_to :comments
- belong_to :user
- belong_to :groups_user


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|string||
|user||references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

## Association
- belong_to :group
- belongs_to :user
