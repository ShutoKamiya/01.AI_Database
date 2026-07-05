---
title: Obsidian AI低トークン運用ルール
created: 2026-07-05
updated: 2026-07-05
tags: [obsidian, ai, rtk, token-saving]
status: active
summary: CodexやClaude CodeがVaultを低トークンで探索・更新するための情報取得順序とRTK運用ルール。
---

# Obsidian AI低トークン運用ルール

## RTKを使う目的

RTKはコマンド出力から判断に不要な情報を削り、CodexやClaude Codeが消費するトークンを抑えるために使う。現環境ではRTKが未導入のため、導入時は [[RTK_Setup_Windows]] を参照する。

## 優先するRTKコマンド

| 目的 | 優先コマンド |
|---|---|
| Git状態確認 | `rtk git status` |
| Git差分確認 | `rtk git diff` |
| ファイル一覧 | `rtk ls .` または `rtk find` |
| キーワード検索 | `rtk grep "<keyword>" .` |
| 大きなファイルの確認 | `rtk read <file>` |
| テスト・ビルド・ログ | `rtk err <command>` または `rtk test <command>` |

## Vaultの探索順序

Vault全体を無目的に全文読みしない。最初にファイル名を検索し、候補ノートのYAML `summary` と見出しを確認する。結論や根拠が不足するときだけ本文を読む。

## ノートの粒度

ノートは実験・問題・判断のいずれかを基本単位とし、1ファイル1テーマにする。独立した結論が複数ある場合はノートを分割し、文脈の中で内部リンクを使って接続する。

## AI相談の保存方法

ChatGPTやClaudeとの会話全文は保存しない。再利用に必要な相談内容、結論、決定事項、次の行動だけを [[ChatGPT_Conversation_Summary_Template]] に沿って残す。

## 30_Dailyと90_Archive

`30_Daily` は、その日の作業記録や未整理の判断材料を短く記録する場所として使う。長期利用する知識は整理後に `20_Knowledge` へ移す。

`90_Archive` は完了済み・旧版・参照頻度の低い情報の保管場所とする。通常のAI探索では優先対象にせず、現行ノートで不足する場合だけ検索する。

## RTKで情報が不足する場合

RTKで情報が削られすぎて判断できない場合だけ通常の詳細コマンドに戻す。その際は、どの情報が不足したため通常コマンドが必要だったかを簡潔に報告する。