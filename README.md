# Lean 4 学習リポジトリ

Lean 4（関数型プログラミング言語 兼 定理証明支援系）を勉強するためのリポジトリです。
`resources/` にインターネット上の学習資料をまとめています（収集日: 2026-11-25）。

## 構成

| パス | 内容 |
| --- | --- |
| `resources/` | 学習資料のリンク集（下の表） |
| `mathematics_in_lean/` | [Mathematics in Lean](https://github.com/leanprover-community/mathematics_in_lean) の演習リポジトリ（git submodule） |
| `docs/` | ゼミのウェブサイト（GitHub Pages、Jekyll） |

このリポジトリを clone したあと、MIL を取得するには:

```sh
git submodule update --init
cd mathematics_in_lean
lake exe cache get   # Lean をインストール済みであること
```

ゼミのサイトを編集するときは `docs/` の Markdown を書き換えて push すると反映されます。日程は `docs/schedule.md`、メニューは `docs/_config.yml` の `nav` です。

## 資料一覧

| ファイル | 内容 |
| --- | --- |
| [resources/01-roadmap.md](resources/01-roadmap.md) | どの順番で何を読むか（学習ロードマップ） |
| [resources/02-setup.md](resources/02-setup.md) | 環境構築（macOS / VS Code / elan / Lake / Mathlib） |
| [resources/03-official-textbooks.md](resources/03-official-textbooks.md) | 公式・定番の教科書とゲーム（英語中心） |
| [resources/04-japanese-resources.md](resources/04-japanese-resources.md) | 日本語の資料・翻訳・コミュニティ |
| [resources/05-tools-and-community.md](resources/05-tools-and-community.md) | 検索ツール、API ドキュメント、フォーラムなど |
| [resources/06-advanced.md](resources/06-advanced.md) | メタプログラミング・型理論・研究会など発展的な資料 |

## 最短で始めるなら

1. ブラウザで [Lean 4 Web](https://live.lean-lang.org/) を開いて `#eval 1 + 1` を試す（インストール不要）
2. [Natural Number Game](https://adam.math.hhu.de/#/g/leanprover-community/NNG4) で証明の書き方に慣れる
3. 目的に合わせて教科書を選ぶ
   - 数学を形式化したい → [Mathematics in Lean](https://leanprover-community.github.io/mathematics_in_lean/)
   - プログラミング言語として使いたい → [Functional Programming in Lean](https://lean-lang.org/functional_programming_in_lean/)
   - 理論（依存型理論）から理解したい → [Theorem Proving in Lean 4](https://lean-lang.org/theorem_proving_in_lean4/)（[日本語訳](https://aconite-ac.github.io/theorem_proving_in_lean4_ja/)）
