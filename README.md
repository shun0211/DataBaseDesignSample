# DataBaseDesignSample

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|strings|null: false, index: true|
|password|strings|null: false|
|Email|stirings|null: false, unique: true|

### association
- has_many :messages
- has_many :groups, though: :users_groups
- has_many :users_groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|strings|null: false|

### association
- has_many :users, though: :users_groups
- has_many :users_groups
- has_many :messages

## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

### messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
|body|text| |
|image|strings| |

## Association
- belongs_to :user
- belongs_to :group
