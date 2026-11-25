---
title: 環境構築
permalink: /setup/
---

第 1 回までに、できるところまで進めておいてください。うまくいかなければ当日一緒に直します。

途中で数 GB のダウンロードがあります。教室の Wi-Fi で全員が一斉にダウンロードすると時間がかかるので、できるだけ自宅などの回線で済ませてきてください。
{: .note }

## 1. まずブラウザで試す（インストール不要）

[Lean 4 Web](https://live.lean-lang.org/) を開いて、次を入力してみてください。右側に `2` と表示されれば動いています。

```lean
#eval 1 + 1

example (a b : Nat) : a + b = b + a := by
  omega
```

## 2. Lean と VS Code をインストールする

公式の推奨手順です（[lean-lang.org/install](https://lean-lang.org/install)）。

1. [VS Code](https://code.visualstudio.com/) をインストールする
2. VS Code の拡張機能で **Lean 4**（`leanprover.lean4`）を検索してインストールする
3. 表示されるセットアップガイドに従う
   - 出てこないときは、右上の **∀** ボタン → Documentation → **Docs: Show Setup Guide**
   - **∀** ボタンが見当たらないときは、コマンドパレット（macOS: `Cmd+Shift+P`、Windows: `Ctrl+Shift+P`）で `Lean 4: Docs: Show Setup Guide` を検索して実行する

日本語の解説: [Lean のインストールと elan・Lake の使い方](https://aconite-ac.github.io/how_to_install_lean/)

## 3. Mathematics in Lean の演習ファイルを手に入れる

### 方法 A: VS Code から（簡単）

右上の **∀** ボタン → **Open Project** → **Download Project** → **Mathematics in Lean** を選ぶ。
**∀** ボタンがないときは、コマンドパレットで `Lean 4: Project: Download Project` を検索する。

### 方法 B: ターミナルから

```sh
git clone https://github.com/leanprover-community/mathematics_in_lean.git
cd mathematics_in_lean
lake exe cache get   # Mathlib のビルド済みファイルをダウンロード（数 GB、数分〜十数分）
code .   # 使えなければ VS Code の「ファイル → フォルダーを開く」で mathematics_in_lean を選ぶ
```

`lake exe cache get` を省略すると、Mathlib を自分の PC でビルドすることになり、数時間かかります。必ず実行してください。
{: .note }

### 動作確認

`MIL/C02_Basics/S01_Calculating.lean` を開き、最初の `example` の `rw [mul_comm a b]` の行にカーソルを置きます。しばらく待って、右側の **Lean Infoview** に証明の状態（ゴール）が表示されれば準備完了です。

`sorry` の行に黄色い波線（警告）が出ますが、これは「まだ証明していない演習」という意味なので問題ありません。

## 4. 自分用のコピーを作る

元のファイルを直接書き換えると、教材を更新するときに困ります。`MIL` フォルダを丸ごとコピーして、コピーのほうで演習してください。
VS Code 左側のエクスプローラーで `MIL` フォルダをコピー＆貼り付けして `my_files` に名前を変えるか、ターミナル（macOS・Linux・PowerShell）で次を実行します。

```sh
cp -r MIL my_files
```

## うまくいかないとき

- **ディスク容量:** Lean 本体と Mathlib のキャッシュで数 GB 以上使います。10 GB 程度の空きを用意してください。
- **PC のスペックが足りない、インストールできない:** GitHub Codespaces を使えば、ブラウザだけで演習できます。GitHub にログインして [このリンク](https://codespaces.new/leanprover-community/mathematics_in_lean) を開き、Machine type を **4-core** にして Create codespace を押します。無料枠には月ごとの上限があるので、使い終わったら停止してください。
- **それでもだめなとき:** エラーメッセージのスクリーンショットを持って質問してください。
