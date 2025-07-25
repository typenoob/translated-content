---
title: path()
slug: Web/CSS/basic-shape/path
original_slug: Web/CSS/path
---

**`path()`** は [CSS](/ja/docs/Web/CSS) の[関数](/ja/docs/Web/CSS/CSS_Values_and_Units/CSS_Value_Functions)で、 SVG のパス文字列を受け取り、 [CSS シェイプ](/ja/docs/Web/CSS/CSS_shapes)や CSS モーションパスで描画される形状を有効にするために使用します。

{{InteractiveExample("CSS デモ: path()")}}

```css interactive-example-choice
clip-path: path(
  "M  20  240 \
 L  20  80 L 160  80 \
 L 160  20 L 280 100 \
 L 160 180 L 160 120 \
 L  60 120 L  60 240 Z"
);
```

```css interactive-example-choice
clip-path: path(
  "M 20 240 \
 C 20 0 300 0 300 240 Z"
);
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element"></div>
</section>
```

```css interactive-example
#default-example {
  background: #fe9;
}

#example-element {
  background: linear-gradient(to bottom right, #f52, #05f);
  width: 100%;
  height: 100%;
}
```

## 構文

{{cssxref("offset-path")}} や {{SVGAttr("d")}} で使用する場合:

```css
path(<string>)
```

{{cssxref("clip-path")}} で使用する場合:

```css
path([<'fill-rule'>,]?<string>)
```

### 引数

- `<'fill-rule'>`
  - : パス内の塗りつぶしルールです。
    指定可能な値は `nonzero` または `evenodd` です。
    既定値は `nonzero` です。
    詳細は[塗りつぶしルール](/ja/docs/Web/SVG/Reference/Attribute/fill-rule)を参照してください。
- `<string>`
  - : 文字列で、[SVG パス](/ja/docs/Web/SVG/Reference/Element/path)を定義する[データ文字列](/ja/docs/Web/SVG/Reference/Attribute/d)です。

## 例

### path() の正しい値の例

```css
path("M 10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80");
path(evenodd,"M 10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80");
```

### offset-path の値として使用

`path()` 関数が、アイテムが一周するためのパスを作成するために使用されています。いずれかの値を変更すると、パスがきれいに円を描かなくなります。

{{EmbedGHLiveSample("css-examples/path/offset-path.html", '100%', 960)}}

### SVG パスで d 属性の値を変更する

`path()` は SVG の [`d` 属性](/ja/docs/Web/SVG/Reference/Attribute/d) の値を変更するために使用することができます。 CSS で `none` に設定することも可能です。

"V" マークは、 CSS のプロパティとして `d` が対応していれば、カーソルを置いたときに縦に反転します。

#### CSS

```css
html,
body,
svg {
  height: 100%;
}

/* This path is displayed on hover*/
#svg_css_ex1:hover path {
  d: path("M20,80 L50,20 L80,80");
}
```

#### HTML

```html
<svg id="svg_css_ex1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <path fill="none" stroke="red" d="M20,20 L50,80 L80,20" />
</svg>
```

#### 結果

{{EmbedLiveSample('Modify the value of the SVG path d attribute', '100%', 200)}}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- {{cssxref("&lt;shape-outside&gt;")}}
- [CSS シェイプ](/ja/docs/Web/CSS/CSS_shapes)
- [CSS シェイプの概要](/ja/docs/Web/CSS/CSS_shapes/Overview_of_shapes)
- [SVG Path Syntax Illustrated Guide](https://css-tricks.com/svg-path-syntax-illustrated-guide/)
