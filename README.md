# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation
## users Table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key: true, autoincrement|
|email|varchar(255)|null: false, unique_key: true|
|encrypted_password|varchar(255)|null: false|
|reset_password_token|varchar(255)|
|remember_created_at|datetime|
|sign_in_count|integer|null: false, default: 0|
|current_sign_in_at|datetime|
|last_sign_in_at|datetime|
|current_sign_in_ip|varchar(255)| 
|last_sign_in_ip|varchar(255)| 
|created_at|datetime| 
|updated_at|datetime| 
|nickname|string|null: false, index: true|

### Association
- has_many :groups, through: :groups_users
- has_many :comments

### Other
- use divese gem

## groups Table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key: true, autoincrement|
|name|string|null: false|
|created_at|datetime|
|updated_at|datetime|

### Association
- has_many :users, through: :groups_users
- has_many :comments


## groups_users Table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key: true, autoincrement|
|groups_id|integer|null: false, foreign_key: true|
|users_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## comments Table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key: true, autoincrement|
|text|string|null: false|
|img_url|text|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|created_at|datetime|
|updated_at|datetime|

### Association
- belongs_to :user
- belongs_to :group

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

