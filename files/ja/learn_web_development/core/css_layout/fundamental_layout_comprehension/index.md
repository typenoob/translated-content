---
title: "課題: 基礎的なレイアウトの理解"
slug: Learn_web_development/Core/CSS_layout/Fundamental_Layout_Comprehension
l10n:
  sourceCommit: 5b20f5f4265f988f80f513db0e4b35c7e0cd70dc
---

{{LearnSidebar}}

{{PreviousMenuNext("Learn_web_development/Core/CSS_layout/Media_queries", "Learn_web_development/Core/Scripting", "Learn_web_development/Core/CSS_layout")}}

このモジュールを乗り越えてきたならば、今日 CSS レイアウトを行うために知っておくべきことや、より古い CSS を使って作業するために必要なことの基本についてはすでに説明しているはずです。 このタスクでは、さまざまなテクニックを使用して簡単なウェブページレイアウトを作成することによって、知識の一部をテストします。

## 出発点

HTML と CSS、そして 6 枚の画像一式は[こちら](https://github.com/mdn/learning-area/tree/main/css/css-layout/fundamental-layout-comprehension)からダウンロードすることができます。

HTML 文書とスタイルシートはコンピューターのディレクトリーに保存し、画像は `images` という名前のフォルダー内に追加してください。ブラウザーに `index.html` ファイルを開くと、下記の画像のような、基本的なスタイル設定はあるがレイアウトがないページができるはずです。

![レイアウト課題の出発点。要素はきれいにレイアウトされていません。左側に5つのリンクがある黒いナビバーの上にウェブサイトのタイトルがあり、以下ブログ記事のタイトルと記事コンテンツが続きます。ブログタイトルとブログコンテンツの間には、左側に配置された写真があります。](layout-task-start.png)

この出発点には、通常フローでブラウザーに表示されるレイアウトのコンテンツがすべて含まれています。

また、[CodePen](https://codepen.io/)、[JSFiddle](https://jsfiddle.net/)、[Glitch](https://glitch.com/) のようなオンラインエディターを使用することもできます。
オンラインエディターを使用する場合、画像をアップロードし、 `src` 属性の値を新しい画像の場所を指すように置き換える必要があります。

> [!NOTE]
> 行き詰まった場合は、[コミュニケーションチャンネル](/ja/docs/MDN/Community/Communication_channels)のいずれかに連絡してください。

### プロジェクト概要

未加工の HTML、基本的な CSS と画像が指定されたので、これでデザインのレイアウトを作成する必要があります。

### あなたの課題

あなたは今レイアウトを実装する必要があります。 達成する必要があるタスクは次のとおりです。

1. ナビゲーション項目を、項目間に等間隔のスペースを置いて、1 行に並べて表示します。
2. ナビゲーションバーはコンテンツと一緒にスクロールし、ビューポートの上部に到達するとそこに固定されるべきです。
3. 記事の中にある画像は、それを囲むテキストを持つべきです。
4. {{htmlelement("article")}} 要素と {{htmlelement("aside")}} 要素は、2 列のレイアウトとして表示するべきです。 ブラウザーウィンドウが小さくなると列が狭くなるように、列は柔軟なサイズにするべきです。
5. 写真は、画像間に 1 ピクセルの間隔を空けて 2 列のグリッドとして表示するべきです。

## ヒントとコツ

このレイアウトを実現するために HTML を編集する必要はなく、使用するべきテクニックは次のとおりです。

- 位置指定
- 浮動ボックス
- フレックスボックス
- CSS グリッドレイアウト

これらの課題を達成する方法はいくつかあり、物事には単一の正しい方法や間違った方法があるわけではありません。いくつか異なる手法を試してみて、どれが一番うまくいくかを見てください。試行錯誤しながらメモを取りましょう。

## 例

次の画面ショットは、デザインのレイアウトの完成例です。

![ウェブサイトのレイアウト課題完了。要素がきれいにレイアウトされています。 5 つのリンクが等間隔に格納された黒いナビバーの上に、ウェブサイトのタイトルがあります。ナビバーの下記には 2 つの節があります。左側にはブログ記事があります。ブログ記事のタイトルの下に、記事のコンテンツが続きます。ブログのコンテンツは、左配置されたの写真を囲むように配置されています。正しい辺には「写真」のタイトルがあり、 2 枚幅のグリッドに並べられた画像群について書かれています。](layout-task-complete.png)

{{PreviousMenuNext("Learn_web_development/Core/CSS_layout/Media_queries", "Learn_web_development/Core/Scripting", "Learn_web_development/Core/CSS_layout")}}
