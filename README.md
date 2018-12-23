# README
# DB

## users table
|Column|Type|Options|
| --- | --- | --- |
|first_name|string|null: false|
|family_name|string|null: false|
|kana_first_name|string|null: false|
|kana_family_name|string|null: false|
|birth_year|integer||
|birth_month|integer||
|birth_day|integer||
|email|string|null: false|
|password|string|null: false|
|nickname|string||
|avator|string||
|introduction|text||
|evaluation_l|integer||
|evaluation_m|integer||
|evaluation_s|integer||

### Association
 - has_many :items, through :histories
 - has_many :comments
 - has_one :credit_cards
 - has_one :address

## addresses table
|Column|Type|Options|
| --- | --- | --- |
|user_id|references|foreign_key: true|
|phone_number|integer|null: false|
|postal_code|integer||
|prefectures|string|null: false|
|municipality|string|null:f alse|
|address|string|null: false|
|building_name|string||

### Association
- belongs_to :user

## credit_cards table
|Column|Type|Options|
| --- | --- | --- |
|number|integer|null: false|
|security_code|integer|null: false|
|expiration_month|integer|null: false|
|expiration_year|integer|null: false|
|user_id|references|foreign_key: true|

### Association
 - belongs_to :user

## items table
|Column|Type|Options|
| --- | --- | --- |
|image|string|null:false|
|name|string|null: false|
|price|string|null: false|
|detail|string|null: false|
|condition|string|null: false|
|size_id|references|foreign_key :true|
|category_l_id|references|foreign_key :true|
|category_m_id|references|foreign_key :true|
|category_s_id|references|foreign_key :true|
|brand_id|references|foreign_key :true|
|shipping_fee|string|null: false|
|shipping_area|integer|null: false|
|shipping_days|string|null: false|
|shipping_method|string||
|item_evaluation|integer||
|seller_id|references|class_name: "User", foreign_key: true|
|buyer_id|references|class_name: "User", foreign_key: true|

### Association
 - belongs_to :user
 - has_many :comments
 - has_one :history
 - has_one :category_l
 - has_one :category_m
 - has_one :category_s
 - has_one :size
 - has_one :brand

## historeis table
|Column|Type|Options|
| --- | --- | --- |
|item_id|references|foreign_key :true|
|seller_id|integer||
|buyer_id|integer||

### Association
 - belongs_to :item
 - belogsn_to :user

## comments table
|Column|Type|Options|
| --- | --- | --- |
|text|text|null: false|
|item_id|references|foreign_key: true|
|user_id|references|foreign_key: true|

### Association
- belongs_to :item
- belongs_to :user

## category_l table
|Column|Type|Options|
| --- | --- | --- |
|genre|string||
|item_id|references|foreign_key: true|
### Association
 - belongs_to :item

## category_m table
|Column|Type|Options|
| --- | --- | --- |
|genre|string||
|item_id|references|foreign_key: true|
### Association
 - belongs_to :item

## category_s table
|Column|Type|Options|
| --- | --- | --- |
|genre|string||
|item_id|references|foreign_key: true|
### Association
 - belongs_to :item

## brand table
|Column|Type|Options|
| --- | --- | --- |
|genre|string||
|item_id|references|foreign_key: true|
### Association
 - belongs_to :item

## size table
|Column|Type|Options|
| --- | --- | --- |
|genre|string||
|item_id|references|foreign_key: true|
### Association
 - belongs_to :item

