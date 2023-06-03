
# マルチステージビルド＝Goプログラムをビルド
FROM golang:1.18 as build

# 作業ディレクトリを設定＝このディレクトリは、コンテナ内での作業ディレクトリ
WORKDIR /go/src/app

# Goの依存関係をコピー＝現在のディレクトリ（Dockerfileがあるディレクトリ）からコンテナ内の作業ディレクトリにコピー
#COPY go.mod ./

# 依存関係をダウンロード=ビルド時に必要なパッケージが取得される


# ソースコードをコピー＝main.goファイルを、コンテナ内の作業ディレクトリにコピー
COPY . .
RUN go mod download

RUN go build -o /go/bin/app

CMD ["/go/bin/app"]
# コンテナ内で実行するコマンド
EXPOSE 8080
