# rustcoder
RustでAtCoderに参加する際のローカル環境を快適にするためのCLIツール。

何番煎じかは知りませんが、Rustの勉強がてら自分で実装してみたいと思った次第です。

# Features

実装予定の機能 / **TODO**

- [x] ワークスペースを新規作成
    - [x] `target` を共有するための `.cargo/config.toml` を生成
    - [x] Gitリポジトリ初期化
    - [x] `.gitignore`を生成
- [x] コンテスト用のcargoパッケージ生成

# Usage

```
$ rustcoder help
rustcoder 0.1.0
Convenient toolchain for AtCoder written in Rust

USAGE:
    rustcoder <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    help     Print this message or the help of the given subcommand(s)
    init     Create workspace for AtCoder
    start    Cerate new workspace for specified contest
```

## ワークスペース初期化

```
$ rustcoder init [directory]
```

default: atcoder_workspace

以下のことを行う。

- コンテストごとのcargoパッケージを並べるためのワークスペース生成
- Gitリポジトリ初期化
- `target`を共有するための `.cargo/config.toml`などを生成。

## コンテスト用のプロジェクト作成

```
$ rustcoder start <contest-name>
```

該当コンテストページから必要な情報をスクレイピングによって抽出し、適切に生成する。
