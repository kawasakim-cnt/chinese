# Chinese Flashcard Project

## 概要
時代華語① のフラッシュカードアプリ。単一の HTML ファイル (`index.html`) で完結している。

## ファイル構成
- `index.html` — アプリ本体（HTML / CSS / JavaScript すべて含む）

## アーキテクチャ
- フレームワークなし、バニラ JS のみ
- ビルドステップなし。`index.html` をブラウザで直接開けば動作する
- データ（単語リスト）は `index.html` 内の JS 配列に直書き

## 主な機能
- 課（レッスン）選択画面 → フラッシュカード学習画面
- カードをタップして表裏を切り替え（CSS 3D flip アニメーション）
- 答え面タップで次のカードへ進む
- 中国語音声の自動再生（カード表示時）および手動再生ボタン
- 進捗バー表示

## スタイル
- モバイルファースト（max-width: 480px）
- テーマカラー: `#2b6cb0`（青系）

## 注意事項
- 単一ファイル構成を維持する（外部ファイルへの分割は行わない）
- 音声は Web Speech API (`SpeechSynthesisUtterance`) を使用

## ワークフロー
- ユーザーが「OK」と書いたら、git commit & push を行う

## データ管理ルール
- VOCABの単語の分類（topic）や訳（ja）、課（lesson）を変更した際は、必ず以下のファイルも更新すること：
  - `docs/vocab.xlsx` — 上記2つをシートにまとめたExcel（全件・課ごと・品詞ごと）
- Excelの生成は `openpyxl` を使用する
