# wordpress-tutorial
WordPress の練習用レポジトリ  
参考: [クィックスタート: Compose と WordPress — Docker\-docs\-ja 17\.06 ドキュメント](https://docs.docker.jp/compose/wordpress.html)

# Docker，Docker Composeのインストール
[Install Docker Engine \| Docker Documentation](https://docs.docker.com/engine/install/)  
[Install Docker Compose \| Docker Documentation](https://docs.docker.com/compose/install/)

# 開発環境での実行
環境ファイルの作成
```bash
cp .env.local .env
```

起動

```bash
docker-compose up -d
```

停止

```bash
docker-compose down
```

# 本番環境へのデプロイ

