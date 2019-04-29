# docker_rails_Quickstart_template
### rails + Mysql の環境をdockerで作った時に他のテンプレートで作ってもうまくいかなかったので自分で作りました。後述の「前提」に該当していて「使い方」の通りに操作すればrailsでの開発が始められる。。。ハズ

### 前提
- dockerがインストールされていること（されていない場合は[こちら](https://qiita.com/scrummasudar/items/750aa52f4e0e747eed68)
- cloneする(https://github.com/yosuke0517/docker_rails_Quickstart_template)

### 使い方
- `docker-compose run web rails new . --force --no-deps --database=mysql` (新規プロジェクト作成)
- `docker-compose build` (新規プロジェクト作成でGemfileが新しくなっているのでbuildする必要がある)
- db/config/database.ymlの`host`のvalueを`db`へ`username`のvalueを`root`へ変更（passwordとかは動かしたいだけならpasswordとかでいいと思います。）
- `docker-compose up`
- `docker-compose run web rake db:create` (初期起動時のみ)
- `http://localhost:3000`　へアクセスすればwelcomeページへ遷移する
