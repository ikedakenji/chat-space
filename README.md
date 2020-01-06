# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

  ## DB設計

  ### Usersテーブル
  |column|type|option|
  |------|----|------|
  |name|string|null: false|
  |email|string|null: false, unique: ture|
  |pass|string|null: false|
  ### association
  - has_many :massages
  - has_many :groups_users
  - has_many :groups, though: :groups_users

  ### groups_usersテーブル
  |column|type|option|
  |------|----|------|
  |user_id|integer|null: false, foreign_key: ture|
  |group_id|integer|null: false, foreign_key: ture|
  ### association
  - belongs_to :group
  - belongs_to :user

  ### groupsテーブル
  |column|type|option|
  |------|----|------|
  |name|string|null: false, unique: ture|
  ### association
  - has_many :groups_users
  - has_many :users ,though :groups_users
  - has_many :massages

  ### massagesテーブル
  |column|type|option|
  |------|----|------|
  |body|text|foreign_key: ture|
  |image|string||
  |user_id|integer|null: false, foreign_key: ture|
  |group_id|integer|null: false, foreign_key: ture|
  ### association
  - belongs_to :user
  - belongs_to :group

