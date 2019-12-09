## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, add_index:true|
|name|string|null: false, add_index:true|
### Association
- has_many :groups
- has_many :groups through:  :uers_groups
- has_many :messages

  
  # sssss

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many_to :groups_users
- has_many_to :users  ,through:  :groups_users
- has_many_to :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string||
|text|text||
|user_id|integer|null: false ,foreign_key: true
|group_id|integer|null: false ,foreign_key: true
### Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|string|null:false,foreign_key:true|
|group_id|integer|null: false ,foreign_key: true
### Association
- belongs_to :group
- belongs_to :user
