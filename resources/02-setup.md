# 環境構築

出典: [lean-lang.org/install](https://lean-lang.org/install), [手動インストール](https://lean-lang.org/install/manual)
日本語の解説: [Lean のインストールと elan・Lake の使い方（aconite-ac）](https://aconite-ac.github.io/how_to_install_lean/), [園田翔氏の環境構築手順](https://shosonoda.github.io/lean-install/)

## 推奨手順（公式）

1. [VS Code](https://code.visualstudio.com/) をインストール
2. 拡張機能 [Lean 4 (leanprover.lean4)](https://marketplace.visualstudio.com/items?itemName=leanprover.lean4) をインストール
3. VS Code 内のセットアップガイドに従う
   - 開かない場合: 拡張機能のメニュー（∀ アイコン）→ Documentation → **Docs: Show Setup Guide**
   - これで elan（Lean のバージョン管理ツール）などが自動で入る

拡張機能の詳しい使い方: [VS Code Extension Manual](https://github.com/leanprover/vscode-lean4/blob/master/vscode-lean4/manual/manual.md)

## 手動インストール（macOS）

公式は上の推奨手順を強く勧めています。仕組みを理解したいとき用のメモです。

```sh
# elan（Lean のツールチェーン管理。rustup のようなもの）
curl https://elan.lean-lang.org/elan-init.sh -sSf | sh
source $HOME/.elan/env

# VS Code と拡張機能（Homebrew がある場合）
brew install --cask visual-studio-code
code --install-extension leanprover.lean4
```

動作確認: `Test.lean` を作って `#eval 1 + 1` と書き、エラーが出ず `2` が表示されれば OK。

## プロジェクトの作り方（Lake = Lean 付属のビルドツール）

```sh
# 素の Lean プロジェクト
lake new MyLeanProject
cd MyLeanProject && lake build

# Mathlib を使うプロジェクト（数学をやるならこちら）
lake +leanprover-community/mathlib4:lean-toolchain new MyMathlibProject math
cd MyMathlibProject
lake exe cache get   # ビルド済み Mathlib をダウンロード（これをしないとビルドに数時間かかる）
```

既存プロジェクト（教科書のリポジトリなど）を使うとき:

```sh
git clone https://github.com/<owner>/<repo>.git
cd <repo>
lake exe cache get   # Mathlib に依存している場合
```

例: Mathematics in Lean の演習を手元でやる

```sh
git clone https://github.com/leanprover-community/mathematics_in_lean.git
cd mathematics_in_lean
lake exe cache get
code .
```

## Mathlib の更新

```sh
curl -L https://raw.githubusercontent.com/leanprover-community/mathlib4/master/lean-toolchain -o lean-toolchain
lake update
```

## その他のエディタ

- Neovim: [lean.nvim](https://github.com/Julian/lean.nvim)
- VSCodium / Cursor: [Open VSX の拡張機能](https://open-vsx.org/extension/leanprover/lean4)（非公式サポート）
