
# マルチステージビルド＝Goプログラムをビルド
FROM golang:1.18 as build

# 作業ディレクトリを設定＝このディレクトリは、コンテナ内での作業ディレクトリ
WORKDIR /go/src/app

# Goの依存関係をコピー＝現在のディレクトリ（Dockerfileがあるディレクトリ）からコンテナ内の作業ディレクトリにコピー
COPY go.mod ./

# 依存関係をダウンロード=ビルド時に必要なパッケージが取得される
RUN go mod download

# ソースコードをコピー＝main.goファイルを、コンテナ内の作業ディレクトリにコピー
COPY main.go .

EXPOSE 8080

RUN go build -o main .

CMD ["./main"]
# コンテナ内で実行するコマンド
