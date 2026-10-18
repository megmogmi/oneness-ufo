# We are Oneness — UFOセンター応援サイト

HTML・CSS・JavaScriptだけで動く静的なサイトです。ビルド、外部パッケージのインストール、APIキー、環境変数は不要です。

## ファイル構成

- `dist/index.html`：ホームページ
- `dist/style.css`：デザイン
- `dist/app.js`：参加メッセージ作成・コピー・保存
- `dist/assets/`：公開する画像
- `vercel.json`：Vercelの公開設定
- `.gitignore`：秘密情報やローカル設定をGitに含めないための除外設定
- `.vercelignore`：Vercelに渡さないファイルの設定

## GitHubに保存する

1. GitHubで新しいリポジトリを作成します。名前の例：`oneness-ufo`。
2. ソースコードは `Private` で保存できます。サイトの一般公開とは別の設定です。
3. 作成時に「Add a README file」（画面によっては「Add README」）をオンにすると、作成後に「Add file」が使えます。
4. 「Add file」→「Upload files」を押します。
5. このフォルダーの**中身**をアップロードします。`dist`フォルダー、`vercel.json`、`README.md`を同じ階層に置いてください。隠しファイルの `.gitignore` と `.vercelignore` も含める場合、MacのFinderで `Command + Shift + .` を押すと表示できます。
6. 「Commit changes」を押して保存します。ZIPファイル自体をアップロードしないでください。

GitHubの最上位に `dist` と `vercel.json` が見えていれば正しい配置です。`oneness-ufo-vercel` という外側のフォルダーを一段増やさないでください。

## Vercelで公開する

1. Vercelにログインします。
2. 「Add New...」→「Project」を押します。初回画面では「Add New Project」などと表示される場合があります。
3. 「Import Git Repository」でGitHubを接続し、`oneness-ufo` の「Import」を押します。リポジトリが見えない場合は、GitHub連携の設定でこのリポジトリへのアクセスを許可してください。
4. 以下を確認します。

| 項目 | 設定 |
| --- | --- |
| Project Name | `oneness-ufo` など任意の名前 |
| Framework Preset | `Other` |
| Root Directory | リポジトリの最上位。初期値のまま（`.` 相当） |
| Build Command | 空欄。ビルドしない |
| Output Directory | `dist` |
| Install Command | 初期値のまま。依存パッケージなし |
| Environment Variables | 追加しない |

`vercel.json` にFramework・Build Command・Output Directoryを設定済みです。Root Directoryを `dist` に変更しないでください。

5. 「Deploy」を押します。
6. 完了後に「Visit」または表示された `https://...vercel.app` のURLを開きます。
7. ログアウトした別のブラウザーやプライベートウィンドウで、本番URLがログインなしで開けることを確認します。認証が求められる場合は、Vercelの対象プロジェクトの「Settings」→「Deployment Protection」で本番環境の公開範囲を確認してください。プレビュー専用URLではなく、本番ドメインを共有します。

## 安全に使うために

- このフォルダーにはAPIキー・パスワード・以前の公開サービスの設定を含めていません。
- `dist` 内のすべてのファイルは、一般公開されます。秘密情報を追加しないでください。
- `.gitignore` は、HTMLやJavaScript本文に書いた秘密情報までは防げません。
- 将来APIを追加する場合、秘密のキーはブラウザー向けファイルに書かず、Vercelのサーバー側の処理と環境変数で管理してください。
- 参加受付の窓口は未定です。現在はメッセージを作るだけで、主催者に送信しません。
- 画像は提供された構想資料から使用しています。

## 確認範囲

公開設定JSON、JavaScriptの構文、HTMLから参照する画像・CSS・JS、ページ内リンク、秘密情報の既知の形式をローカルで確認しています。Vercel上でのデプロイ結果は、実際にDeployを押した後に確認してください。

## 公式ガイド

- https://vercel.com/docs/builds/configure-a-build
- https://vercel.com/docs/git
- https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
