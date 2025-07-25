---
title: "<br>: 改行要素"
slug: Web/HTML/Reference/Elements/br
l10n:
  sourceCommit: e9b6cd1b7fa8612257b72b2a85a96dd7d45c0200
---

{{HTMLSidebar}}

**`<br>`** は [HTML](/ja/docs/Web/HTML) の要素で、文中に改行（キャリッジリターン）を生成します。詩や住所など、行の分割が重要な場合に有用です。

{{InteractiveExample("HTML デモ: &lt;br&gt;", "tabbed-standard")}}

```html interactive-example
<p>
  O’er all the hilltops<br />
  Is quiet now,<br />
  In all the treetops<br />
  Hearest thou<br />
  Hardly a breath;<br />
  The birds are asleep in the trees:<br />
  Wait, soon like these<br />
  Thou too shalt rest.
</p>
```

```css interactive-example
p {
  font-size: 1rem;
  font-family: sans-serif;
  margin: 20px;
}
```

上記の例に見られるように、 `<br>` 要素はテキストを改行したい場所にそれぞれ含められます。 `<br>` の後のテキストは、テキストブロックの次の行の先頭から再開されます。

> [!NOTE]
> 段落の間を開けるために `<br>` を使わないでください。それぞれを {{htmlelement("p")}} 要素で囲み、 [CSS](/ja/docs/Web/CSS) の {{cssxref('margin')}} プロパティで間隔を制御してください。

## 属性

この要素には[グローバル属性](/ja/docs/Web/HTML/Reference/Global_attributes)があります。

### 非推奨の属性

- `clear` {{Deprecated_Inline}}
  - : 改行後の次の行を開始する場所を示します。

## CSS でのスタイル付け

`<br>` 要素は、テキストのブロック内で改行するという、単一の明確な目的を持っています。そのため、寸法を持たず、自身が表示されることもなく、スタイル付けすることができるのはわずかです。

{{cssxref("margin")}} を `<br>` 要素自体に設定して、ブロック内のテキストの行間を開けることができますが、これは良いやり方ではありません。 — この用途のために設計された {{cssxref("line-height")}} プロパティを使用してください。

## アクセシビリティ

段落間の間隔を広げるために連続した `<br>` 要素を使用することは、読み上げ技術の支援の下で操作をしている人にとっては問題になります。読み上げソフトは要素が存在することをアナウンスするものの、その中にはコンテンツが何もないという状況になる可能性があります。これは読み上げソフトを使用している人の利用を混乱させ不満をためる可能性があります。

追加の間隔をあける必要がある場合は、 {{cssxref("margin")}} のような CSS プロパティを使用して効果を得るようにしてください。

## 例

### 基本的な br

以下の例では `<br>` を使用して、住所のそれぞれの行の間に改行を生成しています。

```html
Mozilla<br />
331 E. Evelyn Avenue<br />
Mountain View, CA<br />
94041<br />
USA<br />
```

以下のように出力されます。

{{ EmbedLiveSample('Basic_br', 640, 120) }}

## 技術的概要

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/HTML/Guides/Content_categories">コンテンツカテゴリー</a>
      </th>
      <td>
        <a href="/ja/docs/Web/HTML/Guides/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >、
        <a href="/ja/docs/Web/HTML/Guides/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>なし。これは{{Glossary("void element", "空要素")}}です。</td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>
        開始タグは必須で、終了タグを記述してはなりません。 XHTML
        文書では、この要素は <code>&#x3C;br /></code> と書きます。
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        <a href="/ja/docs/Web/HTML/Guides/Content_categories#記述コンテンツ"
          >記述コンテンツ</a
        >を受け入れるすべての要素。
      </td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role"
          >対応するロールなし</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>
        <a href="/ja/docs/Web/Accessibility/ARIA/Reference/Roles/none_role"><code>none</code></a>, <a href="/ja/docs/Web/Accessibility/ARIA/Reference/Roles/presentation_role"><code>presentation</code></a>
      </td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLBRElement")}}</td>
    </tr>
  </tbody>
</table>

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- {{HTMLElement("address")}} 要素
- {{HTMLElement("p")}} 要素
- {{HTMLElement("wbr")}} 要素
