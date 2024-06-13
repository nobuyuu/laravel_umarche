## ログインIDとパス

管理者ID：test@test.com     パス：password123

オーナーID：test1@test.com  パス：password123

ユーザーID：test@test.com   パス：password123


## ダウンロード方法

git clone

git clone https://github.com/nobuyuu/laravel_umarche.git

laravel_umarche.git


git clone ブランチを指定してダウンロードする場合

giy clone -b ブランチ名 https://github.com/nobuyuu/laravel_umarche.git


もしくはzipファイルでダウンロードしてください

## インストール方法

-cd laravel_umarche

-composer install

npm install

npm run dev


.env.example をコピーして .env ファイルを作成

.envファイルの中の下記をご利用の環境に合わせて変更して
ください。


DB_CONNECTION=mysql

DB_HOST=127.0.0.1

DB_PORT=3306

DB_DATABASE=laravel_umarche

DB_USERNAME=umarche

DB_PASSWORD=password123


XAMPP/MAMPまたは他の環境開発でDBを起動した後に

php artisan migrate:fresh --seed

と実行してください。(データベーステーブルとダミーデータ
が追加されればOK)

最後に
php artisan key:generate
と入力せてキーを生成後、

php artisan serve
で簡易サーバーを立ち上げ、表示確認してください。

## インストール後の実施事項

画像のダミーデータは
public/imagesフォルダ内に
sample1.jpg ～ sample6.jpg として
保存しています。

php artisan storage:link で
storageフォルダにリンク後、

storage/app/public/productsフォルダ内に
保存すると表示されます。
(productsフォルダがない場合は作成してください。)

ショップの画像も表示する場合は、
storage/app/public/shopsフォルダを作成し
画像を保存してください。

## section7の補足

決済のテストとしてstripeを利用しています。
必要な場合は .envにstripeの情報を追記してください。

## section8の補足

メールのテストとしてmailtrapを利用しています。
必要な場合は .envにmailtrapの情報を追記してください。

メール処理には時間がかかるので、キューを使用しています。

必要な場合は php artisan queue:workで
ワーカーを立ち上げて動作確認するようにしてください。
