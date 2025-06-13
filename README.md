# ストップウォッチWebアプリ 仕様書

## 概要

本システムは、シンプルかつ高機能なストップウォッチをWebブラウザ上で動作させるためのHTMLアプリケーションです。PC・タブレット・スマートフォンのいずれでも動作し、Notion等の外部サービスへの埋め込みも可能です。

---

## 構成ファイル

- `index.html`（または `stopwatch-website.html`）
  - 本体HTML・CSS・JavaScriptが1ファイルにまとまっています

---

## 主な機能

- スタート／ストップ
- リセット
- ラップ（区間タイム）記録
- ラップ履歴の表示（最新が上に追加）
- キーボードショートカット対応
  - スペースキー：スタート／ストップ
  - Lキー：ラップ
  - Rキー：リセット
- レスポンシブデザイン
- Notion等へのiframe埋め込み対応

---

## 画面仕様

- 大きなデジタル表示（00:00:00 形式）
- 操作ボタン（START/STOP, LAP, RESET）
- ラップ履歴リスト（最大200pxの高さ、スクロール可）
- ダークテーマ（黒背景・白文字）

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

---

## 注意事項

- 一時公開URL（cloudflared等）はPCやターミナルを閉じると無効になります
- 恒久的な公開にはNetlify DropやGitHub Pages等の利用を推奨
- Notion埋め込み時、外部サービスのiframe制限により表示できない場合があります

---

## ライセンス

- MITライセンス（予定）

---

## 作者

- 作成者: あなたのお名前（必要に応じて記入）
- 最終更新日: 2025-06-13 