# README

## usersテーブル

| Column              | Type       | Options                  |
| ------------------- | ---------- | ------------------------ |
| email               | string     | null: false, ユニーク制約 |
| encrypted_password  | string     | null: false              |
| name                | text       | null: false              |
| profile             | text       | null: false              |
| occupation          | text       | null: false              |
| position            | text       | null: false              |

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column              | Type       | Options                  |
| ------------------- | ---------- | ------------------------ |
| title               | string     | null: false,             |
| catch-copy          | text       | null: false              |
| concept             | text       | null: false              |
| user                | reference  | null: false, 外部キー     |

### Association
- belongs_to :users
- has_many :comments

## commentsテーブル

| Column              | Type       | Options                  |
| ------------------- | ---------- | ------------------------ |
| content             | text       | null: false,             |
| prototype           | reference  | null: false, 外部キー     |
| user                | reference  | null: false, 外部キー     |

### Association
- belongs_to :users
- belongs_to :prototypes