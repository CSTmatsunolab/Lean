---
title: ミニ言語の形式検証
permalink: /mini-language/
---

第 21〜24 回は、MIL を離れて全員で「小さなプログラミング言語」を Lean で定義し、その性質を証明します。
MIL 5 章（帰納法）と 6.3 節（帰納的な構造）で学んだことを、プログラムの正しさの証明に使う単元です。

## ねらい

- 言語の**構文**を帰納型で、**意味**を関数や帰納的述語で書けるようになる
- 「最適化しても結果が変わらない」「コンパイルしても結果が変わらない」といった性質を、構造的帰納法で証明できるようになる
- 型のない言語では計算が**行き詰まる**ことを確かめ、第 25 回の発展課題（型を付けると行き詰まらない）につなげる

## 各回の内容

### 第 21 回: 式と最適化

- 自然数の定数・足し算・掛け算だけの算術式 `Expr` を `inductive` で定義し、値を求める関数 `eval` を書く
- 定数畳み込み `constFold`（例: `2 + 3` を `5` に置き換える）を書き、`eval (constFold e) = eval e` を証明する
- 証明を簡単にするため、足し算の畳み込みは補助関数 `mkAdd` に分け、先に `eval (mkAdd a b) = eval a + eval b` を示す
- コラム: `structure` と `deriving Repr, DecidableEq`（MIL 7.1 の代わりに 15 分ほど）

### 第 22 回: スタックマシンへのコンパイラ

- 命令 `push n` / `add` / `mul` を持つスタックマシンと、その実行関数 `exec` を書く（スタックが足りないときはそのまま返す全域関数にする）
- 式を命令列に変換する `compile` を書き、正しさを証明する
- 証明の山場は**主張の一般化**です。`exec (compile e) [] = [eval e]` をそのまま帰納法で示そうとすると、帰納法の仮定が使えずに行き詰まります。任意のスタック `s` と後に続く命令列 `k` について
  `exec (compile e ++ k) s = exec k (eval e :: s)`
  を `induction e generalizing s k` で示し、元の定理は `s = []` かつ `k = []` の場合として導きます

### 第 23 回: 帰納的述語と small-step 意味論

- TAPL 3 章の言語（`true`, `false`, `if`, `0`, `succ`, `pred`, `iszero`）を定義する
- 「数値の値である」`IsNumVal`（`0` と `succ` の並び）、「値である」`IsValue`、「1 ステップ計算が進む」`Step t t'` を、関数ではなく**帰納的述語**（`inductive ... : ... → Prop`）で定義する
- 具体的な項について計算の導出を組み立てる。`cases h` で「このステップはどの規則から来たか」を調べる（逆転）

### 第 24 回: 規則帰納法と行き詰まり

- 1 ステップ計算の決定性（`Step t t₁ → Step t t₂ → t₁ = t₂`）を証明する。項ではなく**導出**についての帰納法 `induction h₁ generalizing t₂` を使い、先に補題「値は 1 ステップも進まない」を示しておく
- `succ true` や `if 0 then … else …` のように、値でもないのにこれ以上計算が進まない項（行き詰まり）があることを確かめる
- 次回、M1 がこの言語に型を付けて「型の付いた項は行き詰まらない」ことを示す（[発展課題]({{ '/advanced-track/' | relative_url }})）

## 環境と書き方の注意

この単元の教材は、Mathlib を使わない Lean 本体だけで書きます。MIL と同じ Lean のバージョン（`leanprover/lean4:v4.34.0`）を使い、`autoImplicit` は MIL と同じく `false` にします。
{: .note }

MIL で慣れた書き方の一部は Mathlib 由来なので、この単元では次のように書き換えます。

| MIL（Mathlib あり） | この単元（Lean 本体のみ） |
| --- | --- |
| `ℕ` | `Nat` |
| `induction' e with ...` | `induction e with` の後に、構成子ごとの場合を並べる（MIL 5.4 にも出てくる書き方） |
| `use x` | `exists x` または `refine ⟨x, ?_⟩` |
| `ring`, `linarith`, `norm_num` | 直接の代わりはない。自然数・整数の線形な式は `omega`、具体的な数の計算は `simp` や `decide`、`a * b = b * a` のような式は `Nat.mul_comm` などの定理で書き換える |
| `rcases`, `obtain`, `ext`, `simp_all`, `omega` | そのまま使える |

## 教材の準備状況

- 各回の演習ファイル（`sorry` 付きの問題と解答）は、教員と M1 が第 20 回までに用意し、Lean で通ることを確認してから配布します（未作成）。当日は M1 が TA 役をします。
- 余裕があれば: 変数と代入のある命令型言語（While 言語）の意味論、最適化の追加。最終発表のテーマにしてもかまいません。

## 参考資料

- **Types and Programming Languages**（Pierce）3 章 — 第 23〜24 回の言語と評価規則
- **The Hitchhiker's Guide to Logical Verification** — [https://github.com/lean-forward/logical_verification_2026](https://github.com/lean-forward/logical_verification_2026)
  Lean で操作的意味論を扱う講義教材（Mathlib を使っているので、そのままは使わず題材の参考にする）
- **Theorem Proving in Lean 4** 7 章（帰納型）・8 章（帰納法と再帰） — [日本語訳](https://aconite-ac.github.io/theorem_proving_in_lean4_ja/)
- **Concrete Semantics**（Nipkow, Klein） — [http://www.concrete-semantics.org/](http://www.concrete-semantics.org/)
  Isabelle の本ですが、算術式・スタックマシン・While 言語という題材の流れはこの単元とほぼ同じです
