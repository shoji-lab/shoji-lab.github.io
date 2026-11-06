# 荘司研究室ホームページ

GitHub Pages(Jekyll)で公開している研究室のホームページです。
ページはMarkdown(`.md`)で管理しています。

## 記事の書き方

### 基本方針

- **過去の記事を参考に書く。** `_posts/` にある既存の記事をコピーして書き換えるのが確実です。
- **画像はWebP(`.webp`)にする。** JPEGやPNGのままアップロードしないでください。
- **`main` ブランチに直接コミット・プッシュする**(2026年11月現在の運用)。pushするとそのまま公開されるので、できれば事前にローカルでプレビューしてください。

### ファイルの置き場所

| 種類 | パス                                    | 例                                          |
| ---- | --------------------------------------- | ------------------------------------------- |
| 記事 | `_posts/YYYY-MM-DD-記事名.md`           | `_posts/2023-09-15-DBWS2023.md`             |
| 画像 | `assets/img/posts/YYYYMMDD/画像名.webp` | `assets/img/posts/20230915/DBWS2023_1.webp` |

記事のファイル名の日付と、画像フォルダ名の日付は揃えてください。

### 記事の先頭(front matter)

記事の冒頭には次のブロックを書きます。

```markdown
---
layout: post
title: "【発表】DBWS2023で織田、稲垣が受賞しました"
categories: 発表
title_en: "[Presentation] Mr. Oda and Ms. Inagaki received awards at DBWS 2023"
---
```

- `title`:日本語タイトル。先頭に `【発表】` のようにカテゴリ名を付ける。
- `categories`:次の4つのいずれかを指定する。
  - `論文`
  - `研究室`
  - `発表`
  - `雑談`
- `title_en`:英語タイトル。先頭に `[Presentation]` のようにカテゴリの英語名を付ける。表記は同じカテゴリの過去記事に合わせる。

### 画像の貼り方

```markdown
![写真](/assets/img/posts/20230915/DBWS2023_1.webp "乾杯")
```

パスは `/assets/...` のように先頭に `/` を付けて書きます。

## ローカルでのプレビュー方法

### 初回のみ:環境構築

#### Windows

1. Rubyをインストールする

   ```powershell
   winget install RubyInstallerTeam.RubyWithDevKit.3.3
   ```

   または [RubyInstaller](https://rubyinstaller.org/downloads/) から「Ruby+Devkit 3.3.x (x64)」をインストールする。
   インストール後、**VS Codeを完全に閉じて開き直す**(PATHを反映させるため)。

2. 開発ツールを入れる

   ```powershell
   ridk install
   ```

   選択肢が出たら `3` を入力してEnter。
   終わって同じ質問が再表示されたら、何も入力せずEnterで終了。

3. 依存パッケージを入れる(リポジトリ直下で実行)
   ```powershell
   gem install bundler
   bundle install
   ```

#### Mac

1. Rubyをインストールする(Homebrewを使う場合)

   ```bash
   brew install ruby
   ```

   表示される案内に従ってPATHを設定し、ターミナルを開き直す。
   (macOS標準のRubyは使わないこと)

2. 依存パッケージを入れる(リポジトリ直下で実行)
   ```bash
   gem install bundler
   bundle install
   ```

### 毎回:プレビューの起動

1. サーバを起動する(リポジトリ直下で実行)

   ```
   bundle exec jekyll serve --livereload --baseurl=
   ```

2. VS Codeで `Ctrl+Shift+P`(Macは `Cmd+Shift+P`)→「Simple Browser: Show」→ `http://localhost:4000` を開く。
   エディタと並べておくと、`.md` を保存するたびに自動で再読み込みされる。
3. 終了するときはターミナルで `Ctrl+C`。
