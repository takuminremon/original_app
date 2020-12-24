
## users テーブル

| Column               | Type     | Options                  |
| ----------           | ------   | -----------              |
| nickname             | string   | null: false              |
| encrypted_password   | string   | null: false              |
| email                | string   | null: false,unique: true |
| first_name           | string   | null: false              |
| first_name_kana      | string   | null: false              |
| last_name            | string   | null: false              |
| last_name_kana       | string   | null: false              |
| birthday             | date     | null: false              |


### Association


<!--中間テーブル-->
## room_users テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user

## messages テーブル

| Column      | Type       | Options                        |
| -------     | ---------- | ------------------------------ |
| content     | string     |                                |
| user_id     |            |                                |
| partner_id  |            |                                |
| sentence    | text       |                                |
| user        | references | null: false, foreign_key: true |
| room        | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user