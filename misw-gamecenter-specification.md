[![hackmd-github-sync-badge](https://hackmd.io/CUsBYmHsRSqXyx6jGKYCQg/badge)](https://hackmd.io/CUsBYmHsRSqXyx6jGKYCQg)
###### tags: `MIS.W` `misw-gamecenter`

# misw-gamecenter

## baseとなるhtmlについて

### ナビゲーションバー

- ホーム(`base-home.html`)
- 一般ユーザマイページ(`base-user.html`)
- 管理者マイページ(`base-admin.html`)

の3つに分ける。

---

既に作ったhtmlのどれを対応させればよいのか？
- ホーム：`index.html`
- 一般ユーザマイページ：`mypage_home.html`
- 管理者ユーザマイページ：`admin-page.html`

---

### フッター

- 一つのファイルにまとめる。(`footer.html`) <- `index.html`

## ホーム画面に戻るリンク　題名みたいなやつ

![](https://raw.githubusercontent.com/ITK13201/misw-gamecenter-specification/master/img/portal.PNG)

この`MISW Portal`のところみたいなもの

## マイページのアイコンのメニュー

- ログアウトを追加

## 仕様書とhtmlの対応（slackにある画像のやつ）

1. `index.html`
2. `game-detail.html`
3. `developer_detail`
4. `developer.html`

![](https://raw.githubusercontent.com/ITK13201/misw-gamecenter-specification/master/img/mock-up.jpeg)

## モデル

### backapp

#### gameInf(ゲーム情報テーブル)
- id　(ゲームID,int型)
- title　（ゲームタイトル,string型）
- description　（ゲームの説明,string型）
- user (CustomUser)　（申請者情報, Forign Key）
- status　（ゲームタイトル,int型）
- image　（画像,ImageField型）
- submittedtime　（初回申請日時,DateTime型）
- updatededtime 　（更新日時,DateTime型）
#### gameScore(ゲームスコアテーブル)
- gameid (ゲームID,int型)
- player (プレイヤー名,string)
- score （スコア,int）
#### developPartInf(ゲーム開発者テーブル)
- gameid (ゲームID,int型)
- user (CustomUser)　（申請者情報, Forign Key）
- partinf (開発担当部分,string型)
#### developerInf(開発者情報テーブル)
- user (CustomUser)　（申請者情報, Forign Key）
- description （ひとこと,string型）
#### developerPartInf(開発者マスタ)
- Customuser
#### statusInf(状態マスタ)
- statusid(状態ID,int型)
- statusname（状態,string型）
#### downloadLinkInf(ダウンロードリンクテーブル)
- gameid (ゲームID,int型)
- machineid　(対応機種ID,int型)
- link (ダウンロードリンク,string型)
#### machineInf(機種マスタ)
- machineid(対応機種ID,int型)
- machinename（対応機種,string型）
#### GameCategoryInf(カテゴリテーブル)
- gameid (ゲームID,int型)
- categoryid (カテゴリID,string型)
#### categoryInf(カテゴリマスタ)
- categoryid (カテゴリID,int型)
- categoryname (カテゴリ,string型)

### accounts

#### CustomUser

これでslackの認証結果を受け取る

- ハンドネーム
- メールアドレス
- generation（各自設定）
- user image（各自設定）

## 早稲田祭まで完成しなければならない機能

- フォーム申請＆取り消し
- スーパーユーザーで無理やりでもいい