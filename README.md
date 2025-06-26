# latex-kobe-template

LaTeX（ラテフ）は、レポートや学術論文などの文書作成に適したフリーの組版制御ソフトです。数式や図表の自由な配置編集や、自動的な目次や索引の作成、相互参照の構築など、文書作成のさまざまな機能を備えています。

このレポジトリはlatexを使った、神戸大学の論文作成のためのテンプレートです。

---

目次

- [latex-kobe-template](#latex-kobe-template)
  - [1. 環境設定](#1-環境設定)
    - [1.1 VSCodeとLatexのインストール](#11-vscodeとlatexのインストール)
    - [1.2 VSCodeの設定](#12-vscodeの設定)
  - [2. 運用方法](#2-運用方法)
    - [2.1 本レポジトリのダウンロード](#21-本レポジトリのダウンロード)
    - [2.2 latexのコンパイル](#22-latexのコンパイル)
  - [3. 参考文献の作り方](#3-参考文献の作り方)
    - [3.1 BiBTeXの使い方](#31-bibtexの使い方)
    - [3.2 natbibライブラリの使い方](#32-natbibライブラリの使い方)
  - [4. 各ディレクトリの説明](#4-各ディレクトリの説明)


---
## 1. 環境設定

VS CodeはLaTeX環境としておすすめ。「LaTeX Workshop」によるリアルタイムPDFプレビュー、自動補完、エラー表示が可能で、効率的に作業が進められる。
さらに、軽量で動作が速く、拡張機能やAI連携、Gitによるバージョン管理も可能。

参考

- [【自研究室向け】LaTeX+VSCode環境構築 2023年版](https://qiita.com/fuku_uma/items/e5ad46125a9612320273)
- [LaTeX Workshop を使いこなす](https://qiita.com/Yarakashi_Kikohshi/items/a9357dd469320ffb65a0)
- [VSCode で最高の LaTeX 環境を作る](https://qiita.com/rainbartown/items/d7718f12d71e688f3573)

---

### 1.1 VSCodeとLatexのインストール

**MacOSの場合**  
homebrewでいずれもインストールできます。ターミナルから以下のコードを実行してください。

```bash
# VSCode の導入
brew install visual-studio-code --cask 
# LaTeX環境(GUI無)の導入
brew install --cask mactex-no-gui 
# 管理者権限でLaTeXパッケージの更新
sudo tlmgr update --self --all 
# 管理者権限で用紙サイズの変更
sudo tlmgr paper a4 
```

MacOSでhomebrewを使っていない人はいますぐ使えるようになってください。  
これが使えるようになると、今後の全ての環境構築が圧倒的に楽になります。  

- [【macOS版】初心者でもわかる！Homebrewのインストール手順を徹底解説](https://zenn.dev/inablog/articles/5e790c9fbdad20)
- [2024年版 Homebrew完全ガイド：macOSのパッケージマネージャーを使いこなす](https://qiita.com/yu_uk/items/73654985fb1caeab4cec)


**Windowsの場合**  
動作確認をしていないので、以下の資料を読んでインストールしてください。  
[【大学生向け】LaTeX完全導入ガイド Windows編 (2022年)](https://qiita.com/passive-radio/items/623c9a35e86b6666b89e)

---


### 1.2 VSCodeの設定

初めてVSCodeを使う時は、日本語に設定しておくと楽。
[Visual Studio Code（VSCode）の設定をしてみた](https://qiita.com/TS1engineer/items/1b54f65ee87cb49582f5)

1. 左の「拡張機能」タブから「Latex-Workshop」をインストール
2. 左下の歯車マークから「設定」を開き、右上の「設定(JSON)を開く」をクリック
3. settings.jsonが開かれるので、本レポジトリの同名ファイルの中身をコピペする。
Windowsの場合は[こちら](https://qiita.com/fuku_uma/items/e5ad46125a9612320273#:~:text=VSCode%E3%81%AE%E8%A8%AD%E5%AE%9A-,Windows%E3%81%AE%E5%A0%B4%E5%90%88,-Mac%E3%81%AE%E5%A0%B4%E5%90%88)を参考にする。

---

## 2. 運用方法

### 2.1 本レポジトリのダウンロード

本レポジトリ「latex-kobe-template」をダウンロードする方法は大きく2つ。

1. zipファイルを直接ダウンロードする
   1. [latex-kobe-template](https://github.com/nagampere/latex-kobe-template)にアクセスする
   2. 緑色の「< > Code▽」をクリックし、「Download ZIP」を実行
2. 【おすすめ】Githubからフォーク(fork)
   1. [latex-kobe-template](https://github.com/nagampere/latex-kobe-template)にアクセスする
   2. 「< > Code▽」の右上にある「Fork」をクリックし、latex-kobe-templateをコピーした新たなレポジトリ(ホストは自身)を作成する
   3. 新たなレポジトリをgit cloneでローカルに読み込む

**何故Githubを使った方が良いのか？**

1. **バージョン管理が容易**
   - 過去の変更履歴を保存し、特定のバージョンに戻すことが可能。
   - 変更点が明確になり、誰が何を修正したかを把握できる。
2. **バックアップとしての活用**
   - GitHubにリポジトリを保存することで、データが安全に保管される。
   - ローカルPCのトラブルやデータ消失のリスクを軽減。
3. **複数デバイスでの作業が可能**
   - クラウド上のリポジトリを利用することで、どのデバイスからでも最新状態にアクセスできる。
   - 自宅や研究室など、環境を問わず作業を続行可能。
4. **GitHub copilotの援助**
   - 分からないコードやエラーに対して、説明や修正をVSCode内で求められる。
   - コードを書き始めると、次に書くべきコードを予測して提案してくれる。

Gitの使い方については以下を参照

- [Githubリポジトリのfork（フォーク/派生）の使い方・clone（クローン）との使い分け](https://www.kagoya.jp/howto/rentalserver/webtrend/githubfork/)
- [【Git】Git初期設定 for Mac OS](https://qiita.com/mmikri/items/89508e9435339fcb97e1)
- [【入門】VSCodeとGitHubの連携手順・使い方をわかりやすく解説](https://www.kagoya.jp/howto/rentalserver/webtrend/vscode/)
- [サル先生のGit入門](https://backlog.com/ja/git-tutorial/)

### 2.2 latexのコンパイル

main.texをコンパイルしてPDFファイルを作成する方法は大きく2つ。

1. latex-workshopタブから実行する
   1. 任意のtexファイルを開く
   2. 左のタブに「TEX」と表記されたlatex-workshopのタブをクリックして開く
   3. 「コマンド」内の「LaTeXプロジェクトをビルド」をクリックでPDFを更新
   4. 「LaTeX PDFを表示」をクリックしてPDFを開く
2. texファイルを保存して自動更新する
   1. 任意のtexファイルを開く
   2. 「control + S」でファイルを保存する

settings.jsonの設定で、保存時に自動でPDFが保存される。  
動作が重いときは、settings.jsonの"latex-workshop.latex.autoBuild.run"を"off"にする。  
もしくは、main.texを\documentclass[report, 12pt, a4paper, draft]{jsbook} にしてdraftモードを有効にし、画像の出力を省略する。

---

## 3. 参考文献の作り方

### 3.1 BiBTeXの使い方

BiBTeXとは、Latexの参考文献用のデータベースで、通常.bibファイルで管理する。bibファイルを直接編集することはなく、ZoteroやPapershipでまとめて出力する。latex内では本文中で引用された文献のみが目録に登録されるので、細かい文献管理が不要になる。

参考

- [BiBTeXとは](https://qiita.com/SUZUKI_Masaya/items/14f9727845e020f8e7e9)
- [VSCode + Zotero + BibTeXによる論文執筆ワークフロー](https://zenn.dev/nicetak/articles/zotero-tex-bibtex)
- [Zoteroから参考文献リストを自動エクスポートする (PandocとZoteroで参考文献：前編)](https://zenn.dev/sky_y/articles/pandoc-advent-2020-bib1)

### 3.2 natbibライブラリの使い方

natbibとは、文献管理を目的としたlatexライブラリの一つで、```\usepackage{natbib}```で利用可能になる。　　
```\usepackage[options]{natbib}```や```\setcitestyle{options}```で設定ができる。

初期設定

- ```\renewcommand{\bibname}{参考文献}```
  - 文献目録のタイトルを「参考文献」にする
- ```\setcitestyle{super,sort&compress,open={},close={)}}```
  - "super"で、右肩上がり数字(山田 (2020) <sup>3\)</sup> )にする。
  - "open={},close={)}"で、「3\)」のスタイルにする。
- ```\setcitestyle{authoryear}```
- ```\bibliographystyle{backmatter/kucivil.bst} ```
  - 設定の基準は[経済学におけるBibTeXの利用](https://qiita.com/shiro_takeda/items/92adf0b20c501548355e)
  - 神戸大学市民工学の書式に変更

参考

- [Natbibチュートリアル: BibTeXを使ったLaTeXでの参考文献管理](https://bibtex.eu/ja/natbib/)
- [natbibチートシート](https://gking.harvard.edu/files/natnotes2.pdf)
- [【LaTeX】BibTeXのスタイル76個一覧](https://mathlandscape.com/latex-bibstyles/)

---

## 4. 各ディレクトリの説明

```{}
latex-kobe-template
├── main.tex                   # 本文のメインファイル（全体をまとめる）
├── digest.tex                 # 要旨のメインファイル
├── preamble
│   ├── packages.tex           # 使用するパッケージ
│   ├── settings.tex           # ドキュメント設定（章構成、引用スタイルなど）
│   └── macros.tex             # カスタムコマンド・マクロ定義
├── frontmatter
│   ├── title.tex              # タイトル
│   ├── abstractEN.tex         # 英文要旨
│   ├── abstractJP.tex         # 和文要旨
│   └── contents.tex           # 目次・図表目次
├── mainmatter                 # 各章ごとの内容
│   ├── chapter1.tex
│   ├── chapter2.tex
│   ├── chapter3.tex
│   ├── chapter4.tex
│   └── chapter5.tex
├── backmatter
│   ├── citations.tex          # 参考文献リスト
│   ├── kucivil.bst            # 引用スタイルの設定ファイル
│   ├── references.bib         # bibtexファイル
│   ├── appendix.tex           # 付録
│   └── acknowledgements.tex   # 謝辞
├── figure                     # 図専用のディレクトリ
│   └── figure_sample.png
├── table                      # 表専用のディレクトリ
│   ├── table_sample1.tex
│   └── table_sample2.tex
├── digest                     # 要旨の設定ファイル
│   └── settings.tex
├── output
├── log                        # ログファイルや中間生成物
├── template                   # テンプレート関連
├── main.pdf            　      # 本文の最終出力物(ignore)
├── digest.pdf                 # 要旨の最終出力物(ignore)
├── settings.json              # settings
└── README.md
```

---