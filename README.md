# cert-pages

## Overview

研修修了証（PDF）を GitHub Pages で公開するリポジトリです。
別リポジトリのGitHub Actions が `docs/` を自動生成します。
修了証は UUID ベースの URL でのみアクセス可能で、一覧ページは存在しません（検索エンジンにも非公開）。

## Tech Stack

- **GitHub Actions** — `docs/` の自動生成・コミット
- **GitHub Pages** — `docs/` を公開ホスティング（このリポジトリから直接配信）

## Prerequisites

- GitHub の公開リポジトリであること
- 別リポジトリの GitHub Actions からこのリポジトリへの write 権限を持つトークンが発行済みであること

## Setup

1. GitHub で Fine-grained PAT を作成し、発行元リポジトリのシークレットに登録

   | 項目 | 値 |
   |---|---|
   | Repository access | Only selected repositories → `co6tter/cert-pages` |
   | Contents | Read and write |
   | Metadata | Read |

2. Settings → Pages で **Source** を `docs/` フォルダに設定

## Usage

別リポジトリの GitHub Actions が `docs/` を更新すると、GitHub Pages に自動反映されます。

修了証は以下の URL でアクセスできます。

```
https://co6tter.github.io/cert-pages/c/{publicFile}
```

## Directory Structure

```
cert-pages/
├── docs/        # [生成物] GitHub Pages 公開ディレクトリ
├── .gitignore
└── README.md
```

## License

MIT
