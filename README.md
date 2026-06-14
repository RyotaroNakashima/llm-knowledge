# llm-knowledge

LLM Wiki をセットアップするための再利用資材です。

このリポジトリには、2種類の形式を置いています。

- `codex-skills/setup-llm-wiki/`: Codex skill 形式
- `kiro/.kiro/steering/llm-wiki-setup.md`: Kiro steering 形式
- `kiro/AGENTS.md`: Kiro / Codex / Claude Code などが読める共通入口ルール

## LLM Wiki とは
LLM Wiki は、LLM エージェントが読める・更新できる Markdown ベースの長期記憶です。

Obsidian は必須ではありません。Obsidian はリンク、バックリンク、グラフビュー、テンプレートを人間が扱いやすくする optional な UI です。

必須なのは以下です。

- Markdown ファイルとして保存されていること
- `AGENTS.md` があり、エージェントの作業前後ルールがあること
- `index.md` があり、Wiki の入口になっていること
- `90_運用/` などに運用ルールがあること
- 作業後に、長期的に意味がある変更だけを関連ノートへ統合すること

## Codex で使う

`codex-skills/setup-llm-wiki/` を Codex の skills ディレクトリへコピーします。

```sh
mkdir -p ~/.codex/skills
cp -R codex-skills/setup-llm-wiki ~/.codex/skills/
```

使うときの例:

```text
$setup-llm-wiki を使って、このプロジェクトに Markdown ベースの LLM Wiki をセットアップしてください。Obsidian は optional として扱ってください。
```

## Kiro で使う

Kiro の workspace steering として使う場合は、対象プロジェクトに `.kiro/steering/llm-wiki-setup.md` を置きます。

```sh
mkdir -p .kiro/steering
cp kiro/.kiro/steering/llm-wiki-setup.md .kiro/steering/
cp kiro/AGENTS.md ./AGENTS.md
```

Kiro の global / team steering として使う場合は、`llm-wiki-setup.md` を `~/.kiro/steering/` に置きます。

```sh
mkdir -p ~/.kiro/steering
cp kiro/.kiro/steering/llm-wiki-setup.md ~/.kiro/steering/
```

Kiro では steering files が Markdown として読み込まれます。`llm-wiki-setup.md` は `inclusion: auto` なので、LLM Wiki、長期記憶、Obsidian、Markdown Wiki セットアップなどの依頼で自動的に使われる想定です。

## 運用方針

すべての作業を自動記録しません。

作業後に Wiki を更新するのは、次のような長期的に意味がある変更があった場合だけです。

- 意思決定をした
- 既存ノートの内容が古くなった
- 新しい運用ルールや注意点が分かった
- 失敗した案を次回も避けたい
- プロジェクトの現在地や次の行動が変わった
- ユーザーの制約や希望が今後も効く

作業ログ全文ではなく、将来使える知識だけを圧縮して残します。

