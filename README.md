# Herokuめざまし
GitHub Actionsを使って、Herokuにデプロイしたアプリを15時間30分起きるようにして、8時間30分スリープさせるリポジトリです。アプリを起動させる時間はJSTで9:00〜0:30に設定していて、20分ごとに`curl`コマンドを実行して、アプリを起こすようにしています。publicリポジトリで運用する場合、完全無料で運用することができます。

## Herokuの無料枠
Herokuの無料枠はデフォルトで550時間与えられます。Herokuにクレジットカード登録をすると、Herokuの無料枠は1000時間になります。

## 使い方
このリポジトリをforkして、secretsの値を設定して、使用することができます。

### secretsでAPP_URLを設定する
アプリのURLはGitHub Actionsの[secrets](https://help.github.com/ja/github/automating-your-workflow-with-github-actions/virtual-environments-for-github-actions#creating-and-using-secrets-encrypted-variables)で設定するようにしました。理由はアプリのURLを公開したくない人もいると思ったためです。secretsで設定すると、実行結果は以下のように表示されます。  
![スクリーンショット 2019-10-22 12 09 17](https://user-images.githubusercontent.com/39484102/67257037-d244c380-f4c4-11e9-9620-55063b1d8c05.png)

secretsの設定方法は以下の通りです。
![2019-10-22 11 52 18](https://user-images.githubusercontent.com/39484102/67256887-52b6f480-f4c4-11e9-84c9-ba152939070c.gif)

### 起動時間を変更する場合
cronの設定を変更して、スリープさせない時間をカスタマイズすることができます。GitHub Actionsでcronを設定する場合、時間はUTCで設定する必要があります。デフォルトではUTCで0:00〜15:00で設定しています。（JSTの9:00〜0:00）
* https://help.github.com/en/articles/events-that-trigger-workflows#scheduled-events-schedule

### 起動時間が15時間30分である理由
9:00からアプリを起動させて、0:00に最後の`curl`を実行して30分起こすため、起動時間が15時間30分となっています。
