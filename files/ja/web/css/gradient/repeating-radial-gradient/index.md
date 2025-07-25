---
title: repeating-radial-gradient()
slug: Web/CSS/gradient/repeating-radial-gradient
l10n:
  sourceCommit: 14515827c44f3cb814261a1c6bd487ae8bfcde1b
---

**`repeating-radial-gradient()`** は [CSS](/ja/docs/Web/CSS) の[関数](/ja/docs/Web/CSS/CSS_Values_and_Units/CSS_Value_Functions)で、原点から広がり反復するグラデーションから成る画像を生成します。 {{cssxref("gradient/radial-gradient", "radial-gradient()")}} と似ており、同じ引数を取りますが、 {{cssxref("gradient/repeating-linear-gradient", "repeating-linear-gradient()")}} と同様にすべての方向に色経由点を無限に繰り返してコンテナー全体を埋めます。関数の返値は {{cssxref("&lt;gradient&gt;")}} データ型のオブジェクトであり、これは {{cssxref("&lt;image&gt;")}} の特殊型です。

{{InteractiveExample("CSS デモ: repeating-radial-gradient()")}}

```css interactive-example-choice
background: repeating-radial-gradient(#e66465, #9198e5 20%);
```

```css interactive-example-choice
background: repeating-radial-gradient(closest-side, #3f87a6, #ebf8e1, #f69d3c);
```

```css interactive-example-choice
background: repeating-radial-gradient(
  circle at 100%,
  #333,
  #333 10px,
  #eee 10px,
  #eee 20px
);
```

```html interactive-example
<section class="display-block" id="default-example">
  <div id="example-element"></div>
</section>
```

```css interactive-example
#example-element {
  min-height: 100%;
}
```

それぞれの繰り返しにおいて、色経由点の位置は基本的な放射グラデーションの寸法 (最初と最後の色経由点の間の距離) の倍数だけずらしたものになります。この結果、グラデーションの最初と最後の色は常に隣り合わせになります。 2 つが異なる色であれば、視覚的に明確な変わり目ができるので、最初の色を最後の色として繰り返すことで緩和できます。

他のグラデーションと同じく、反復放射グラデーションも[内在的な寸法を持ちません](/ja/docs/Web/CSS/image#解説)。つまり、本来の寸法も優先される寸法も、優先されるアスペクト比も持たないということです。実際の寸法は、適用先の要素の寸法と一致します。

`<gradient>` は `<image>` データ型に属するため、 `<image>` が使用できるところでしか使用できません。このため、 `repeating-radial-gradient()` は {{cssxref("background-color")}} や、その他の {{cssxref("&lt;color&gt;")}} データ型を使用するプロパティでは動作しません。

## 構文

```css
/* コンテナーの中央からのグラデーションで、
   赤で始まり、青に変化し、緑で終わり、
   それぞれ 30px ごとに色が繰り返される */
repeating-radial-gradient(circle at center, red 0, blue, green 30px)

/* 左上の角付近の楕円形のグラデーションで、
   赤で始まり、緑に変化し、また戻り、
   中央と右下の角の間で5回繰り返され、
   中央と左上の角の間は1回だけ */
repeating-radial-gradient(farthest-corner at 20% 20%, red 0, green, red 20%)
```

### 値

- {{cssxref("&lt;position&gt;")}}
  - : グラデーションの位置で、 {{cssxref("background-position")}} や {{cssxref("transform-origin")}} と同じ方法で解釈されます。指定されなかった場合、既定値は `center` です。
- `<shape>`
  - : グラデーションの形状です。 `circle` (グラデーションの形状が一定の半径の円の意味) か `ellipse` (軸に沿った楕円の意味) のいずれかです。指定されなかった場合、既定値は `ellipse` です。
- `<extent-keyword>`
  - : 終端の形状の大きさを指定するキーワードです。利用可能な値は次の通りです。

    | キーワード        | 説明                                                                                                                                              |
    | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
    | `closest-side`    | グラデーションの終端の形状は、中心から最も近いボックスの辺に (circle の場合) または中心から最も近い縦の辺と横の辺に (ellipse の場合) 内接します。 |
    | `closest-corner`  | グラデーションの終端の形状は、ボックスの中心から最も近い頂点に接するように大きさが調整されます。                                                  |
    | `farthest-side`   | `closest-side` と同様ですが、終端の形状がその中心から最も遠い辺 (または縦と横の辺) に接するように大きさが調整される点が異なります。               |
    | `farthest-corner` | グラデーションの終端の形状は、ボックスの中心から最も遠い頂点に接するように大きさが調整されます。                                                  |

    > [!NOTE]
    > この関数の初期の実装では、他のキーワード (`cover` および `contain`) をそれぞれ標準の `farthest-corner` および `closest-side` の別名として含めていました。実装によってはすでに古い形を外しているので、標準的なキーワードのみを使用してください。

- `<color-stop>`
  - : 色経由点の {{cssxref("&lt;color&gt;")}} 値と、それに続く省略可能な経由位置 (グラデーション軸沿いの {{cssxref("&lt;percentage&gt;")}} または {{cssxref("&lt;length&gt;")}}) です。 percentage が `0%`、または length が `0` の場合は、グラデーションの中心を表します。 `100%` は終端の形状と仮想グラデーション光の交点を表します。その間のパーセント値は仮想グラデーション光における直線的な位置です。

### 形式文法

{{csssyntax}}

## 例

### 白と黒のグラデーション

```html hidden
<div class="radial-gradient"></div>
```

```css hidden
.radial-gradient {
  width: 120px;
  height: 120px;
}
```

```css
.radial-gradient {
  background: repeating-radial-gradient(
    black,
    black 5px,
    white 5px,
    white 10px
  );
}
```

{{EmbedLiveSample('Black_and_white_gradient', 120, 120)}}

### 最も遠い角

```html hidden
<div class="radial-gradient"></div>
```

```css hidden
.radial-gradient {
  width: 240px;
  height: 120px;
}
```

```css
.radial-gradient {
  background: repeating-radial-gradient(
    ellipse farthest-corner at 20% 20%,
    red,
    black 5%,
    blue 5%,
    green 10%
  );
  background: repeating-radial-gradient(
    ellipse farthest-corner at 20% 20%,
    red 0 5%,
    green 5% 10%
  );
}
```

{{EmbedLiveSample('Farthest-corner', 120, 120)}}

楕円のグラデーションは左上から 20% の位置が中心となり、中心と最も遠い角 (右下の角) の間で 10 回繰り返します。色経由点で複数の位置に対応しているブラウザーでは、赤と緑の縞模様の楕円が表示されます。この構文にまだ対応していないブラウザーでは、赤から黒、それから青から緑へと変化するグラデーションが表示されます。

### 色相での補間

```html hidden live-sample___interpolating_with_hue
<div class="shorter"></div>
<div class="longer"></div>
```

```css hidden live-sample___interpolating_with_hue
div {
  display: inline-block;
  margin-top: 1rem;
  width: 45vw;
  height: 80vh;
}

.shorter::before {
  content: "shorter hue";
  display: block;
  margin-top: -1rem;
}

.longer::before {
  content: "longer hue";
  display: block;
  margin-top: -1rem;
}
```

この補間処理の例では、 [hsl](/ja/docs/Web/CSS/color_value/hsl) 色系を使用して、[色相](/ja/docs/Web/CSS/hue)を補間しています。

```css live-sample___interpolating_with_hue
.shorter {
  background-image: repeating-radial-gradient(
    circle at center in hsl shorter hue,
    red 30px,
    blue 60px
  );
}

.longer {
  background-image: repeating-radial-gradient(
    circle at center in hsl longer hue,
    red 30px,
    blue 60px
  );
}
```

左のボックスは、 [shorter の補間](/ja/docs/Web/CSS/hue-interpolation-method#shorter)を使用しており、[色相環](/ja/docs/Glossary/Color_wheel)の短い方の弧を使用して、色が赤から青に直接変化しているということになります。右のボックスは、 [longer の補間](/ja/docs/Web/CSS/hue-interpolation-method#longer)を使用しており、色が赤から青に変化する際に、緑、黄、オレンジを通って変化しているということになります。

{{EmbedLiveSample("Interpolating with hue", 240, 200)}}

> [!NOTE]
> 他の例は [CSS グラデーションの使用](/ja/docs/Web/CSS/CSS_images/Using_CSS_gradients)をご覧ください。

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- [CSS グラデーションの使用](/ja/docs/Web/CSS/CSS_images/Using_CSS_gradients)
- 他のグラデーション関数: {{cssxref("gradient/radial-gradient", "radial-gradient()")}}, {{cssxref("gradient/linear-gradient", "linear-gradient()")}}, {{cssxref("gradient/repeating-linear-gradient", "repeating-linear-gradient()")}}, {{cssxref("gradient/conic-gradient", "conic-gradient()")}}, {{cssxref("gradient/repeating-conic-gradient", "repeating-conic-gradient()")}}
- [`<hue-interpolation-method>`](/ja/docs/Web/CSS/hue-interpolation-method)
- [`<color-interpolation-method>`](/ja/docs/Web/CSS/color-interpolation-method)
- {{cssxref("&lt;image&gt;")}}
- {{cssxref("image/image","image()")}}
- {{cssxref("element", "element()")}}
- {{cssxref("image/image-set","image-set()")}}
- {{cssxref("cross-fade", "cross-fade()")}}
