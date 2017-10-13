== README

Please feel free to use a different markup language if you do not plan to run
<tt>rake doc:app</tt>.

## newsテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false, foreign_key: true|
|body|text|null: false, foreign_key: true|
|image|string|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many : comments

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index:true, unique: true|
|mail|string|null: false, index:true, unique: true|
|password|string|null: false|

### Association
- has_many : news
- has_many : comments

## commentテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index:true, unique: true|
|user_id|integer|null: false, foreign_key: true|
|news_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :news

