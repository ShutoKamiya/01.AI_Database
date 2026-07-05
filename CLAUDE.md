# Claude Code Instructions

このVaultで作業するときは、最初に `AGENTS.md` を読み、その運用規約に従うこと。

## RTKによるトークン削減

トークン削減を優先する作業では、可能な限りRTK経由のコマンドを使う。

- `git status` の代わりに `rtk git status` を使う。
- `git diff` の代わりに `rtk git diff` を使う。
- `ls` または `tree` の代わりに `rtk ls .` を使う。
- `find` の代わりに `rtk find` を使う。
- `grep` または `rg` の代わりに `rtk grep` を使う。
- 大きなファイルの読み取りには `rtk read` を使う。
- Claude Codeの組み込みRead、Grep、GlobはRTKを通らない場合があるため、必要に応じて明示的にRTKコマンドを使う。
- RTKで情報が不足する場合だけ通常コマンドに戻し、不足した理由を簡潔に報告する。

大量削除・大量リネーム・広範囲編集は事前確認し、明示的な指示なしに `git commit` または `git push` しないこと。