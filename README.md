# factcheck-skill

情報の信頼性を科学的・体系的に評価する、Claude Code / Cowork 用ファクトチェック・スキル。

20項目×4カテゴリの評価フレームワークで、記事・URL・主張・AIの回答などあらゆる情報の信頼性をスコアリングします。

> 元プロジェクト: [shuji-bonji/fact-checklist](https://github.com/shuji-bonji/fact-checklist) — 12言語対応のファクトチェックPWA

## 構成

```
factcheck-skill/
├── SKILL.md              # メインのスキル定義（20項目の評価基準含む）
├── agents/
│   └── fact-checker.md   # ファクトチェック専門サブエージェント定義
└── README.md
```

## 使い方

### Cowork / Claude Code でスキルとして使う

1. このリポジトリ（またはディレクトリ）を `.claude/skills/` 配下にコピーする:

```bash
cp -r factcheck-skill ~/.claude/skills/factcheck
```

2. Claude に「この記事をファクトチェックして」「この情報の信頼性を評価して」と頼む

### サブエージェントとして使う（Claude Code）

メインエージェントの回答を独立した検証者としてチェックさせたい場合:

```
Agent ツールで agents/fact-checker.md を読み込み、
メインエージェントの出力を渡して検証させる
```

これにより「自分で自分を採点する」バイアスを排除し、より客観的な検証が可能になります。

## 評価カテゴリ

| カテゴリ | 項目数 | 概要 |
|---|---|---|
| クリティカル評価 | 6 | 情報源の権威性・一次情報・匿名性・論理性 |
| 詳細評価 | 6 | 新しさ・専門性・根拠・引用の質 |
| 検証・照合 | 4 | クロスチェック・ファクトチェック機関・データ検証 |
| 文脈・バイアス | 4 | 利害関係・バランス・背景・適用範囲 |

## ライセンス

MIT License — [shuji-bonji/fact-checklist](https://github.com/shuji-bonji/fact-checklist) に準拠
