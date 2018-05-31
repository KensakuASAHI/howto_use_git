初心者向け GIT 使い方メモ
===================

---

# GITのコマンド

## はじめに使うコマンド

- init  新規に空のリポジトリを作成する
- clone 新しいディレクトリにリポジトリを複製する

## 日常のコマンド

- add インデックスにファイルを追加する
  - git add \<file\>
  - git add *.c カレントディレクトリの全ての.cファイルをaddする．
  - git add -u (git add --update) 以前コミットしたファイルで，更新・削除されたファイルをaddする（新規ファイルは対象外）．
  - git add -A (git add -all) 変更のあった全てのファイルをaddする．
  - git add . カレントディレクトリ以下の変更のあった全てのファイルをaddする．
- commit 変更を記録する，追加とコミット(-a)
- status 現在のブランチの状態を表示する
- show コミットの変更点等を表示
- log コミットの履歴を表示する

## ブランチ

- branch ブランチの作成(ブランチ名を指定)，一覧表示(引数なしの場合)，削除(-d ブランチ名)
- checkout ブランチの切り替え，作成と切り替え(-b ブランチ名)
- merge ブランチを結合（マージ）する
- tag タグを付ける

## 他のリポジトリから

- fetch 他のリポジトリからファイルなどを取得する
- pull = fetch + merge
- push 他のリポジトリへ更新を反映する

## たまに使う

- mv ファイルやディレクトリの名前を変更する
- rm ファイルを削除する

## その他

- grep gitが管理しているファイルの内容を検索する
- diff コミット間やコミットとワーキングツリーとの間の変更点を表示

## 少し危険なコマンド

- reset HEADの指すコミット位置を変更する
  - addを取り消す．git reset
- rebase マージするもう一つの方法

## ほとんど使わない（知っていれば便利かも）

- bisect 二分探索で不具合が混入したコミットを探す

---

# HELP message

```
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Reapply commits on top of another base tip
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch

   push       Update remote refs along with associated objects
```

