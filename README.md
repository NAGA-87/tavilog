# TavilogのER図

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| name       | string | null: false |
| email      | string | null: false |
| password   | string | null: false |

### Association

- has_many :trips
- has_many :comments

## trips テーブル

| Column        | Type       | Options                         |
| ------------- | ---------- | ------------------------------- |
| country       | string     | null: false                     |
| location_name | string     | null: false                     |
| explain       | text       | null: false                     |
| user          | references | null: false, foreign_key: true  |

### Association

- belongs_to :user
- has_many :comments

## comments テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| text        | text       | null: false                    |
| user        | references | null: false, foreign_key: true |
| trip        | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :trip
