# テーブル設計

## usersテーブル

| Column      | Type     | Options        |
| ----------- | -------- | ---------------|
| email       | string   | null: flase    |
| password    | string   | null: flase    |
| name        | string   | null: flase    |
| profile     | text     | null: flase    |
| occupation  | text     | null: flase    |
| position    | text     | null: flase    |

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column        | Type       | Options                          |
| ------------- | ---------- | ---------------------------------|
| title         | string     | null: flase                      |
| catch_copy    | text       | null: flase                      |
| concept       | text       | null: flase                      |
| image         | string|    | ActiveStorage                    |
| user          | references | null: false, foreign_key: true   |

### Association

- has_many :comments
- belongs_to :user

## commentsテーブル

| Column        | Type       | Options                          |
| ------------- | ---------- | ---------------------------------|
| text          | text       | null: flase                      |
| user          | references | null: false, foreign_key: true   |
| prototype     | references | null: false, foreign_key: true   |

### Association

- belongs_to :user
- belongs_to :prototype