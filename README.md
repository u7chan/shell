# Shell

カスタムシェルスクリプトの管理リポジトリ。

## インストール

```sh
git clone <リポジトリのURL>
cd shell
```

OSに応じてPATHを設定してください。

**Ubuntu:**

```sh
echo 'export PATH=$PATH:'"$(pwd)" >> ~/.bash_profile
source ~/.bash_profile
```

**macOS (Zsh):**

```sh
echo 'export PATH=$PATH:'"$(pwd)" >> ~/.zprofile
source ~/.zprofile
```

## コマンド一覧

```sh
$ hello
Available commands:
- dcprune
- devc-claude
- devc-cursor
- devc-share-bashrc
- gif
- sendkey
```

| コマンド | 説明 | 引数 |
|----------|------|------|
| `dcprune` | 未使用のDockerリソースを一括削除し、ネットワークのみを保持します。 | - |
| `devc-claude <CONTAINER> [USER]` | DevContainerにClaude CLIをインストール | `CONTAINER`: コンテナID<br>`USER`: ユーザー名（default: `vscode`） |
| `devc-cursor <CONTAINER> [USER]` | DevContainerにCursor CLIをインストール | `CONTAINER`: コンテナID<br>`USER`: ユーザー名（default: `vscode`） |
| `devc-share-bashrc <CONTAINER> [USER]` | `.bashrc.local`をコンテナに共有 | `CONTAINER`: コンテナID<br>`USER`: ユーザー名（default: `vscode`） |
| `gif <FILE> [WIDTH]` | 動画をGIFに変換 | `FILE`: mp4/movファイル<br>`WIDTH`: 幅（default: `600`） |
| `sendkey <CONTAINER> [USER]` | SSH秘密鍵をコンテナに注入 | `CONTAINER`: コンテナID<br>`USER`: ユーザー名（default: `root`） |

## 必要条件

| コマンド | 必要なもの |
|----------|-----------|
| `dcprune`, `devc-*`, `sendkey` | Docker |
| `gif` | ffmpeg |

## 環境変数

| 変数 | 説明 | デフォルト |
|------|------|------------|
| `CONTAINER_RUNTIME` | コンテナランタイム | `docker` |

> [!NOTE]
> `CONTAINER_RUNTIME`は、Docker互換のCLIを持つランタイム（Podmanなど）を使用する場合に設定してください。

```sh
# Podmanを使用する例
export CONTAINER_RUNTIME=podman
devc-claude <CONTAINER_ID>
```
