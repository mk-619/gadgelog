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

## ローカルでの起動方法
プロジェクト直下で次を実行する． 

`hugo server -D`

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

