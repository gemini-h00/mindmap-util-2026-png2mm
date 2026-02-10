# MindMap NotebookLM to Freeplane
画像のドロップ操作だけで、NotebookLM からエクスポートしたマインドマップ画像を Freeplane 形式（.mm）に変換するWebアプリケーションです。Gemini 2.5 Flash の画像解析能力を活用して、階層構造を自動的に抽出します。

## 🌟 特徴
- 完全自動解析: 画像をドロップするだけで、AIが階層構造をテキスト化し、Freeplane形式のファイルに変換します。
- サーバーレス・プライバシー: Gemini APIと直接通信します。画像データが独自のサーバーに保存されることはありません。
- APIキー保存機能: ブラウザの LocalStorage を利用してAPIキーを安全に保存。二回目以降の入力は不要です。
- モダンなUI: Material Design 3 に準拠した、直感的で美しいユーザーインターフェース。

## 🚀 使い方
1. APIキーの設定:
- Google AI Studio から無料のGemini APIキーを取得します。
- アプリの「API キー設定」欄にキーを入力し、「保存」ボタンをクリックします。
2. 画像の変換:
- マインドマップの画像ファイルを中央のドロップゾーンにドラッグ＆ドロップします。
- 「解析中...」の表示が終わると、自動的に .mm ファイルがダウンロードされます。
3. Freeplaneで開く:
- ダウンロードされたファイルを Freeplane で開き、編集を開始できます。

## 🛠 デプロイ方法
このプロジェクトは単一の index.html ファイルで構成されているため、静的ホスティングサービスで簡単に公開できます。

### おすすめのサービス
- GitHub Pages: リポジトリの設定から数クリックで公開可能。
- Vercel / Netlify: ファイルをアップロードするだけで公開可能。
- [!IMPORTANT] <br>
  Google サイトへの埋め込みについて<br>
  Google サイトなどの iframe 埋め込み環境では、リロードのたびにドメインが変更される仕組みがあるため、APIキーの保存機能（LocalStorage）が正しく動作しない場合があります。永続的な保存を利用したい場合は、GitHub Pages 等の独自のドメインを持つ環境での利用を推奨します。

## 📄 技術スタック
- Frontend: HTML5, Tailwind CSS
- Icon: Google Material Symbols, Inline SVG
- AI Model: Google Gemini 2.5 Flash (gemini-2.5-flash-preview-09-2025)
- Format: Freeplane XML (.mm)

## ⚖️ ライセンス

MIT License

Created with Gemini.
