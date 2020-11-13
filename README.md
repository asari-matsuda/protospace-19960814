# README

## users table
| Column       | Type    | Options           |
|--------------|---------|-------------------|
| email              | string  | null: false |
| encrypted_password | integer | null: false |
| name               | string  | null: false |
| profile            | text    | null: false |
| occupation         | text    | null: false |
| position           | text    | null: false |

### association
* has_many :prototypes
* has_many :comments

## comments table
| Column       | Type    | Options           |
|--------------|---------|-------------------|
| text      | text       | null: false |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

### association
* belongs_to :user
* belongs_to :prototype

## prototypes table
| Column       | Type    | Options           |
|--------------|---------|-------------------|
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references | null: false, foreign_key: true |

### association
* belongs_to :user
* has_many :comments