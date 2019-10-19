# Simple Heroku Mezamashi
GitHub Actionsを使って、Herokuアプリがスリープしないように設定できるか試してみるリポジトリです。

## cronはUTCで設定する
GitHub Actionsでcronを設定する場合、時間はUTCで設定する必要があります。
* https://help.github.com/en/articles/events-that-trigger-workflows#scheduled-events-schedule
