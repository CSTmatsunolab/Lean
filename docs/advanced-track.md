---
title: 発展トラック（M1 向け）
permalink: /advanced-track/
---

MIL を進めながら、後半に個人課題として取り組む内容です。
セキュリティ分野では、プロトコルや型システム、コンパイラの正しさを証明支援系で検証する研究が広く行われています。
その入口として「小さな言語の型安全性」を Lean で証明します。

## ゴール

まずは TAPL 8 章の「型付き算術式」（真偽値と自然数だけの、変数のない言語）について、次の 2 つの定理を Lean で証明することを到達目標にします。

- **進行（Progress）:** 型の付いた項は、値であるか、あと 1 ステップ計算を進められる
- **保存（Preservation）:** 型の付いた項を 1 ステップ計算しても、型は変わらない

変数のある言語（単純型付きラムダ計算）に広げる場合、進行定理は「自由変数を含まない（閉じた）項」についてだけ成り立ちます。
{: .note }

この 2 つを合わせると「型の付いた（閉じた）プログラムは実行中に行き詰まらない」ことが言えます。これが型安全性です。

## 進め方（案）

| 時期 | 内容 | 参考 |
| --- | --- | --- |
| 前期 | MIL 1〜4 章をほかの参加者と一緒に進める。並行して、TPIL 7 章（帰納型）と 8 章（帰納法と再帰）を読む | [TPIL 日本語訳](https://aconite-ac.github.io/theorem_proving_in_lean4_ja/) |
| 夏休み | TAPL 3 章（型なし算術式）と 8 章（型付き算術式）を読み、構文・評価規則・型付け規則を Lean の帰納型として定義する | TAPL（Pierce） |
| 後期前半 | 進行定理と保存定理を証明する（MIL 5〜6 章の帰納法、6.3 節の帰納的な構造が直接役に立つ） | — |
| 後期後半 | 第 25 回で発表。余力があれば単純型付きラムダ計算（TAPL 9 章）に拡張する。そのためには変数の束縛・代入・型付け文脈の扱いと、保存定理で使う代入補題が必要になる | TAPL 5 章（ラムダ計算）、6 章（項の名前なし表現） |

## 参考資料

- **Theorem Proving in Lean 4** — [英語](https://lean-lang.org/theorem_proving_in_lean4/) / [日本語訳](https://aconite-ac.github.io/theorem_proving_in_lean4_ja/)
  帰納型、構造的帰納法、帰納的に定義された述語。
- **Functional Programming in Lean** — [https://lean-lang.org/functional_programming_in_lean/](https://lean-lang.org/functional_programming_in_lean/)
  Lean でプログラムを書く方法。
- **The Hitchhiker's Guide to Logical Verification** — [https://github.com/lean-forward/logical_verification_2026](https://github.com/lean-forward/logical_verification_2026)
  プログラムの意味論と検証を Lean で扱う大学院講義の教材。操作的意味論・Hoare 論理の章が特に参考になります。
- **Types and Programming Languages**（Benjamin C. Pierce, MIT Press）
  型システムの標準的な教科書。3・8 章を使い、拡張する場合は 5・6・9 章も使います。
- **Lean by Example**（日本語） — [https://lean-ja.github.io/lean-by-example/](https://lean-ja.github.io/lean-by-example/)
  `inductive` などの構文をコード例で確認できます。
