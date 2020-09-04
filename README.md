<h1 align="center">PicTweet</h1>

[![Image from Gyazo](https://gyazo.com/082c456a66440408233ed6a8c6543d6e.jpg)](https://gyazo.com/082c456a66440408233ed6a8c6543d6e)

## :link: アプリケーションの概要
<ul>
  <li>ツイート投稿共有アプリです。</li>
  <li>画像と文章を合わせて投稿できます。</li>
</ul>

## :link: アプリケーションの機能
<ul>
  <li>ユーザーの新規登録/ログイン</li>
  <li>ツイートの一覧表示</li>
  <li>ツイートの投稿</li>
  <li>ツイートの削除</li>
  <li>ツイートの編集</li>
  <li>ツイートの詳細表示</li>
  <li>ツイートへのコメント</li>
  <li>ツイートの検索</li>
</ul>

## :link: 開発環境

<p align="center">
  <a href="https://www.ruby-lang.org/ja/"><img src="https://user-images.githubusercontent.com/39142850/71774533-1ddf1780-2fb4-11ea-8560-753bed352838.png" width="45px;" /></a>
  <a href="https://railsguides.jp/getting_started.html"><img src="https://y-hilite.com/wp-content/uploads/2018/02/rails_logo.png" height="45px;" /></a>
  <a href="https://devdocs.io/html/"><img src="https://user-images.githubusercontent.com/66232530/88711698-87429580-d153-11ea-9ae5-452b13d15a70.png" height="45px;" /></a>
  <a href="https://sass-lang.com/"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/Sass_Logo_Color.svg/144px-Sass_Logo_Color.svg.png" height="40px;" /></a>
  <a href="https://jquery.com/"><img src="https://user-images.githubusercontent.com/66232530/88712858-58c5ba00-d155-11ea-9314-fa1a6d3442fc.png" height="50px;" /></a>
  <a href="https://github.co.jp/"><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" height="45px;" /></a>
</p>

## :globe_with_meridians: サイト紹介

## :computer: インストール方法
1.このリポジトリを複製
$ git clone https://github.com/karajan-37458/PicTweet.git

2.インストールしたリポジトリに移動
$ cd PicTweet

3.gemをアプリケーションに適用
$ bundle install

4.DBの作成&反映
$ rails db:create
$ rails db:migrate

5.アプリケーションの起動
$ rails s
👉 http://localhost:3000

## :link: DB設計

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :tweets
- has_many :comments

### tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|null: false|
|image|text||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :comments

### commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :tweet
