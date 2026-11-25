# ツール・ドキュメント・コミュニティ

## 試す・動かす

- **Lean 4 Web（Playground）** — https://live.lean-lang.org/ ブラウザで Lean と Mathlib を実行
- **Lean 4 VS Code 拡張** — https://github.com/leanprover/vscode-lean4

## 定理・定義を探す

Lean の学習でいちばん時間を使うのは「欲しい補題の名前を探すこと」です。

- **Loogle** — https://loogle.lean-lang.org/
  型や名前のパターンで検索（例: `Nat.succ_le_iff`, `(_ + _) * _ = _`）。Web・CLI・エディタ拡張あり。
- **LeanSearch** — https://leansearch.net/ 自然言語で Mathlib を検索
- **Moogle** — https://www.moogle.ai/ 自然言語で Mathlib を検索（2026-11-25 時点で接続できず。終了した可能性あり）
- **LeanExplore** — https://www.leanexplore.com/ 自然言語で宣言を検索
- エディタ内では `exact?`, `apply?`, `rw?`, `simp?` タクティクも補題探しに使える

## API ドキュメント・一覧

- **Mathlib / Lean API ドキュメント** — https://leanprover-community.github.io/mathlib4_docs/
- **Lean API（公式）** — https://lean-lang.org/doc/api/
- **タクティク一覧** — https://leanprover-community.github.io/mathlib4_docs/tactics.html
- **タクティクのチートシート (PDF)** — https://leanprover-community.github.io/papers/lean-tactics.pdf
- **用語集** — https://leanprover-community.github.io/glossary.html
- **Mathlib の全体像** — https://leanprover-community.github.io/mathlib-overview.html
- **学部数学のうち Mathlib にあるもの** — https://leanprover-community.github.io/undergrad.html
- **100 の定理の形式化状況** — https://leanprover-community.github.io/100.html
- **Mathlib の命名規則** — https://mathlib.org/contribute/naming.html
- **Mathlib のスタイルガイド** — https://mathlib.org/contribute/style.html

## ライブラリ・パッケージ

- **Mathlib4** — https://github.com/leanprover-community/mathlib4 学部〜研究レベルの数学ライブラリ
- **Reservoir** — https://reservoir.lean-lang.org/ Lean パッケージの索引
- **CSLib** — https://www.cslib.io/ 計算機科学向けライブラリ

## コミュニティ

- **Lean Zulip** — https://leanprover.zulipchat.com/ 公式フォーラム（英語）。初心者は `#new members` へ。過去ログ: https://leanprover-community.github.io/archive/
- **lean-ja Discord** — 日本語。招待リンクは https://lean-ja.github.io/links/ にある
- **Lean Community ブログ** — https://leanprover-community.github.io/blog
- **イベント情報** — https://leanprover-community.github.io/events.html
- **YouTube（Lean Community）** — https://www.youtube.com/channel/UCWe5B7Ikr0AI9727doEUxPg/playlists
- **Lean を使った授業の一覧** — https://leanprover-community.github.io/teaching/courses.html
- **教える人向けの資料** — https://leanprover-community.github.io/teaching/resources.html
- **Lean を使ったプロジェクト一覧** — https://leanprover-community.github.io/lean_projects.html
- **Lean に関する論文一覧** — https://leanprover-community.github.io/papers.html

## AI・機械との連携

- **LeanDojo** — https://leandojo.org/ データ抽出・プログラムからの操作
- **REPL** — https://github.com/leanprover-community/repl
- **Pantograph** — https://github.com/leanprover/Pantograph
