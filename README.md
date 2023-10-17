## userテーブル
 
| column             | type   | options                   |
| email              | string | null: false , unique:true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Associations

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| column           | type       | options                      |
| title            | string     | null: false                  |
| catch_copy       | text       | null: false                  |
| concept          | text       | null: false                  |
| user             | references | null: false,foreign_key:true |

### Associations

- belongs_to :user
- has_many :comments

## commentsテーブル

| column       | type       | options                        |
| content      | text       | null: false                    |
| prototype    | references | null: false, foreign_key: true |
| user         | references | null: false, foreign_key: true |

### Associations

- belongs_to :prototype
- belongs_to :user
