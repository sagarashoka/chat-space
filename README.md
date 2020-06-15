# CHAT-SPACE DB設計
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true,|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|imaage|string|-|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|

### Association
- has_many :groups, through::groups_users
- has_many :comments
- has_many :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|

### Association
- has_many :commens
- has_many :users,  through::groups_users
- has_many :groups_users
