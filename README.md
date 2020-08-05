## users table

|Column|Type|Options|
|------|----|-------|
|nickname|string|null false|
|email|string|null false, unique true|
|password|string|null false, unique true, length:minimum:7|

### Association
- has_one :addresses
- has_one :profiles
- has_one :cards
- has_many :item


## profiles table

|Column|Type|Options|
|------|----|-------|
|first-name|string|null false|
|last-name|string|null false|
|birthday|date|null false|
|user_id|integer|null false, foreign_key true|
|address_id|integer|null false, foreign_key true|

### Association
- belongs_to :user


## cards table

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null false, foreign_key true|

### Association
- belongs_to :user


## items table

|Column|Type|Options|
|------|----|-------|
|name|string|null false|
|explain|text|null false|
|delivery-cost|integer|null false|
|area|string|null false|
|limit|string|null false|
|price|integer|null false|
|user_id|integer|null false,foreign_key true|
|category_id|integer|foreign_key true|
|brand_id|integer|foreign_key true|
|image_id|integer|foreign_key true|

### Association
- belongs_to :user
- belongs_to :category
- belongs_to :brand
- belongs_to :image


## categories table

|Column|Type|Options|
|------|----|-------|
|name|string|null false|

### Association
- has_many :items


## brands table

|Column|Type|Options|
|------|----|-------|
|name|string|null false|

### Association
- has_many :items


## images table

|Column|Type|Options|
|------|----|-------|
|name|text|null false|

### Association
- has_many :items