# cook-keep
### mimi-deploy
- デプロイ用にNginxコンテナ追加。
- ReactはビルドファイルをS3に置いてCloudFront経由でアクセス。nginx+DjangoはEC2。PostgresはRDSへ変更。
### mimi-deploy3
- reactでビルドしたdistファイルをnginxにて配信するように変更。 →リクエストは全てnginxで受け付けて、静的ファイルまたはDjangoコンテナへ振り分ける。
- reactのdomainEndpointは現在localhost. →適宜変更してからReactコンテナ内でbuildして、distファイルを作る。 →その後、nginx+Django+postgresのコンテナを起動する。
