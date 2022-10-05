# MyProofContainer_VSCode

ブログや職務経歴書など、Markdownで文章を書く際に文章を校正してくれる仮想環境を作成しました。
VSCode上で動かすことを前提に作っています。

やっていることはtextlintなど、様々な先人たちの知恵をDockerfileなどにまとめて、VSCodeですぐに試せるようにしました、というだけです。
しかし意外なことに、これらをまとめて1つの環境にしている方は意外といなかったので、今回公開するに至りました。
もしすでにいたらすいません、その場合は二番煎じです。

## できること

VSCode上で文章を書きながら、自動で校正までやってくれます。
上図では試しにデタラメな文章を書いてみましたが、接続詞の繰り返しや、ら抜き言葉をしっかりと検知できていることが分かります。

VScodeの拡張機能として静的な解析ツールや、PDF化できるツールも入れてあります。
またgitもコンテナー内で使用できるようにしてあるので、文書をgit管理したい方もすぐに使えます。

## 手順

以下の手順は2022/10/2現在のものです。

1. VSCode, Git, Docker Desktopをダウンロードしておく。
2. Gitのユーザー名とEmailアドレスを設定する。これを飛ばすとコンテナー内からGithubにpushなどができないか、一手間必要になるかもしれません。（参考：https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup#_first_time）
3. このリポジトリをforkする。
4. forkしたリポジトリをcloneする。
5. cloneしたフォルダをvscodeで開く。（参考：https://www.youtube.com/watch?v=u3PMR8voOo0）
6. VSCodeの拡張機能[Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)をインストールする。
7. Ctrl (command) + Shift + P を入力、`Remote-Containers: Reopen in Container`を選択する。
8. コンテナーが立ち上がったら、執筆作業を開始できます。

## （おまけ）なぜVScodeにこだわっているか

textlintとDockerを使って１つの環境を用意されている方は何名かいました。
しかし私が作成したリポジトリには、あえてVSCodeしか使えないようなファイルがあります。
これには理由があって、文章校正を「書きながら」注意するレベルで行って欲しかったからです。
例えばCI上で自動修正されるようにしてしまうと、あえて崩した書き方をしている部分も修正されてしまう恐れがあります。
例えtextlintのルールには反していても、書き手が納得していればOKという使い方もできるように、VScodeとtextlintのextensionを採用しています。

## 終わりに

今回Dockerを使った環境構築に初めて自力で挑戦してみました。
正直奥が深い技術で、まだ使いこなせていない感は否めませんが、最低限調べながら実装できるレベルにはなれたのかなと感じてます。
