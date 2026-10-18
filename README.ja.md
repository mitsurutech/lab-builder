# lab-builder：教員の公開 GitHub リポジトリからコンテナラボのイメージをビルド

[English](README.md) | [Français](README.fr.md) | [日本語](README.ja.md) | [Español](README.es.md)

教員の公開 GitHub リポジトリから、[MitsuruTech のコンテナラボ](https://mitsurutech.co.uk/ja/help/labs)のサービスをビルドし、
各イメージを
[`ghcr.io/mitsurutech/lab-images`](https://github.com/orgs/mitsurutech/packages/container/package/lab-images) に公開します。

ラボは、compose ファイルで記述されたコンテナの集まりです。教員が、compose ファイルに `build:` があるラボのコミットを
公開すると、ウェブサイトはビルドするサービスごとに1回、ここで `Build a lab image` を起動します。
イメージには `<lab>-<service>-<commit>` というタグが付き、ラボのマシンはそこから取得します。
教員の Dockerfile がラボのマシン上で実行されることは一切ありません。

**公開されるものは誰でも見られます。** ビルドされるのは公開リポジトリだけです。Dockerfile が
コピーするものや、`ENV` や `ARG` で設定した値は、イメージを取得した人なら誰でも読めます。
秘密の値は `env_file` に置いてください。`env_file` はコピーの起動時にサイトが追加するもので、
イメージには組み込まれません。

ビルドは GitHub 自身のランナーで実行され、ほかに何もできないトークンを使ってウェブサイトだけが起動します。
ここにあってはならないイメージを報告するには、mitsurutech.co.uk の
[お問い合わせページ](https://mitsurutech.co.uk/ja/contact)に記載のアドレスへご連絡ください。

## ライセンス

この作品は [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) でライセンスされています。Mitsuru Technologies Ltd のクレジットを表示し、商用に使わず、これをもとに作ったものを同じライセンスで共有するなら、学習と授業のために共有・改変できます。全文は `LICENSE` ファイルにあります。

## このリポジトリについて

[Mitsuru Technologies](https://mitsurutech.co.uk/ja) が
[MitsuruTech ラーニングプラットフォーム](https://mitsurutech.co.uk/ja/learning)のために作りました。Python、Java、Go、Node、SQL、
Linux をブラウザーで学べる、学校向けのプラットフォームで、コンテナのラボ、GitHub からデプロイする Web アプリ、
自動で採点されるクイズがあります。アカウントなしでコードを試せる
[プレイグラウンド](https://mitsurutech.co.uk/ja/playground)もあります。

クラスで教えていますか？ [料金](https://mitsurutech.co.uk/ja/pricing)を確認するか、[学校のアカウントを作成](https://mitsurutech.co.uk/ja/signup)してください。
