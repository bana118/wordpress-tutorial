# wordpress-tutorial
WordPress の練習用レポジトリ  
参考: [クィックスタート: Compose と WordPress — Docker\-docs\-ja 17\.06 ドキュメント](https://docs.docker.jp/compose/wordpress.html)

# Docker，Docker Composeのインストール
[Install Docker Engine \| Docker Documentation](https://docs.docker.com/engine/install/)  
[Install Docker Compose \| Docker Documentation](https://docs.docker.com/compose/install/)
## CentOS
### Docker のインストール
```bash
sudo yum install -y yum-utils
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install -y docker-ce docker-ce-cli containerd.io
```

### Docker Composeのインストール
```bash
sudo yum install -y curl
sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

### dockerコマンドの権限設定
```bash
sudo usermod -a -G docker ${username}
```
一度ログアウトして再度ログイン

# How to get started
## 開発環境での実行
```bash
git clone https://github.com/bana118/wordpress-tutorial.git
```

### 環境ファイルの作成

```bash
cp .env.local .env
```

### 起動

```bash
docker-compose up -d
```

### 停止

```bash
docker-compose down
```

## 本番環境へのデプロイ
```bash
git clone https://github.com/bana118/wordpress-tutorial.git
cd wordpress-tutorial
```

### 環境ファイルの作成
```bash
cp .env.production .env
```

### ドメインの設定
example.com を自身のホスト名に変更
```bash
vi .env
```

### ファイルの権限設定
`${www-data-id}` はwordpressのdockerコンテナ内のwww-dataユーザーのユーザーID．  
`docker-compose up -d`の後にwordpressディレクトリ以下に生成されるファイルの所有権を確認するかコンテナ内の/etc/passwd を確認する．
```bash
sudo chown -R ${www-data-id} wordpress/
```

### 起動

```bash
docker-compose up -d
```
