# [Live Memory]

## サービス概要
自分が行ったライブのことを記録できるサービスです。
出演アーティストや公演名・日程に加え、写真やセットリスト、感想などを記録し、共有できます。

## 想定されるユーザー層
音楽ライブに行くのが好きで、自分が行ったライブについて記録し、思い出を振り返りたい人。

## サービスコンセプト
私は主にロックバンドのライブに行くのが好きで、同じ趣味の人たちとTwitterやInstagramなどのSNSで交流をしています。
そしてライブに行った際には必ず、チケットや会場外のポスターやその日に食べたごはんなどの写真を投稿し合っています。

しかし、そういったライブに関する、思い出として大切にしておきたい投稿が
新しく投稿された他のものにすぐに埋もれてしまうことや、すぐに検索できないことに不満を抱いていました。
そこで、ツイートやフィード投稿といった投稿方法に比べ、投稿した写真が他のものに埋もれにくく、
任意のカテゴライズが可能であるInstagramのストーリーズハイライトという方法を
昨年試したのですが、一度忘れてしまったことで途切れてしまいました。
途切れたところから投稿を再開しようと思っても、順番を間違えると間違えた時点からやり直すことになり、
それを防ぐためには一度すべての公演の情報を整理する必要があるため、
億劫に感じ放置してしまっているのが現状です。

また、ライブに行くのが趣味である人たちの間に、
年末にその1年でどれくらいのライブに行ったのかメモにリストアップし、
そのスクショをSNSで投稿する風習みたいなものがあります。
自分も同じように投稿したいという思いはあるものの、振り返って改めてメモに書き出すことを面倒に感じています。

これらのことから、ライブに行く予定が決まったタイミングで登録でき、
ライブが終わったら思い出として写真や感想などを1つにまとめ記録できるサービスがあればいいなと思い、
作ろうと考えました。
登録したあとは公演日順で昇順・降順で並び替えができ、
年やアーティストでフィルターをかけ表示し共有できます。
SNSの他の投稿で埋もれてしまいがちなライブの大切な思い出をまとめることができます。

## 実装を予定している機能
### MVP
- ユーザー登録

- プロフィール
  - ユーザーネーム
  - アイコン
  - ヘッダー画像
  - bio
  - タグ（アーティスト名）
  - SNSのリンク（アイコンで表示）

- ログイン機能
- ログインなし
  - 公開設定された他のユーザーのライブ記録の一覧表示（以下記載）
  - 他のユーザーのプロフィール閲覧
- ログインあり
  - ライブ記録の登録
  - ライブ記録のSNS投稿

- ライブ記録　登録
  - ライブタイトル
  - 公演名（例：宮城公演）
  - 公演日
  - 開場、開演、終演時間
  - ライブ形式（ワンマン、対バン、フェスか選べる）
  - アーティスト名（対バン、フェスを選択した場合複数入力できるようにする）
    - 入力したアーティスト名がタグとして保存され、プロフィールに表示される
  - 開催場所（会場名）
    - キャパやコインロッカーの情報を調べられるよう、会場のサイトURLを貼る欄を設ける
    - 写真（上限：5~10枚程度）（チケット、会場の写真、その日食べたごはんなど）
  - 1枚目が記録のアイコンとして使用される
  - 登録がない場合デフォルトの画像を表示するよう設定
  - セットリスト（直接入力 or プレイリストのリンクを貼る）
    - Spotify、Apple Musicのプレイリストの共有リンクを利用する
  - メモ欄（感想やちょっとしたメモなど、公開か非公開か選べる）
    - noteなどに感想を綴っている人もいるので、リンクを貼る欄を設ける
  - その他URL欄
    - 後日ナタリーなどのニュースサイトで出されるライブレポのリンク
    - アーティストのSNSアカウントのライブに関する投稿（ライブ後の写真など）のリンク
  - 座席や整理番号の登録
    - 公開か非公開か選べる
  - 登録ボタンを押すとプレビュー画面が表示され、修正か送信か選べる

- ライブ記録　一覧（表示形式をリスト、アイコンなど変えられる）
  - リストとした場合、以下の項目が左から順に一列に並び、公演日順などで表示
    - 公演日
    - ライブタイトル
    - 公演名（例：宮城公演）
    - アーティスト名
    - 開催場所（会場名）
  - アイコンとした場合、記録時に登録した写真の1枚目 or デフォルトの画像 の下に以下の項目を表示
    - 公演日
    - ライブタイトル
    - アーティスト名

- ライブ記録　詳細
  - 詳細画面上部には、登録した写真をスライダー形式で表示
  - ライブ記録を登録した際の情報が並ぶ（非公開のものは他のユーザーからは見られない）

- ライブ記録　検索（マルチ検索・オートコンプリート）
  - 開催年やアーティストで絞り込み検索でき、それを参加記録として共有できる
  - リンクを貼るかスクショして共有（その月や年にどれくらいライブに行ったのか投稿できる）

- ライブ記録は、公開か非公開を選ぶことができ、公開を選んだ場合は共有されたリンクから誰でも閲覧可能

### その後の機能
- カレンダーとの連携
  - ライブの予定を登録すると、Googleカレンダーに予定が自動追加される
- 公演日前に登録したライブ情報は一覧画面の上部に表示され、「あと○日」というメッセージも横に表示される


# 画面遷移図
https://www.figma.com/file/2YQXPgWphelfc8g3YSsTzn/%E7%94%BB%E9%9D%A2%E9%81%B7%E7%A7%BB%E5%9B%B3?type=design&node-id=0%3A1&mode=design&t=nJ4GQUYnBUhYGOlE-1

# ER図
[![Image from Gyazo](https://i.gyazo.com/fc4754fd5b0b3fce511f72c0d9eb6d33.png)](https://gyazo.com/fc4754fd5b0b3fce511f72c0d9eb6d33)
