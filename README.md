# WAKUWAKU inc. LLM Agent StartKit: LLM Agent スタートキット

## Overview: 概要

WAKUWAKU Inc. において、LLM Agent を利用した、自動化タスクを作成する為のスターターキットです。

このスターターキットは、LLM Agentを利用して、日常的に行うタスクを自動化するためのものです。

IDEを利用したLLM Agentの実行をサポートします。

WAKUWAKUではGoogle Workspaceを利用しているため、Gemini CLIを使って無料で利用可能です。

以下いずれかの統合開発環境 ( IDE )での利用を想定しています。

- 無料で利用可能
  - [Visual Studio Code](https://code.visualstudio.com/)
- 有料
  - [JetBrains PHPStorm](https://www.jetbrains.com/phpstorm/)

上記以外のエディタやツールで利用いただくことも可能です。

対象のLLM Agentは以下になります。

- Gemini CLI
- (Optional) Claude Code
- (Optional) Codex CLI

## How to Use: 使い方

### 1. エディタ( VS Code etc )を開いてTerminalを起動する

VS Code を 起動し、Terminalを立ち上げましょう。

- Windows: `Control + j` ボタンで起動できます。
- mac: `Command + J` ボタンで起動できます。

### 2. LLM Agent を起動する。

Terminalにコマンドを入力するか、コピーしてEnterボタンを押下してください。

```bash
# Gemini CLI を起動する。
gemini
```

#### Claude Code, Codex を起動したい場合

それぞれ以下のコマンドを入力するか、コピーしてEnterボタンを押下してください。

Claude Code

```bash
# Claude Code を起動する。
claude
```

Codex CLI

```bash
# Codex CLI を起動する。
codex
```

### 3. エージェントにタスクを実行してもらう。

現在、カスタムスラッシュコマンドに対応している以下ツールのみに対応しています。
execファイルに記載されたタスクをエージェントが実行します。

- Gemini CLI
  - [exec.toml](.gemini/commands/exec.toml)
- Claude Code
  - [exec.md](.claude/commands/exec.md)

```bash
# LLMを起動後（ロゴの表示後）以下コマンドにて実行
/exec
```

任意の作業を実行させたい時は、execファイルを編集してLLM エージェントを再起動して実行してください。

## Requirements: 必要要件

以下の一般的に使用される開発ツールを必要とします。

- [Node.js](https://nodejs.org/): version 22 or higher installed.
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

有料サービスの契約が必要になりますが、以下のツールなども必要に応じてインストールして利用できます。

- Anthropic: Claude Code
  - https://docs.anthropic.com/ja/docs/claude-code/overview
- OpenAI: Codex CLI
  - https://github.com/openai/codex

#### For Developer

エンジニアなど開発者の方は下記ツールの利用を推奨しています。

#### Windows

- [WSL2](https://learn.microsoft.com/ja-jp/windows/wsl/install)
- [Homebrew](https://brew.sh/)
- [anyenv](https://github.com/anyenv/anyenv)
- [git](https://git-scm.com/downloads)

#### Mac

- [Homebrew](https://brew.sh/)
- [anyenv](https://github.com/anyenv/anyenv)
- [git](https://git-scm.com/downloads)


## Getting Started: 事前準備

### Node.js をインストールする。

https://nodejs.org/ja/download

上記ページを訪れ、インストーラーをダウンロードしてインストールしてください。

### Gemini CLIをインストール

VS Code を 起動し、Terminalを立ち上げましょう。

- Windows: `Control + j` ボタンで起動できます。
- mac: `Command + J` ボタンで起動できます。

ターミナルに下記コマンドを入力するか、コピーしてEnterボタンを押下してください。

```bash
# Gemini CLI をインストールする。
npx https://github.com/google-gemini/gemini-cli
```

------------------------------------------------------------------------------------

#### For Developer

エンジニアなど開発者の方は、コマンドラインでのインストールを推奨しています。

※ Windows利用中のエンジニアはWSLにてコマンドラインで実行してください。

#### Homebrew をインストールする。

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 以下コマンドでバージョンが表示されれば、インストールが完了している。
brew --version
```

#### Git をインストールする。

```bash
brew install git

# 以下コマンドでバージョンが表示されれば、インストールが完了している。
git --version
```

#### anyenv をインストールする。

```bash
# Install anyenv
brew install anyenv

# Set up anyenv in your shell.
anyenv init

```

#### anyenv を利用して、Node.js をインストールする。

Node.jsをバージョン管理するために、nodenvをインストールします。

```bash
# Install nodenv
anyenv install nodenv

# 以下コマンドでバージョンが表示されれば、インストールが完了している。
nodenv --version

```
nodenv利用して、node.js ( LTSバージョン ) で利用できるバージョン指定しインストールします。

```bash
nodenv install --list

# 以下のような形式で、インストール可能なバージョンが表示される
20.19.2
22.16.0
23.11.1
24.1.0
graal+ce-19.2.1
graal+ce_java11-20.0.0
graal+ce_java8-20.0.0

```
2025/08/01 現在は22以上のバージョンを推奨しています。

```bash
nodenv install 22.16.0
```

バージョンのインストールが完了したら初期化コマンド 及び 使用するバージョンの指定コマンドを実行してインストールを完了してください。

```bash
nodenv rehash

nodenv global 22.16.0

```

無事に完了していれば、以下コマンドでNodeのバージョンが表示されます。

```bash
node --version
```


#### Install LLM Agent: LLM Agentのインストール

VS Code を 起動し、Terminalを立ち上げましょう。

- Windows: `Control + j` ボタンで起動できます。
- mac: `Command + J` ボタンで起動できます。

ターミナルに下記コマンドをコピーしてEnterボタンを押下してください。

### Gemini CLI をインストールする

```bash

brew install gemini-cli

# 初回起動時に認証を行う必要があります。
# ログイン方法をヒアリングされますので 「Login with Google」を選択してください。
gemini

```

以下は、有料のサブスクリプションを契約された方のみ実行してください。

#### Claude Code をインストールし、認証を行う。

```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# 認証を行う。ブラウザが立ち上がり認証が成功するとログイン完了となります。
# ログイン方法をヒアリングされますので 「Claude account with subscription」を選択してください。
claude "/login"

```

#### Codex をインストールし、認証を行う。

```bash
# Install Codex CLI
brew install codex

# 認証を行う。ブラウザが立ち上がり認証が成功するとログイン完了となります。
codex login
```

お疲れ様でした。以上でLLM Agentを使うための準備完了です。
一旦、IDEを終了していただいて結構です。（そのまま使用したい方は起動したままで構いません。）

------------------------------------------------------------------------------------


## Structure: ディレクトリ構造

```bash
root/  -------------------------- # Current Directory 作業ディレクトリ
├── .claude/  ------------------- # Claude Code ディレクトリ
│   ├── commands/  -------------- # Claude Code カスタムスラッシュコマンド 格納ディレクトリ
│   │   └── tasks/  ------------- # 分割タスクのMarkdownファイル格納ディレクトリ
│   ├── docs/  ------------------ # Claude Code 参照用ドキュメント格納ディレクトリ
│   ├── prompts/  --------------- # Claude Code 汎用プロンプト 格納ディレクトリ
│   ├── tmp/  ------------------- # Claude Code テンポラリーファイル格納ディレクトリ
│   ├── settings.json  ---------- # Claude Code チーム共有用 設定ファイル
│   └── settings.local.json  ---- # Claude Code 個人用 設定ファイル
├── .gemini/  ------------------- # Gemini CLI ディレクトリ
│   ├── commands/  -------------- # Gemini CLI カスタムスラッシュコマンド 格納ディレクトリ
│   │   └── tasks/  ------------- # 分割タスクのMarkdownファイル格納ディレクトリ
│   ├── docs/  ------------------ # Gemini CLI 参照用ドキュメント格納ディレクトリ
│   ├── tmp/  ------------------- # Gemini CLI テンポラリーファイル格納ディレクトリ
│   └── settings.json  ---------- # Gemini CLI 設定ファイル ( MCP Server 設定 etc)
├── .vscode/  ------------------- # VS Code 設定ファイル格納 ディレクトリ
├── .idea/  --------------------- # JetBrains 設定ファイル格納 ディレクトリ
├── .mcp.json  ------------------ # Claude Code - MCP Server 設定ファイル
├── CLAUDE.md  ------------------ # Claude Code コンテキスト ファイル
├── GEMINI.md  ------------------ # Gemini CLI コンテキスト ファイル
└── README.md  ------------------ # Current File
```

## Commands: その他、設定済みのカスタムスラッシュコマンド

```bash
# 一時作成したファイルの削除
/clear-tmp

```

## MCP Servers: 利用可能なMCPサーバー

### Context7

[Context7 MCP](./docs/MCP/mcp-context7.md)

### Playwright

[Playwright MCP](./docs/MCP/mcp-playwright.md)

### Google Analytics

[Google Analytics MCP](./docs/MCP/mcp-google-analytics.md)

### GitHub

[GitHub MCP Server (Remote Server)](./docs/MCP/mcp-github-remote.md)

### Asana

[Asana MCP](./docs/MCP/mcp-asana.md)

## Caution: 注意事項

### 認証情報を設定ファイルに保存しない

### MCP Serverを利用する際の認証情報の設定について

## Appendix: 参考資料

- Gemini CLI
  - [Gemini CLI GitHub](https://github.com/google-gemini/gemini-cli)
  - [Gemini CLI documentation](https://github.com/google-gemini/gemini-cli/blob/main/docs/index.md)
- Claude Code
  - [Claude Code GitHub](https://github.com/anthropics/claude-code/)
  - [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code/overview)
- Codex CLI
  - [OpenAI Codex CLI GitHub](https://github.com/openai/codex/)