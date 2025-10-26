# Latex on DevContainer Boilerplate (Updatable)
DevContainer上でLaTex文章を書くリポジトリのボイラープレートを、submodule運用でアップデート可能にしたもの。

### What's this?
VS Codeで、LaTex文章の作成に必要な環境をDevContainerにまとめたものです。このリポジトリは、GitHubの[テンプレートリポジトリ](https://docs.github.com/ja/repositories/creating-and-managing-repositories/creating-a-template-repository)として動作します。

そもそもの元リポジトリの使い方などについては、[taiseiue/latex-devcontainer-boilerplateのREADME.md](https://github.com/taiseiue/latex-devcontainer-boilerplate/blob/main/README.md)をご覧ください。

### Why did you make it?
`taiseiue/latex-devcontainer-boilerplate`はまだ(継続して)開発中のリポジトリです。しかし、ある時点でリポジトリを作成すると、それより後の変更を反映するのに非常に手間がかかるという課題がありました。そこで、[taiseiue/latex-devcontainer-boilerplate](https://github.com/taiseiue/latex-devcontainer-boilerplate)をsubmoduleとして取りこむことで、変更を反映できるようにしたものです。

### Usage
このリポジトリ固有の使用方法のみ説明します。そもそもの使用方法は[taiseiue/latex-devcontainer-boilerplateのREADME.md](https://github.com/taiseiue/latex-devcontainer-boilerplate/blob/main/README.md)をご覧ください。

#### 更新
元リポジトリの変更を受けとるには、次のコマンドを実行します。

```sh
$ git submodule update --remote
```

#### カスタムスタイルの扱い
`/style`以下にカスタムスタイルを追加できます。
`/style/base`はsubmodule管理となっているので触らないでください。

#### 既存のリポジトリを更新可能にする
既存の[taiseiue/latex-devcontainer-boilerplate](https://github.com/taiseiue/latex-devcontainer-boilerplate)をこのようなsubmodule運用にするには、リポジトリルートで以下のコマンドを実行します。

> [!CAUTION]
> 何を実行しようとしているか理解してから実行してください。以下のコマンドを実行すると、.devcontainerディレクトリがリセットされます。もしあなたがdevcontainer.jsonやDockerfileに変更を加えている場合、それが消えてしまいます。

```sh
$ rm -r .devcontainer
$ git submodule add https://github.com/taiseiue/latex-devcontainer-boilerplate.git .base-module
$ ln -s .base-module/.devcontainer .devcontainer
$ ln -s .base-module/style style/base
$ sed -i '' '1a\do '\/workspace\/.base-module\/.latexmkrc' or die "Could not do '\/workspace\/.base-module\/.latexmkrc': $!";' .latexmkrc
```

mystyleも自動更新するようにする場合は、`style/mystyle.sty`を削除してください。

### License
このボイラープレートは、[The MIT License](./LICENSE.txt)のもとで公開します。
submoduleとして読みこんでいるリポジトリについても同様に、[The MIT License](.base-module/LICENSE.txt)となっています。

Copyright (c) 2025 Taisei Uemura  
Released under the [MIT license](./LICENSE.txt)
