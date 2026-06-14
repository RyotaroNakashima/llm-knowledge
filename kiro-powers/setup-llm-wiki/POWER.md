---
name: "setup-llm-wiki"
displayName: "LLM Wiki セットアップ"
description: "Markdown ベースの LLM Wiki / 長期記憶 / Obsidian optional なプロジェクト知識ベースをセットアップ・改善する"
keywords: ["llm wiki", "LLM Wiki", "長期記憶", "knowledge base", "markdown wiki", "obsidian", "vault", "AGENTS.md", "セットアップ", "プロジェクト記憶"]
author: "Ryotaro Nakashima"
---

# LLM Wiki セットアップ Power

この power は、Kiro で既存プロジェクトに LLM Wiki をセットアップするときに使う。

## Onboarding
初回利用時は、まず対象プロジェクトを確認する。

1. ファイルを作る前に、プロジェクト直下の構成を確認する。
2. 既に `AGENTS.md`、`index.md`、`.kiro/steering/`、`90_運用/` などがあるか確認する。
3. Obsidian を前提にしない。会社環境では Markdown-only を標準にする。
4. 既存の README、docs、設計メモ、運用ルールがある場合は壊さず、LLM Wiki 側から参照する。

## 使い分け
- 既存プロジェクトに LLM Wiki を新規セットアップする場合: `steering/setup-workflow.md` を使う。
- Kiro で常時参照される運用方針を入れたい場合: `.kiro/steering/llm-wiki-operations.md` を作る。
- Codex / Claude Code とも共通で使いたい場合: ルートに `AGENTS.md` を作る。

## 重要な方針
- Obsidian は optional。必須ではない。
- 必須なのは、LLM エージェントが読める・検索できる・編集できる Markdown フォルダ。
- すべての作業を自動記録しない。
- 作業ログ全文ではなく、将来使える知識だけを圧縮して残す。
- 毎回すべてのノートを読ませない。`AGENTS.md` と `index.md` を入口にして関係ノートだけ読む。

## When to Load Steering Files
- LLM Wiki の作成、セットアップ、初期化、既存プロジェクトへの導入 → `steering/setup-workflow.md`
- Kiro で継続運用するための常時方針、作業後更新、軽量メンテナンス → `steering/operations.md`
- Codex skill や Claude Code 向けプロンプトとの対応関係を確認する → `steering/prompts.md`

## 完了条件
セットアップ作業では、少なくとも次を満たす。

- `AGENTS.md` がある。
- `index.md` がある。
- `90_運用/運用マニュアル.md` がある。
- `90_運用/LLM記憶プロトコル.md` がある。
- 初期プロジェクトノートがある。
- Markdown-only でも運用できる。
- Obsidian-compatible にする場合だけ `.obsidian/` を作る。
- 作成後にファイル一覧とリンク、JSON があれば JSON を検証する。

