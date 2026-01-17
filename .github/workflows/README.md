# .github/workflows について

このディレクトリは，GitHub Actions による自動処理（CI / CD）を定義するためのフォルダである．  
本リポジトリでは，Hugo で生成した静的サイトを GitHub Pages に自動で公開するために使用している．  

---

## ディレクトリ構成

.github/
└─ workflows/
├─ gh-pages.yml
└─ README.md


---

## 各ファイルの役割

### gh-pages.yml
GitHub Actions の workflow 定義ファイルである．  

このファイルには，以下の処理内容が記述されている．  

- main ブランチへの push をトリガーとして処理を開始する  
- Hugo（Extended）をセットアップする  
- Hugo により静的サイトをビルドする  
- 生成された public ディレクトリを成果物としてアップロードする  
- GitHub Pages に自動でデプロイする  

これにより，  
ローカルで記事を作成し，GitHub に push するだけで，  
自動的に Web サイトが更新・公開される．  

---

### README.md
この README ファイルは，  
`.github/workflows` ディレクトリの目的と，  
その中に配置されているファイルの役割を説明するための文書である．  

GitHub Actions の設定は，  
一見すると分かりにくくなりやすいため，  
後から見返したときや，他者がリポジトリを参照したときに，  
「なぜこのフォルダが存在するのか」「何をしているのか」が分かるようにする目的で設置している．  

---

## 補足
- このディレクトリ以下のファイルは，Web サイトの表示内容には影響しない  
- Hugo の content や layout とは役割が完全に分離されている  
- GitHub Pages を利用した自動公開を行う場合，`.github/workflows` は必須となる.  

