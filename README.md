# TISCON2-SIGCOLLE

##背景

各社SIerのネットワーク環境は情報セキュリティーを守るという名目で環境が規制されています。  
しかし、規制がいきすぎており、エンジニアたちは開発に必要な情報まで制限されているというツラい環境。。  
そんなとき、T社の1人のエンジニアが立ち上がりました。  

>**開発に必要なサイトはプロキシでのブロックをやめたい！**  

アプリを使って社内で賛同者を募ったところ、たちまち賛同者が集まりました。  
その結果、T社のプロキシは緩和され、エンジニアに必要なサイトの閲覧ができるようになってきました。  

※この物語はノンフィクションです


##今回の依頼


T社のエンジニアが作ったアプリは  
**社員の声を集めて偉い人にかけあうツール**として武器になることが分かりました。  
そこで、このアプリをもっと社内のいろんなボトムアップの改善に使っていきたいと考えています。  

1つのキャンペーン(プロキシでのブロックをやめたい)を実施しているアプリがあります。  
**君たちの力で機能を追加し、ユーザが誰でも自由に新しいキャンペーンを作れる**システムに作りかえてください。  


## 環境構築

下記リンクtiscon2-startup-guide内のREADMEを参考に、環境構築をしてください。  
[【tiscon2-startup-guide】](https://github.com/tiscon/tiscon2-startup-guide)

ローカル上での動作確認まで終わったら、オンライン上での動作確認をします。  
Herokuにログインした状態で、下のDeploy to Herokuボタンを押下してください。  

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)  

HerokuのDeployページが開くので、画面のDeployボタンを押下してください。  
その際、App Name (optional)及びRuntime Selectionの項目を入力・変更する必要はありません。  
(TISCONアプリケーションがHeroku上でビルド・動作します。)  

Deploy to Herokuにチェックがついたら右下のViewボタンを押下してください。  
SIGCOLLEの画面が表示されたら想定通りの挙動です。  

## 提供機能(2017/2/1現在)
本アプリケーションで提供されているのは以下の機能です。  
- ログイン機能
- ログアウト機能
- キャンペーン一覧表示機能
- ユーザ登録機能
- キャンペーンに賛同する機能


## 更新を検知する方法
機能の追加、修正（プログラムの修正）が行われる場合があります。  
GithubのWatch機能を使用すれば、プログラムの修正があった場合、登録したメールアドレスに通知メールが来るようになります。  
各リポジトリページの右上にある「Watch」ボタンを押下し、プルダウンからWatchingを選択してください。  
そうするとWatch機能が有効になります。  


## 更新の取り込み方
更新の通知を受け取ったら、https://github.com/tiscon/tiscon2 からForkしてきた自身の環境へ更新内容を取り込みます。  

更新の取り込み方は[更新手引き](doc/UpdateGuide.md)を参照してください。


<br>

# 参考
## 本プロジェクトの構成


```

tiscon2

└ src

 └ main

    ├ java

    │├ db.migration       #DBスキーマ、事前登録データの定義情報

    │└ net.unit8.sigcolle

    │  ├ auth             #認証情報

    │  ├ controller       #リクエスト内容がURLマッチした時に実行されるコントローラー

    │  ├ dao              #DBアクセス

    │  ├ form             #画面からリクエストされた内容を保持する

    │  ├ model            #DBから取得した情報を保持する

    │  ├ SigColleApplicationFactory.java     # ルート定義とmiddleware定義

    │  └ SigColleSystemFactory.java          # システムが利用するコンポーネントの定義

    └ resources

      ├ META-INF                   #アプリケーションが公開する静的リソース

      ├ net.unit8.sigcolle.dao   #Daoに対応するSQLファイル

      ├ public                     #アプリケーションが公開する静的リソース

      └ template                   #画面表示する内容

```


---
## 使用技術
### Enkan
本アプリケーションはマイクロフレームワーク『Enkan』を使用して構築されています。  
Enkanについて学びたい方は、以下を参考にしてください。
- [Getting Started(スタートガイド)](https://enkan.github.io/getting-started.html)
- [マイクロフレームワークEnkan(とKotowari)ではじめるREPL駆動開発](http://www.slideshare.net/kawasima/enkankotowarirepl)


### Semantic UI
本アプリケーションの画面レイアウトには、デザインフレームワークSemantic UIを使用しています。  
Semantic UIについて学びたい方は、以下を参考にしてください。
- [Getting Started(スタートガイド)](http://semantic-ui.com/introduction/getting-started.html)
　※左側のメニューから、各UI部品の解説・サンプル実装ページへ移動できます。

### Thymeleaf
ThymeleafはJavaのテンプレートエンジンライブラリです。  
Thymeleafについて学びたい方は、以下を参考にしてください。
- [Thymeleafチュートリアル](http://www.thymeleaf.org/doc/tutorials/2.1/usingthymeleaf_ja.html)


### Java API
Javaで提供している標準のAPIです。  
- [Java 8 API仕様](https://docs.oracle.com/javase/jp/8/docs/api/)

### HTMLリファレンス
本アプリケーションの画面を構成している技術要素です。  
- [HTMLタグリファレンス](http://www.htmq.com/html/indexm.shtml)
- [CSSリファレンス](http://www.htmq.com/style/index.shtml)
