##DB設計

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association


## usersテーブル
|Column|Type|Options|
|------|----|-------|
name|string|index: true, null: false,unique: true|
mail|strung|null: false|

### Association
- has_many :group, through: menbers
- has_many :message
- has_many :members

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
