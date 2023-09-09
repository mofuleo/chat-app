# テーブル設計

## usersテーブル

| Column                 |  Type        |    Options  |
|----------------------- | ----------   | ----------  |
|name                    | string       | null: false |
|email                   | string       | null: false |
|encrypted_password      | string       | null: false |

## association

-has_many :room_users
-has_many :rooms,through:room_users
-has_many :messages

## roomsテーブル

| Column                 |  Type        |    Options  |
|----------------------- | ----------   | ----------  |
|name                    | string       | null: false |

## association

-has_many :room_users
-has_many :rooms,through:room_users
-has_many :messages

## room-usersテーブル

| Column      |  Type        |    Options                    |
|-------------| -----------  |-----------------------------  |
|user         | references   | null: false,foreign_key: true |
|room         | references   | null: false,foreign_key: true |

## association

-belongs_to :room
-belongs_to :user

## messagesテーブル

| Column      |  Type        |    Options                    |
|-------------| ----------   |-----------------------------  |
|content      | string       |                               |
|user         | references   | null: false,foreign_key: true |
|room         | references   | null: false,foreign_key: true |

## association

-belongs_to :room
-belongs_to :user
