# AI Database Vault Instructions

## Vaultの目的

- このリポジトリはObsidian Markdown Vaultとして扱う。
- Codex、Claude Code、Claudian、ChatGPTが少ないトークンで必要情報に到達できる知識データベースを維持する。
- 構成はフラットに保ち、不要に深い階層を作らない。
- Google Drive、iCloud、OneDriveなどのクラウド同期は使わない。

## ノート作成ルール

- 新規ノートは1ファイル1テーマのアトミックノートにする。
- ノート粒度は、実験・問題・判断など、単独で再利用できる単位にする。
- 新規ノートにはYAMLフロントマターを付ける。
- YAMLは低トークン化のため、原則として title、created、updated、tags、status、summary の6項目だけにする。
- summaryには、本文を読まなくても用途と結論を判断できる短い説明を書く。
- 内部リンクは単なる羅列にせず、文章の文脈に組み込む。
- ChatGPTやClaudeとの会話全文は保存せず、相談内容、結論、決定事項、次の行動をまとめた相談まとめ形式で保存する。

## AIの探索順序

- Vault全体を無目的に全文読みしない。
- 最初にファイル名を確認する。
- 次にYAMLのsummaryと見出しを確認する。
- 必要な場合だけ本文を読む。
- 関連ノートの探索では、全文読みより検索と見出し確認を優先する。

## RTK運用ルール

- Git状態確認は `rtk git status` を優先する。
- Git差分確認は `rtk git diff` を優先する。
- ファイル一覧確認は `rtk ls .` または `rtk find` を優先する。
- 検索は `rtk grep "<keyword>" .` を優先する。
- 大きなMarkdownファイルを読む場合は `rtk read <file>` を優先する。
- テスト、ビルド、ログ確認では `rtk err <command>` または `rtk test <command>` を優先する。
- RTKで情報が削られすぎて判断できない場合だけ、通常の詳細コマンドに戻す。
- 通常コマンドに戻した場合は、RTKでは不足した理由を簡潔に報告する。

## 安全な変更とGit運用

- 大量削除・大量リネーム・広範囲編集は事前確認する。
- `.obsidian/workspace.json` と `.obsidian/workspace-mobile.json` はGit管理しない。
- Git操作の前後に `git status` を確認する。RTKが利用可能なら `rtk git status` を優先する。
- 明示的な指示なしに `git commit` または `git push` しない。
- 作業後に作成・変更したファイルと内容を簡潔に報告する。