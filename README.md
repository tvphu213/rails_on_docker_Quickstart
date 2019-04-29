# rails_on_docker_Quickstart
# railsをdockerで環境構築するテンプレートを作成しました。
### rails + Mysql の環境をdockerで作った時に他のテンプレートで作ってもうまくいかなかったので自分で作りました。後述の「前提」に該当していて「使い方」の通りに操作すればrailsでの開発が始められます。
- Macでの動確は済
- Windows環境での動作検証は行なっておりませんので悪しからず

### 前提
- dockerがインストールされていること（されていない場合は[こちら](https://qiita.com/scrummasudar/items/750aa52f4e0e747eed68)

### 使い方
- cloneする(https://github.com/yosuke0517/rails_on_docker_Quickstart)
- `docker-compose run web rails new . --force --no-deps --database=mysql` (新規プロジェクト作成)
- `docker-compose build` (新規プロジェクト作成でGemfileが新しくなっているのでbuildする必要がある)
- db/config/database.ymlの`host`のvalueを`db`へ`username`のvalueを`root`へ変更（passwordとかは任意で変更願います。）
- `docker-compose up`
- 別のターミナルを開き`docker-compose run web rake db:create` (初期起動時のみ)
- `http://localhost:3000`　へアクセスすればwelcomeページへ遷移する
