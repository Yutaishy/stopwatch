# ストップウォッチ＆タイマーWebアプリ 仕様書

## 概要

本システムは、シンプルかつ高機能なストップウォッチとタイマーをWebブラウザ上で動作させるためのHTMLアプリケーションです。PC・タブレット・スマートフォンのいずれでも動作し、Notion等の外部サービスへの埋め込みも可能です。

---

## 構成ファイル

- `index.html`（または `stopwatch-website.html`）
  - 本体HTML・CSS・JavaScriptが1ファイルにまとまっています

---

## 主な機能

### ストップウォッチ機能
- スタート／ストップ
- リセット
- ラップ（区間タイム）記録
- ラップ履歴の表示（最新が上に追加）

### タイマー機能
- 分・秒の設定
- カウントダウン表示
- タイマー終了時の通知
- スタート／ストップ
- リセット

### 共通機能
- モード切り替え（ストップウォッチ⇔タイマー）
- キーボードショートカット対応
  - スペースキー：スタート／ストップ
  - Lキー：ラップ（ストップウォッチモード時のみ）
  - Rキー：リセット
- レスポンシブデザイン
- Notion等へのiframe埋め込み対応

---

## 画面仕様

- 大きなデジタル表示（00:00:00 形式）
- モード切り替えボタン
- タイマー設定入力フィールド（タイマーモード時）
- 操作ボタン（START/STOP, LAP, RESET）
- ラップ履歴リスト（ストップウォッチモード時のみ、最大200pxの高さ、スクロール可）
- モノクロテーマ（黒背景・白文字のみ）

---

## 技術仕様

- HTML5, CSS3, JavaScript（ES6）
- 外部ライブラリ不使用
- 1ファイル完結型
- PC・スマホ両対応
- 埋め込み時のiframeサイズ推奨：幅460px以上

---

## 埋め込み・公開方法

### Notion等への埋め込み
1. 本ファイルを `index.html` として静的ホスティングサービス（Netlify Drop, GitHub Pages等）で公開
2. 発行されたURLをNotionの「Embed」ブロックに貼り付け

### 一時的な公開（開発・テスト用）
- `http-server` + `cloudflared` などで一時的な公開URLを発行可能
  - 例：
    - `npx --yes http-server . -p 8000`
    - `npx --yes cloudflared@npm:cloudflared tunnel --url http://localhost:8000 --no-autoupdate`
- ただし、これらのURLはコマンド実行中のみ有効

### 恒久的な公開（GitHub Pages）
1. GitHubで新しいリポジトリを作成（例: `stopwatch`）
2. `index.html` をリポジトリにアップロード
3. リポジトリの「Settings」→「Pages」へ移動
4. 「Branch」→ `main`、`/（root）` を選択し「Save」
5. 数分後、
   - `https://ユーザー名.github.io/リポジトリ名/` で公開されます
   - 例: `https://yutaishy.github.io/stopwatch/`
6. このURLをNotion等の「Embed」ブロックに貼り付け

※リポジトリが「Private（非公開）」の場合は「Public（公開）」に変更する必要があります。

---

## 注意事項

- 一時公開URL（cloudflared等）はPCやターミナルを閉じると無効になります
- 恒久的な公開にはNetlify DropやGitHub Pages等の利用を推奨
- Notion埋め込み時、外部サービスのiframe制限により表示できない場合があります
- GitHub Pagesはリポジトリが「Public（公開）」でないと利用できません

---

## ライセンス

- MITライセンス（予定）

---

## 作者

- 作成者: あなたのお名前（必要に応じて記入）
- 最終更新日: 2025-06-14 