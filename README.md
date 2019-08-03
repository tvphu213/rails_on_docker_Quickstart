# rails_on_docker_Quickstart
# railsをdockerで環境構築するテンプレートを作成しました。
### rails + Mysql の環境をdockerで作った時に他のテンプレートで作ってもうまくいかなかったので自分で作りました。後述の「前提」に該当していて「使い方」の通りに操作すればrailsでの開発が始められます。
- Macでの動確は済
- Windows環境での動作検証は行なっておりませんので悪しからず

### 前提
- dockerがインストールされていること（されていない場合は[こちら](https://qiita.com/scrummasudar/items/750aa52f4e0e747eed68)

### 使い方
#### Qiitaにまとめました [[こちら]](https://qiita.com/sukezane/items/ad97e24c450e117f8eaf)
- 1.`clone`する(https://github.com/yosuke0517/rails_on_docker_Quickstart)
- 2.`docker-compose run web rails new . --force --no-deps --database=mysql` (新規プロジェクト作成)
- 3.`docker-compose build` (新規プロジェクト作成でGemfileが新しくなっているのでbuildする必要がある)
- 4.db/config/database.ymlの`host`のvalueを<font color="Crimson">db</font>へ`username`のvalueを<font color="Crimson">root</font>へ変更（passwordとかは任意で変更願います。）
- 5.`docker-compose up`
- 6.別のターミナルを開き`docker-compose run web rake db:create` (初期起動時のみ)
- 7.`http://localhost:3000`　へアクセスすればwelcomeページへ遷移する
