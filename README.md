##DB設計

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user|references|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false,unique: true|
|mail|strung|null: false|

### Association
- has_many :group, through: :members
- has_many :messages
- has_many :members

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
