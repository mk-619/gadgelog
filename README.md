# gadgelog

Hugo を用いて構築した個人ブログである．  
学習内容，ガジェット，日常の記録を整理し，  
GitHub Pages を用いて静的サイトとして公開している．  

---

## 使用技術
- Hugo (Extended)
- GitHub Actions
- GitHub Pages
- Markdown

---

## ディレクトリ構成

gadgelog/
├─ archetypes/
├─ assets/
├─ content/
├─ data/
├─ i18n/
├─ layouts/
├─ public/
├─ resources/
├─ static/
├─ themes/
├─ .gitmodules
├─ .hugo_build.lock
├─ hugo.toml
└─ README.md


---

## 各ディレクトリ・ファイルの役割

### archetypes/
`hugo new` コマンドで記事を生成する際の  
Markdown テンプレートを定義するディレクトリである．  

---

### assets/
Hugo のパイプライン（Hugo Pipes）で処理される  
CSS や画像などのアセットを配置するためのディレクトリである．  
SCSS などの変換処理を行う場合に使用される．  

---

### content/
ブログの記事や固定ページを配置するディレクトリである．  
このディレクトリ以下の構成が，  
そのまま Web サイトのページ構成に対応する．  

例：  
- `_index.md`：トップページ  
- `manabi/`：学びカテゴリ  
- `gadget/`：ガジェットカテゴリ  

---

### data/
JSON，YAML，TOML 形式のデータファイルを配置するディレクトリである．  
テンプレートから参照される補助データとして使用される．  

---

### i18n/
多言語対応用の翻訳ファイルを配置するディレクトリである．  
現在は将来拡張を見据えて保持している．  

---

### layouts/
Hugo のテンプレート（HTML）を配置するディレクトリである．  
テーマを上書き・カスタマイズする場合に使用される．  

---

### public/
Hugo によって生成された **静的サイトの出力先**である．  
GitHub Actions では，このディレクトリの内容を  
GitHub Pages にデプロイしている．  

※ 通常は手動で編集しない．  

---

### resources/
Hugo Pipes によって生成された  
中間生成物やキャッシュが格納されるディレクトリである．  

---

### static/
画像，favicon，CSS など，  
そのまま公開される静的ファイルを配置するディレクトリである．  
この中のファイルは，ビルド時にそのまま `public/` にコピーされる．  

---

### themes/
Hugo のテーマを配置するディレクトリである．  
本リポジトリでは，`ananke` テーマを Git submodule として利用している．  

---

### .gitmodules
Git submodule（テーマ）の設定を記述したファイルである．  

---

### .hugo_build.lock
Hugo のビルド時に生成されるロックファイルである．  
ビルドの整合性を保つために使用される．  

---

### hugo.toml
Hugo の設定ファイルである．  
サイトのタイトル，言語，テーマ，メニュー構成などを定義している．  

---

### README.md
本リポジトリの概要および構成を説明する文書である．  

---


## Git の基本的な使い方（このリポジトリ用）

本リポジトリは，Git を用いて変更履歴を管理し，  
GitHub へ push することで Web サイトを自動公開する構成になっている．  

以下では，本リポジトリを運用するために必要な  
最低限の Git 操作のみを説明する．  

---

### 現在の状態を確認する
作業前・作業後には，必ず次を実行する．  

```bash
git status
```

このコマンドにより，  
どのファイルが変更されているか，  
commit 可能な状態かどうかを確認できる．  

---

### 変更を記録する（commit）
ファイルを編集した後は，次の手順で変更を記録する．  

#### 1．commit したいファイルを指定する
```bash
git add ファイル名
```

例：README.md を追加する場合  
```bash
git add README.md
```

すべての変更をまとめて追加する場合は次を用いる．  
```bash
git add .
```

#### 2．変更内容を commit として記録する
```bash
git commit -m "変更内容の要約"
```

例：  
```bash
git commit -m "update README"
```

---

### GitHub に反映する（push）
commit が完了したら，GitHub に反映する．  

```bash
git push
```

本リポジトリでは，  
main ブランチへの push をトリガーとして  
GitHub Actions が自動実行され，  
GitHub Pages にサイトが公開される．  

---

### よく使う一連の流れ
通常の作業は，次の流れで完結する．  

```bash
git status
git add .
git commit -m "変更内容"
git push
```

---

### 注意事項
- git add を実行しないと commit はできない  
- git status を確認すれば，次に何をすべきか判断できる  
- public ディレクトリは自動生成物であり，手動で編集しない  

---

### トラブル時
commit や push でエラーが出た場合は，  
まず次を実行して状態を確認する．  

```bash
git status
```

エラーメッセージが表示された場合は，  
内容を省略せず確認すること．  


## ローカルでの起動方法
プロジェクト直下で次を実行する． 

```bash
hugo server -D --baseURL "http://localhost:1313/" --appendPort=false
```

ブラウザで次にアクセスする．  

http://localhost:1313


---

## 公開方法
`main` ブランチに push すると，  
GitHub Actions により Hugo ビルドが実行され，  
GitHub Pages に自動でデプロイされる．  

公開 URL：  

https://mk-619.github.io/gadgelog/


---

## 補足
- 本リポジトリはサーバを自前で運用していない  
- 静的ファイルのみで構成されている  
- Windows／macOS のどちらでも同一手順で運用可能  

