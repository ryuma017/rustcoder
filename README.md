# AtCoder Tools for Rust
RustでAtCoderに参加する際のローカル環境を快適にするためのコマンドラインツール。

何番煎じかは知りませんが、Rustの勉強がてら自分で実装してみたいと思った次第です。


## Features

実装予定の機能

・*マスト(できそうなやつ)*
- [ ] テストケースデータの抽出
    - [ ] ローカルテスト
    - [ ] ローカルデバッグ

・*できたら(難しそう)*
- [ ] ワークスペースを新規作成
    - [ ] GitHubへの自動プッシュスクリプト生成
    - [ ] `target` を共有するための `.cargo/config.toml` を生成。
- [ ] コンテスト用のプロジェクトファイル生成
- [ ] AtCoderへのログイン(セッション情報を保存)
- [ ] 解答提出

テスト&デバッグくらいしかできなそうやけど大丈夫かしら^^


## Usage

使用イメージ(予定)

---

### テストケース抽出

ローカルテスト or デバッグの実行毎に抽出する。
初回実行時にローカルに保存したほうがいいのか迷う。

---

### ローカルテスト

```
$ rustcoder test <problem-id>
```

問題ページから入出力例を抽出して、テストを行う

---

### ローカルでバッグ

```
$ rustcoder dbg <problem-id>
```

問題ページから入出力例を抽出して、デバッグを行う

---

以上、なんとかできそうなやつ。

以下、難しそうなやつ。できたらやる。

---

### ワークスペース初期化

```
$ rustcoder init <language>
```

以下のことを行う。

- コンテストごとのプロジェクトを並べるためのワークスペース生成
- Gitリポジトリ、自動プッシュスクリプト の生成
- `target`を共有するための `.cargo/config.toml`などを生成。

---

### ログイン

```
$ rustcoder login
```

実行後、ユーザー名・パスワードの入力を要求する。
HTTPのセッション情報を保存(ログイン情報は保存しない)。

---

### コンテスト用のプロジェクト作成

```
$ rustcoder start <contest-name>
```

該当コンテストページから必要な情報をスクレイピングによって抽出し、適切に生成する。
