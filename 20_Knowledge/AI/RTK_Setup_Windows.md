---
title: WindowsでのRTKセットアップ
created: 2026-07-05
updated: 2026-07-05
tags: [rtk, windows, codex, claude-code]
status: pending
summary: RTK未導入のWindows環境で、低トークン運用を始めるために必要なセットアップ方針。
---

# WindowsでのRTKセットアップ

## 現在の状態

`rtk --version` を実行した結果、RTKコマンドは認識されず、現在のWindows環境には導入されていない。

## 導入する目的

RTKを使う目的は、Git状態、差分、検索結果、テストログなどの出力を圧縮し、AIが判断に使うトークン量を減らすことにある。

## CodexとClaude Codeで使う理由

CodexやClaude Codeはコマンド出力もコンテキストとして消費する。RTK経由で必要な情報に絞ることで、Vault探索時のコストを抑え、重要なノート内容へ多くのコンテキストを使える。

## 必要な対応

RTKはあとでWindowsへ手動インストールする必要がある。導入後に `rtk --version` で確認し、Codex向けのグローバル初期化が利用できる場合は `rtk init -g --codex` を実行する。