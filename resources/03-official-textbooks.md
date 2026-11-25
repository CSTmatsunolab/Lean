# 公式・定番の教科書とゲーム

どれも無料で公開されています。多くは VS Code で手を動かしながら読む前提です。
出典: [Learn Lean (lean-lang.org)](https://lean-lang.org/learn), [Learning Lean 4 (Lean Community)](https://leanprover-community.github.io/learn)

## 中核となる 4 冊

### Theorem Proving in Lean 4 (TPIL)
- URL: https://lean-lang.org/theorem_proving_in_lean4/
- 日本語訳: https://aconite-ac.github.io/theorem_proving_in_lean4_ja/
- 内容: 依存型理論、命題と証明、タクティク、帰納型、型クラスなど。Lean の「土台」を理解する標準的な本。
- 対象: 仕組みから理解したい人。数学の形式化だけが目的なら MIL を先にしてもよい。

### Functional Programming in Lean (FPIL)
- URL: https://lean-lang.org/functional_programming_in_lean/
- 内容: Lean をプログラミング言語として使う。型、構造体、型クラス、モナド、依存型プログラミングなど。
- 対象: プログラマ。関数型言語の経験は不要。メタプログラミングに進むならモナドの章は必読。

### Mathematics in Lean (MIL)
- URL: https://leanprover-community.github.io/mathematics_in_lean/
- PDF: https://leanprover-community.github.io/mathematics_in_lean/mathematics_in_lean.pdf
- 演習リポジトリ: https://github.com/leanprover-community/mathematics_in_lean
- 内容: Mathlib を使ってタクティクで数学（論理、集合、初等整数論、代数構造、位相、解析など）を形式化する。
- 対象: 数学者・数学科の学生。数学目的なら第一候補。

### The Lean Language Reference
- URL: https://lean-lang.org/doc/reference/latest/
- 非公式日本語訳: https://s-taiga.github.io/reference-manual-ja （Lean 4.16.0-rc2 時点の版。最新とはずれている）
- 内容: 言語仕様の正確なリファレンス。読み通すものではなく、調べるときに引く。

## ゲーム・入門

- **Natural Number Game** — https://adam.math.hhu.de/#/g/leanprover-community/NNG4
  ブラウザで遊べる。自然数の性質を一から証明していく。最初の一歩として最も推奨されている。
- **Lean Game Server** — https://adam.math.hhu.de/
  NNG と同形式のゲーム集（Set Theory Game, Logic Game, Robo など）。
- **Glimpse of Lean** — https://github.com/PatrickMassot/GlimpseOfLean
  基本ファイル 4 つ＋分野別（解析、位相、論理など）のファイルで、速いペースで全体像をつかむ。

## その他の教科書

- **The Mechanics of Proof** (Heather Macbeth) — https://hrmacbeth.github.io/math2001/
  Fordham 大学の講義 Math2001 用。証明の書き方そのものを Lean で学ぶ。MIL よりやさしい。
- **Logic and Proof** — https://leanprover-community.github.io/logic_and_proof/
  古典論理の教科書を Lean で。
- **The Hitchhiker's Guide to Logical Verification** — https://github.com/lean-forward/logical_verification_2026
  アムステルダム自由大学の大学院講義。計算機科学・検証寄り。
- **Lean FAQ** — https://lean-lang.org/faq

## 有料・個人の本

- **Learning Lean 4 With Examples** (Mark Watson, Leanpub) — https://leanpub.com/learninglean4
  実用的な関数型言語として Lean を扱う。
- **From Zero to QED** (Stephen Diehl) — https://sdiehl.github.io/zero-to-qed/01_introduction.html
  言語を基礎から解説する記事シリーズ。
