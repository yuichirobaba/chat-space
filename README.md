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
- has_many :groups_users
- has_many :groups, though: :groups_users


## groupsテーブル
|Column|Type|Options|
|text|text||
|user|references|null: false, foreign_key: true|
## association
- has_many :groups_users
- has_many :users, though: :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false,foreign_key: true|

## association
- belong_to :group
- belong_to :user

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|string||
|user||references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

## Association
- has_many :group
- has_many :user
