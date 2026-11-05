# PDFまとめる君：Codex適用記録
確認日：2026-11-05（日本時間）。対象：ken-tak-steam/pdf_matomerukun の取得時の既定ブランチ。アプリ本体の改修・実機テストは今回実施していない。

## 確認した現状
約6.0MBのHTML本体をblob取得で確認。外部script srcなし、CSP connect-src 'none'。現状のライセンス表示はdetailsで、共通ダイアログへの移行候補。READMEは文字・ベクター・外部/内部リンク・回転保持と、削除先リンク除去を説明。今回の実行テストは未実施。

## 本体ライセンス
独自の非商用条件の全文をindex.html内で確認。LICENSE、LICENSE.md、LICENSE.txtは今回のAPI取得では404。READMEのLICENSE参照と一致していないため、別名ファイルの有無を追加確認してから既存本文を独立ファイルに保存する。新しいライセンスを選び直さない。

## 依存ライブラリ・付属データ
READMEにpdf-lib 1.17.1とpdfjs-dist 5.6.205。index.htmlの内蔵assets.licensesにMIT、Apache-2.0、Adobe CMap条件、Foxit/PDFium系フォント条件、SIL OFL 1.1の文面を確認。個々の内蔵バイナリとの対応・推移的依存の網羅は未完了。README記載のTHIRD_PARTY_NOTICES.txt、core.js、build.pyは今回取得404。外部ファイルがあるとの記述だけで配布完了としない。

## 次の適用順序
優先1：READMEと実ファイルの整合、編集用ソースと再現可能なビルドの確保。優先2：内蔵通知を実物と対応付けて独立ファイルにも保存。優先3：既存のリンク再設定を維持し、ページ移動・削除・番号追加の回帰確認。表示変更は別PRで最小差分にする。

## 取得根拠
- README.md: dc2853418387b87131e64ef2d95c6bec89752e3b
- LICENSE: 取得404（ファイル不在の断定は別名等の確認後）
- index.html: 6a4e333e20d46250a8db5fff5b167ad8ca6c146f
ソース：https://github.com/ken-tak-steam/pdf_matomerukun
取得したコードとREADMEの記述、過去チャットの報告は区別する。取得時点のファイル単位のSHAであり、リポジトリ全体の同一コミットを保証しない。

## 今回の変更範囲
AGENTS.mdとdocs/CODEX_APP.md、docs/CODEX_TEMPLATES.mdの追加のみ。既存HTML・ライセンス本文・依存バージョン・公開設定は変更しない。共通ルールは目標であり、現アプリが全条件を満たす証明ではない。
