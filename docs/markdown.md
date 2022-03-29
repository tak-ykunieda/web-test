<link href="../@css/github-markdown.css" rel="stylesheet"></link>

# 院内サーバセットアップ手順

## クラウド版カルテを利用するまでの流れ
クラウド版カルテを利用する際は、以下の順に作業を行い利用開始してください
```
　[導入] 施設コードの申請
　　　　　↓
　[開発] クラウド情報の払出し
  　　　　↓
　[開発] クラウド環境作成
　　  　　↓
　[導入] 院内NASのセットアップ
　　　　　↓
　[導入] 院内サーバのセットアップ
　　　　　↓
　[導入] 院内クライアントのセットアップ
```

## 施設コードの申請
クラウド版電子カルテを利用する施設は申請をいただくことで以下の情報を払い出します  
※申請先は今の所`「大脇」`としています

- クラウド用グループコード
- クラウド用施設コード
- ライセンスコード
- クラウド接続用の証明書

## 院内サーバセットアップ資源
格納場所
```
\\192.168.61.23\share300\303_ＨＣシ事シスソリＢＵ\01_利用者限定\25 カルテT\10 共通\90_セットアップ\SVセットアップ\クラウド院内SV\01_院内サーバインストーラー
```
院内サーバ端末のデスクトップにフォルダごとコピーして利用してください
```
C:\Users\KarteUser\Desktop\01_院内サーバインストーラー
```

## windowsのセットアップ
> windowsのバージョン、パソコンメーカ・機種により画面が一部異なります  

| 画像                                          | 説明                                                                                                                                                                         |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img width="300" alt="" src="img/win-1.png">  | `日本`を選択して`はい`をクリック                                                                                                                                             |
| <img width="300" alt="" src="img/win-2.png">  | `はい`をクリック                                                                                                                                                             |
| <img width="300" alt="" src="img/win-3.png">  | `スキップ`をクリック                                                                                                                                                         |
| <img width="300" alt="" src="img/win-4.png">  | `組織用に設定`を選択して`次へ`をクリック                                                                                                                                     |
| <img width="300" alt="" src="img/win-5.png">  | `代わりにドメインに参加する`をクリック                                                                                                                                       |
| <img width="300" alt="" src="img/win-6.png">  | `名前`に`KarteUser`を入力して`次へ`をクリック                                                                                                                                |
| <img width="300" alt="" src="img/win-7.png">  | `パスワード`に`AppUser00`を入力して`次へ`をクリック                                                                                                                          |
| <img width="300" alt="" src="img/win-8.png">  | `パスワードの確認入力`に`AppUser00`を入力して`次へ`をクリック                                                                                                                |
| <img width="300" alt="" src="img/win-9.png">  | `セキュリティの質問`から最初の選択肢を選択後、`答え`に`tak`と入力して`次へ`をクリック<br>同様の作業を３回実施                                                                |
| <img width="300" alt="" src="img/win-10.png"> | 変更せずに`同意`をクリック                                                                                                                                                   |
| <img width="300" alt="" src="img/win-11.png"> | `今は実行しない`をクリック                                                                                                                                                   |
| <img width="300" alt="" src="img/win-12.png"> | Microsoft EdgeでWebを閲覧画面の`始める`をクリック                                                                                                                            |
| <img width="300" alt="" src="img/win-13.png"> | `完全セットアップ`をクリック                                                                                                                                                 |
| <img width="300" alt="" src="img/win-14.png"> | `サインインしないで続行`をクリック                                                                                                                                           |
| <img width="300" alt="" src="img/win-15.png"> | `「×」`でMicrosoft Edgeを終了                                                                                                                                                |
| <img width="300" alt="" src="img/win-16.png"> | スタートメニューから`設定`をクリック                                                                                                                                         |
| <img width="300" alt="" src="img/win-17.png"> | 画面を一番下部までスクロールし、`Windowsがライセンス認証されていません。今すぐWindowsをライセンス認証してください。`をクリック<br>ライセンス認証されるまでしばらく待機します |
| <img width="300" alt="" src="img/win-17.png"> | 画面を一番下部までスクロールし、`Windowsがライセンス認証されていません。今すぐWindowsをライセンス認証してください。`をクリック<br>ライセンス認証されるまでしばらく待機します |


## 端末名の設定
端末名は以下のように設定してください<br>
| 区分           | 端末名   |
| -------------- | -------- |
| メインサーバ   | TAKSV001 |
| レプリカサーバ | TAKSV003 |

上記以外の端末名はセットアップが行えません<br>


## 院内NASのセットアップ
### NAS本体の構築

以下の手順を元にNAS本体にHDDを装着します

| 画像                                         | 説明                                                                                  |
| -------------------------------------------- | ------------------------------------------------------------------------------------- |
| <img width="200" alt="" src="img/nas-1.png"> | 本体を取り出し、正面のカバーを引っ張り外します                                        |
| <img width="200" alt="" src="img/nas-2.png"> | `「Push」`ボタンを押しながらHDDマウントケースを取出します                             |
| <img width="200" alt="" src="img/nas-3.png"> | HDDマウントケースの側面にあるロックを外します                                         |
| <img width="200" alt="" src="img/nas-4.png"> | HDDを装着し、HDDマウントケース側面のロックを付けます                                  |
| <img width="200" alt="" src="img/nas-5.png"> | HDDマウントケースを本体に戻します。「`▲UP`」を目印にし、上下をあわせてください        |
| <img width="200" alt="" src="img/nas-6.png"> | 本体背面の`「LAN1」`にインターネットに接続できるLANを接続し、電源ゲーブルも接続します |
| <img width="200" alt="" src="img/nas-7.png"> | 本体前面のカバーを戻し、電源ボタンを押下します                                        |

### NASの初期セットアップ
NASセットアップURLを起動します  
```
01_院内サーバインストーラー
├─@NAS
│  │- NASセットアップURL.url
```

`接続`をクリックします  
<img width="400" alt="" src="img/nas-setting-1.png">

`私はEULAの条件を読み、これに同意します`にチェックを入れ、`次へ`をクリックします  
<img width="400" alt="" src="img/nas-setting-2.png">

`続行`をクリックします  
<img width="400" alt="" src="img/nas-setting-3.png">

`設定`をクリックします  
<img width="400" alt="" src="img/nas-setting-4.png">

`今すぐインストール`をクリックします  
<img width="400" alt="" src="img/nas-setting-5.png">

`これらのハードディスクに保管されているすべてのデータが削除されることを理解しました`にチェックを入れ、`OK`をクリックします  
<img width="400" alt="" src="img/nas-setting-6.png">

インストールが完了し、再起動が完了するまで待機します(10分ほど)  
<img width="400" alt="" src="img/nas-setting-7.png">
<img width="400" alt="" src="img/nas-setting-8.png">

再起動後、画面が表示されたら`起動`をクリックします<br>
<img width="400" alt="" src="img/nas-setting-19.png">

管理者アカウント情報を入力して`次へ`をクリックします  
  - デバイス名：TAKNAS
  - 管理者アカウント：KarteUser
  - パスワード：AppUser00
  - パスワードの確認：AppUser00

<img width="400" alt="" src="img/nas-setting-20.png">

`DSM またはパッケージのアップデートが利用可能になったら私に通知してもらえれば、私は手動でインストールできます`を選択し、`次へ`をクリックします<br>
<img width="400" alt="" src="img/nas-setting-21.png">

`アカウントをお持ちですか？今すぐサインイン。`のリンクをクリックします<br>
<img width="400" alt="" src="img/nas-setting-22.png">

以下の情報でSynologyアカウントにサインインします<br>
　Synologyアカウント：tak-karte_support@taknet.co.jp  
　パスワード：Tak756532!  
<img width="400" alt="" src="img/nas-setting-11.png">

`中国でSynology QuickConnect。。。`のポップアップで`OK`をクリックします<br>
<img width="400" alt="" src="img/nas-setting-24.png">

何も選択せずに`送信`をクリックします<br>
<img width="400" alt="" src="img/nas-setting-25.png">

`今すぐ作成`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-1.png">

`起動`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-2.png">

RAIDタイプから`RAID1`を選択して`次へ`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-3.png">

全てのディスクを選択して`次へ`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-4.png">

`続行`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-5.png">

`ドライブチェックをスキップする`選択して`次へ`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-6.png">

`最大`をクリックしてから`次へ`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-7.png">


`Btrfs`を選択して`次へ`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-8.png">

`適用`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-9.png">

`OK`をクリックします<br>
<img width="400" alt="" src="img/nas-raid-10.png">

ストレージプール、ボリューム共に`正常`と表示されたら`×`でストレージマネージャ画面を終了します<br>
<img width="400" alt="" src="img/nas-raid-11.png">


### NASの設定を復元
初期設定値を設定ファイルから復元します  

コントロールパネルから`更新と復元`を選択します  
> NAS管理画面 > コントロールパネル > 更新と復元 > 設定のバックアップ  

`DSM構成を復元する`から`復元`をクリックします  
<img width="400" alt="" src="img/nas-repair-1.png">

NAS初期値設定ファイルを選択し、`次へ`をクリックします  
```
01_院内サーバインストーラー
├─@NAS
│  ├─NAS設定ファイル
│  │    │- NASSetting.dss
```
<img width="400" alt="" src="img/nas-repair-2.png">

`上書き競合設定`と`全システムの構成`にチェックを入れ、`完了`をクリックします  
<img width="400" alt="" src="img/nas-repair-3.png">

`はい`をクリックします  
<img width="400" alt="" src="img/nas-repair-4.png">


### メール通知の設定
NAS故障時にメール通知が行われるように設定を行います  

コントロールパネルから`通知`を選択します  
> NAS管理画面 > コントロールパネル(上級者モード) > 通知

`電子メール`ページの設定を以下のように変更し、`適用`をクリックします<br>
  - 電子メール通知を有効にするにチェックを入れる<br>
  - 受信者のEメールアドレス：`tak-karte_alert@taknet.co.jp`<br>
  - 対象接頭辞：`taknas%クラウド用施設コード%-%施設名%`<br>
        例）クラウド用施設コード：00010<br>
        　　施設名：タッククリニック<br>
        　　対象接頭辞：taknas00010-タッククリニック<br>
  - サービスプロバイダ：`カスタムSMTPサーバー`<br>
  - SMTPサーバー：`smtp-mail.outlook.com`<br>
  - SMTPポート：`587`<br>
  - 認証が必要：`チェック`<br>
  - ユーザ名：`tak-karte@outlook.jp`<br>
  - パスワード：`Tak756532!`<br>
  - 安全な接続(SSL/TLS)が必要：`チェック`<br>
  - 送信者の名前：`タック電子カルテクラウド`<br>
  - 送信者の電子メール：`tak-karte@outlook.jp`<br>

`適用`ボタンクリック後に`テストメールの送信`をクリックします
> 認証メールの受信確認は`大脇`にて実施を行いますので、声をかけてください    
> テストメール送信時にOutlookの認証エラーで送信エラーが発生する可能性があります  
> その際は`大脇`にて認証処理を行いますので、声をかけてください  

<img width="400" alt="" src="img/nas-mail-1.png">
<img width="400" alt="" src="img/nas-mail-2.png">


### DDNSの設定
NASにQuickConnect・DDNSの設定を行い、生存確認を行えるようにします

コントロールパネルから`外部アクセス`を選択します  
> NAS管理画面 > コントロールパネル(上級者モード) > 外部アクセス

`QuickConnect`ページを以下のように変更し、`適用`をクリックする<br>
 - `QuickConnect を有効にする`にチェックを入れる<br>
 - QuickConnect IDに`TAKNAS%クラウド用施設コード%`を入力する<br>
        例）クラウド用施設コード：00010<br>
        　　ホスト名：TAKNAS00010<br>

<img width="400" alt="" src="img/nas-ddns-1.png">

`DDNS`ページを開き、`追加`ボタンをクリックします  
<img width="400" alt="" src="img/nas-ddns-2.png">

`DDNS`ページの設定を以下ようにに変更し、`OK`ボタンをクリックします  
  - サービスプロバイダー：`Synology`
  - ホスト名：`TAKNAS-%クラウド用施設コード%`  
        例）クラウド用施設コード：00010  
        　　ホスト名：TAKNAS-00010  
  - Heartbeat：有効  

<img width="400" alt="" src="img/nas-ddns-3.png">


### WOLの設定
NASの電源をリモートでONにする設定を行います  

コントロールパネルから`ハードウェアと電源`を選択します  
> NAS管理画面 > コントロールパネル(上級者モード) > ハードウェアと電源

`全般`ページの設定を以下のように変更し、`適用`をクリックします  
  - 電源復旧欄の`電源の問題が修正されたときに自動的に再起動する`にチェックを入れる
  - 電源復旧欄の`WOL を LAN 1で有効にする`にチェックを入れる

WOLはIPアドレスとMACアドレスを使用してリモートで電源を入れる仕組みです  
パソコンにも同じ仕組みが用意されていますので、使いたい方はネットで調べてください  

<img width="400" alt="" src="img/nas-hardware-1.png">


### IPアドレスの設定
現地のIPアドレスを設定します  

コントロールパネルから`ネットワーク`を選択します  
> NAS管理画面 > コントロールパネル(上級者モード) > ネットワーク

  - `ネットワークインターフェース`ページを開き`LAN 1`を選択します
  - `編集`をクリックします
  - `手動で設定する`を選択し、現地の設定を入力する
  - `OK`をクリックします

<img width="400" alt="" src="img/nas-net-1.png">
<img width="400" alt="" src="img/nas-net-2.png">


### 監視ソフトのインストール資源をアップロード
院内サーバを監視するソフトをインストール資源をアップロードします  

`File Station`画面をを起動します  
> NAS管理画面 > メニュー > File Station

画面左部のツリーから`docker`を選択します  
インストール資源の`docker設定ファイル`フォルダ内のフォルダ・ファイルを`docker`へドラッグドロップでアップロードします  
```
01_院内サーバインストーラー
├─@NAS
│  ├─docker設定ファイル
│  │    ├─zabbix
│  │    │   ├─usr
│  │    │   │  │- ...
│  │    │   ├─var
│  │    │   │  │- ...
│  │    │- zabbix-agent2.json
│  │    │- zabbix-proxy.json
```
<img width="700" alt="" src="img/nas-docker-copy-1.png">

アップロード時に上書き確認が表示されますので`上書き`を選択  
<img width="400" alt="" src="img/nas-docker-copy-2.png">

zabbixフォルダの権限を変更する為、zabbixフォルダを選択し、`操作 > プロパティ`を選択します  
<img width="400" alt="" src="img/nas-docker-copy-3.png">

`許可`ページを開き、`詳細オプション > 継承権限を明確にする`を選択します  
<img width="400" alt="" src="img/nas-docker-copy-4.png">

ユーザ内から`Everyone`を選択し`編集`をクリックします  
<img width="400" alt="" src="img/nas-docker-copy-5.png">

`Everyone`を`読込み/書込み`に変更し`OK`をクリックします  
<img width="400" alt="" src="img/nas-docker-copy-6.png">

`このフォルダ、サブフォルダ、ファイルに適用する`にチェックを入れて`保存`をクリックします  
<img width="400" alt="" src="img/nas-docker-copy-7.png">


### 監視ソフトのインストール
院内サーバを監視するソフトを実行するソフトをダウンロードします  

`パッケージセンター`画面をを起動します  
> NAS管理画面 > パッケージセンター

`私はパッケージセンターのサービス規約を読み、これに同意します`にチェックを入れ、`OK`をクリックします  
<img width="400" alt="" src="img/nas-docker-1.png">

検索ボックスに`docker`と入力し、`Docker`をインストールした後、`Docker`を開きます  
<img width="400" alt="" src="img/nas-docker-2.png">
<img width="400" alt="" src="img/nas-docker-3.png">

`今後このメッセージを表示しない`にチェックを付け、`×`で閉じる  
<img width="400" alt="" src="img/nas-docker-4.png">

レジストリメニューを開き、検索ボックスに`zabbix-proxy-sqlite`と入力し、`zabbix/zabbix-proxy-sqlite3`をダブルクリックする  
<img width="400" alt="" src="img/nas-docker-5.png">

タグの選択で`5.4.2-alpine`を選択し、`選択`をクリックする  
<img width="400" alt="" src="img/nas-docker-6.png">

検索ボックスに`zabbix-agent2`と入力し、`zabbix/zabbix-agent2`をダブルクリックする  
<img width="400" alt="" src="img/nas-docker-7.png">

タグの選択で`5.4.2-alpine`を選択し、`選択`をクリックする  
<img width="400" alt="" src="img/nas-docker-8.png">

コンテナメニューを開き、`設定 > インポート`をクリックする  
<img width="400" alt="" src="img/nas-docker-9.png">

`zabbix-proxy.json`を選択し、`選択`をクリックする  
<img width="400" alt="" src="img/nas-docker-10.png">

コンテナ名に`zabbix-proxy`と入力し、`OK`をクリックする  
<img width="400" alt="" src="img/nas-docker-11.png">

コンテナメニューを開き、`設定 > インポート`をクリックする  
<img width="400" alt="" src="img/nas-docker-12.png">

`zabbix-agent2.json`を選択し、`選択`をクリックする  
<img width="400" alt="" src="img/nas-docker-13.png">

コンテナ名に`zabbix-agent2`と入力し、`OK`をクリックする  
<img width="400" alt="" src="img/nas-docker-14.png">

コンテナ一覧から`zabbix-proxy`を選択し、`編集`をクリックする  
<img width="400" alt="" src="img/nas-docker-15.png">

`環境`ページを選択し、`ZBX_HOSTNAME`の値を`TAKNAS%クラウド施設用コード%`に修正後、`適用`をクリック  
例）クラウド用施設コード：00010  
　　ZBX_HOSTNAME：TAKNAS00010  
<img width="400" alt="" src="img/nas-docker-16.png">

コンテナを以下の順に起動する<br>
 1. zabbix-proxy<br>
 2. zabbix-agent2<br>

<img width="400" alt="" src="img/nas-docker-17.png">


## 院内サーバのセットアップ

注意事項  
 - 端末がインターネットに接続できる状態でセットアップを行ってください  
 - セットアップ後のIPでNASと通信が可能なLANでセットアップを行ってください  


### インストーラーの実行
クラウド接続用の証明書をインストーラー内に配置してください
> 証明書の名称は施設によって異なります
```
01_院内サーバインストーラー
│- takvpn001_1.p12
```

院内サーバのインストーラーを実行します
```
01_院内サーバインストーラー
│- SetupTerminalInfoSV.exe

```
サーバ情報の入力画面が表示されますので、現地設定を入力し、`確定`をクリックします  

| 区分                   | 項目                   | 説明                                                                   |
| :--------------------- | :--------------------- | :--------------------------------------------------------------------- |
| クラウド設定           | クラウドグループ       | クラウド用グループコード                                               |
|                        | 施設コード             | クラウド用施設コード                                                   |
| 院内ネットワーク設定   | アダプタ               | 有線LANのアダプタ名を選択                                              |
|                        | IPアドレス(メイン)     | メインサーバのIPアドレスを入力  (レプリカサーバのセットアップ時も必要) |
|                        | IPアドレス(レプリカ)   | レプリカサーバのIPアドレスを入力  (メインサーバのセットアップ時も必要) |
|                        | サブネット             | サブネットマスクを入力                                                 |
|                        | デフォルトゲートウェイ | デフォルトゲートウェイを指定  (未使用の場合は未入力)                   |
|                        | DNS                    | DNSサーバのIPアドレスを入力  (セカンダリを未使用の場合は未入力)        |
| その他ネットワーク設定 | NAS IPアドレス         | NASのIPアドレスを入力                                                  |

<img width="300" alt="" src="img/sv-1.png">　<img width="300" alt="" src="img/sv-2.png">

セットアップ情報の確認とサーバ種別の選択画面が表示されますので、画面に従い`メインサーバ`か`レプリカサーバ`かを入力します  
<img width="300" alt="" src="img/sv-3.png">

１時間程で下記の画面となり、セットアップが完了します  
> セットアップ中は複数回再起動が行われます  

<img width="300" alt="" src="img/sv-4.png">


### 共有フォルダのパスワード保護を無効化
共有の詳細設定を開きます
> コントロール パネル > ネットワークとインターネット > ネットワークと共有センター > 共有の詳細設定

`パスワード保護共有を無効にする`を選択し、`変更の保存`をクリックします

<img width="300" alt="" src="img/sv-share-1.png">


### 不要アプリケーションの削除
プログラムと機能を開きます
> コントロール パネル > プログラムのアンインストール

HP製のアプリケーション、ウイルス対策アプリケーションの削除を行います<br>
出荷時期、型番によってインストールされているアプリケーションが違いますので、適宜読み替えて対応下さい<br>

<img width="400" alt="" src="img/uninstall-1.png">
<img width="400" alt="" src="img/uninstall-2.png">


