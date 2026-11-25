# 学習ロードマップ

Lean の資料は「誰向けか」で大きく分かれます。公式サイト（[Learn Lean](https://lean-lang.org/learn)）とコミュニティ（[Learning Lean 4](https://leanprover-community.github.io/learn)）の推奨をもとに、順番を整理しました。

## ステップ 0: 触ってみる（30分）

- [Lean 4 Web](https://live.lean-lang.org/) — ブラウザ上の Lean。インストール前に雰囲気をつかむのに最適。ただし大きな開発には向かない。

## ステップ 1: ゲームで証明に慣れる（数日）

- [Natural Number Game (NNG4)](https://adam.math.hhu.de/#/g/leanprover-community/NNG4)
  - 自然数の加法・乗法・べき・不等式を 9 ワールド・約 80 レベルで証明していく。Kevin Buzzard らが作成。
  - `rfl`, `rw`, `induction` など基本タクティクを自然に覚えられる。
- 余裕があれば [Lean Game Server](https://adam.math.hhu.de/) の他のゲーム（Set Theory, Logic, Robo など）。

## ステップ 2: 環境を作る

- [02-setup.md](02-setup.md) を参照。VS Code + Lean 4 拡張機能が公式推奨。

## ステップ 3: 目的別の教科書を 1 冊通す

| 目的 | 推奨 | 日本語 |
| --- | --- | --- |
| 数学の形式化（Mathlib を使う） | [Mathematics in Lean](https://leanprover-community.github.io/mathematics_in_lean/) | 和訳リポジトリあり（アーカイブ済み、[04](04-japanese-resources.md) 参照） |
| 数学の証明そのものに不慣れ | [The Mechanics of Proof](https://hrmacbeth.github.io/math2001/) | — |
| 速めに全体像をつかむ（数学寄り） | [Glimpse of Lean](https://github.com/PatrickMassot/GlimpseOfLean) | — |
| プログラミング言語として | [Functional Programming in Lean](https://lean-lang.org/functional_programming_in_lean/) | 和訳リポジトリあり（アーカイブ済み） |
| 型理論・Lean の仕組み | [Theorem Proving in Lean 4](https://lean-lang.org/theorem_proving_in_lean4/) | [日本語訳あり](https://aconite-ac.github.io/theorem_proving_in_lean4_ja/) |
| 日本語でコード例から学ぶ | [Lean by Example](https://lean-ja.github.io/lean-by-example/) | 日本語オリジナル |
| 日本語で数学ユーザー向けに | [数学系エンドユーザーのためのLean入門](https://shosonoda.github.io/lean-math-note/) | 日本語オリジナル |

## ステップ 4: 手元に置いて引く資料

- [タクティクのチートシート (PDF)](https://leanprover-community.github.io/papers/lean-tactics.pdf)
- [Mathlib のタクティク一覧](https://leanprover-community.github.io/mathlib4_docs/tactics.html)
- [Lean Language Reference](https://lean-lang.org/doc/reference/latest/)（言語仕様。チュートリアルではない）
- 定理の検索: [Loogle](https://loogle.lean-lang.org/), [LeanSearch](https://leansearch.net/) など（[05](05-tools-and-community.md) 参照）

## ステップ 5: その先

- 自分の分野の定理を形式化してみる / [Mathlib の good first issue](https://github.com/leanprover-community/mathlib4/issues?q=is%3Aissue%20is%3Aopen%20label%3A%22good%20first%20issue%22) に挑戦
- タクティクを自作する → [06-advanced.md](06-advanced.md)
- 困ったら [Lean Zulip](https://leanprover.zulipchat.com/)（英語、`#new members` ストリーム）や lean-ja の Discord（日本語）で質問
