# Latex on DevContainer Boilerplate (Updatable)
DevContainer上でLaTex文章を書くリポジトリのボイラープレートを、submodule運用でアップデート可能にしたもの。

### What's this?
VS Codeで、LaTex文章の作成に必要な環境をDevContainerにまとめたものです。このリポジトリは、GitHubの[テンプレートリポジトリ](https://docs.github.com/ja/repositories/creating-and-managing-repositories/creating-a-template-repository)として動作します。

そもそもの元リポジトリの使い方などについては、[taiseiue/latex-devcontainer-boilerplateのREADME.md](https://github.com/taiseiue/latex-devcontainer-boilerplate/blob/main/README.md)をご覧ください。

### Why did you make it?
`taiseiue/latex-devcontainer-boilerplate`はまだ(継続して)開発中のリポジトリです。しかし、ある時点でリポジトリを作成すると、それより後の変更を反映するのに非常に手間がかかるという課題がありました。そこで、[taiseiue/latex-devcontainer-boilerplate](https://github.com/taiseiue/latex-devcontainer-boilerplate)をsubmoduleとして取りこむことで、変更を反映できるようにしたものです。

### Usage
このリポジトリ固有の使用方法のみ説明します。そもそもの使用方法は[taiseiue/latex-devcontainer-boilerplateのREADME.md](https://github.com/taiseiue/latex-devcontainer-boilerplate/blob/main/README.md)をご覧ください。

#### カスタムスタイルの扱い
`/style`はsubmodule管理となっているので、リポジトリで独自のスタイルをあてるには、`/mystyle`を使ってください。

**使用例**

```tex
\documentclass[autodetect-engine,dvipdfmx,ja=standard,a4paper,12pt]{bxjsarticle}

\usepackage{mystyle}

\begin{document}
\title{レポート \\
  レポートタイトル
}
```