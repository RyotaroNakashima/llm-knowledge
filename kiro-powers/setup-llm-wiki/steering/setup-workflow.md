# LLM Wiki セットアップワークフロー

## 基本方針
Obsidian は optional。必須なのは、LLM エージェントが読める・検索できる・編集できる・保守できる Markdown フォルダ。

ユーザーが明示的に希望しない限り、セットアップを Obsidian 前提にしない。

## セットアップ手順
1. ファイルを作る前に、対象プロジェクトやワークスペースの構成を確認する。
2. モードを決める。
   - **Markdown-only**: Obsidian が使えない、または不要な場合。
   - **Obsidian-compatible**: Obsidian を使う、または将来使う可能性がある場合。
3. 大きな分類体系ではなく、小さなフォルダ構成から始める。
4. `AGENTS.md`、`index.md`、運用マニュアル、LLM 記憶プロトコル、テンプレートを作る。
5. 初期プロジェクトノートと、セットアップ方針の意思決定ノートを作る。
6. リンク、ファイルパス、Obsidian 設定 JSON を作った場合は JSON 構文を検証する。

## 推奨フォルダ構成
ユーザーの作業言語が日本語なら日本語フォルダ名を使う。別言語のプロジェクトなら、そのプロジェクトの言語に合わせる。

```text
AGENTS.md
index.md
00_受信箱/
10_情報源/
20_ノート/
30_意思決定/
40_プロジェクト/
80_テンプレート/
90_運用/
```

Obsidian-compatible の場合だけ、必要に応じて追加する。

```text
.obsidian/app.json
.obsidian/core-plugins.json
.obsidian/templates.json
.obsidian/workspace.json
```

`.obsidian` 設定は最小限にする。初期セットアップでは community plugin を入れない。

## 必須ノート
- `index.md`: 入口、現在のテーマ、主要ノート、未解決事項。
- `AGENTS.md`: LLM エージェントが作業前後に従う入口ルール。毎回すべてを自動記録せず、意味のある変更だけ Wiki に統合する方針を書く。
- `90_運用/運用マニュアル.md`: フォルダの役割、日常ワークフロー、ノート基準、保守方法。
- `90_運用/LLM記憶プロトコル.md`: LLM が最初に読むもの、更新ルール、残す情報、残さない情報、作業後プロンプト。
- `40_プロジェクト/<project-name>.md`: 現在の状態、重要な文脈、次の行動。
- `30_意思決定/YYYY-MM-DD-LLM記憶にMarkdownを使う.md`: Markdown を使う理由、却下した案、結果。

## ノート基準
長期保存するノートには、できるだけ次を入れる。

```text
状態: 現行 | 下書き | 古い | 置き換え済み
最終更新: YYYY-MM-DD
信頼度: 低 | 中 | 高
```

次を分けて書く。

- 事実
- 判断
- 理由
- 却下した案
- 未解決事項
- 関連リンク

## Obsidian について説明するとき
- vault は、Obsidian が管理する Markdown フォルダのこと。
- Obsidian は、リンク、バックリンク、グラフビュー、テンプレートを人間が扱うために便利。
- Obsidian は LLM Wiki に必須ではない。Obsidian がなくても、`rg`、ファイル読み取り、Markdown リンク、Git で運用できる。
- 会社で Obsidian が使えない場合は Markdown-only 構成にして、VS Code、Cursor、GitHub、任意のエディタで見る。

## 検証
セットアップや変更後は次を確認する。

- `find` または `rg --files` で期待ファイルがあることを確認する。
- ファイル名変更をした場合、古い Markdown リンクが残っていないか確認する。
- `.obsidian/*.json` がある場合は `python3 -m json.tool` で検証する。
- 最終回答は短くし、重要なファイルパスを含める。

