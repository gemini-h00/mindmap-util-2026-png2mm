# MindMap Markdown to Freeplane

Markdownファイルのドロップ操作だけで、テキスト形式の階層構造を Freeplane 形式（.mm）に変換するWebアプリケーションです。Gemini を活用して、Markdownの構造（見出しやリスト）を自動的に整形・抽出します。

---

## 🌟 特徴

**完全自動解析**  
ファイルをドロップするだけで、AIがMarkdownを解析し、Freeplane形式のファイルに変換します。

**サーバーレス・プライバシー**  
Gemini APIと直接通信します。テキストデータが独自のサーバーに保存されることはありません。

**APIキー保存機能**  
ブラウザの LocalStorage を利用してAPIキーを保存。二回目以降の入力は不要です。

**モダンなUI**  
Material Design 3 に準拠した直感的なインターフェース。

---

## 🚀 使い方

### 1. APIキーの設定

Google AI Studio から Gemini APIキーを取得します。

アプリの「API キー設定」欄にキーを入力し「保存」をクリックします。

---

### 2. ファイルの変換

Markdownファイル（.md / .txt など）をドロップします。

解析完了後、自動的に `.mm` ファイルがダウンロードされます。

---

### 3. Freeplaneで開く

ダウンロードしたファイルを Freeplane で開いて編集できます。

---

## 🛠 デプロイ方法

このプロジェクトは単一の HTML ファイルで構成されています。

以下の静的ホスティングで公開可能です：

- GitHub Pages
- Vercel
- Netlify

---

## ⚠️ Gemini API 利用に関する重要事項（2026-02-23 の修正内容）

本アプリは当初、画像対応の preview モデルを利用していましたが、以下の問題が発生しました。

### 発生した問題

- `429 quota exceeded`
- `free tier limit: 0`
- 公開後に突然 API が失敗する

これは次の理由によるものでした：

1. preview / image モデルは無料枠が無効化される場合がある
2. プロジェクトごとに quota が異なる
3. 無料枠が 0 の場合はリセットされず常に失敗する

---

### 解決策

以下を実施しました：

- 安定したプロジェクト（Gemini API 2）を使用
- 通常の Flash モデルを利用
- quota が十分な APIキーを使用

これにより GitHub Pages 環境でも正常動作するようになりました。

---

## 🔐 APIキー運用のベストプラクティス

公開アプリでは以下を推奨：

- APIキーに HTTP Referrer 制限を設定
- 公開用に専用プロジェクトを使用
- preview モデルを避ける

理由：

APIキーが第三者に使用され quota を消費されるリスクがあるため。

---

## 🧠 技術的背景（重要）

Gemini API の quota は、APIキー単位ではなく
プロジェクト単位で管理されます。

つまり：

- 新しいキーでも同じプロジェクトなら quota を共有します
- 別プロジェクトなら独立します

---

## 📄 技術スタック

- Frontend: HTML5, Tailwind CSS
- AI Model: Gemini Flash
- Format: Freeplane XML (.mm)

---

## ⚖️ ライセンス

MIT License

Created with Gemini.