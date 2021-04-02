## usersテーブル
|Column     |Type        |Options     |
|-----------|------------|------------|
|name       | string     |null: false |
|email      | string     |null: false |
|password   |string      |null: false | 
|profile    |text        |null: false |
|occupation |text        |null: false |
|position   |text        |null: false |

### association
- has_many :prototypes
- has_many :comments

## prototypesテーブル
|Column     |Type        |Options                      |
|-----------|------------|-----------------------------|
|title      |string      |null :false                  | 
|catch_copy |text        |null :false                  |
|concept    |text        |null :false                  |
|user       |references  |null :false,foreign_key :true|

### association
- has_many :comments
- belongs_to :users


## commentsテーブル
|Column     |Type        |Options                      |
|-----------|------------|-----------------------------|
|text       |text        |null :false                  | 
|prototype  |references  |null :false,foreign_key :true|
|user       |references  |null :false,foreign_key :true|

### association
- belongs_to :prototypes
- belongs_to :users