---
title: Element.ariaColIndexText
slug: Web/API/Element/ariaColIndexText
l10n:
  sourceCommit: 388135bbfb0c1f852a17f52a6bfe6e85c8dc1abc
---

{{APIRef("DOM")}}{{SeeCompatTable}}

**`ariaColIndexText`** は {{domxref("Element")}} インターフェイスのプロパティで、[`aria-colindextext`](/ja/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-colindextext) 属性の値を反映し、aria-colindex の人間が読むための代替テキストを定義します。

## 値

文字列です。

## 例

この例では、ID が `role-heading` の要素の `aria-colindex` 属性に "Aria Role column" が設定されています。`ariaColIndexText` を使用して、値を文字列 "New column name" に更新します。

```html
<table
  id="semantic-table"
  role="table"
  aria-label="Semantic Elements"
  aria-describedby="semantic_elements_table_desc"
  aria-rowcount="100">
  <caption id="semantic_elements_table_desc">
    Semantic Elements to use instead of ARIA's roles
  </caption>
  <thead role="rowgroup">
    <tr role="row">
      <th
        role="columnheader"
        id="role-heading"
        aria-sort="none"
        aria-rowindex="1"
        aria-colindex="1"
        aria-colindextext="Aria Role column">
        ARIA Role
      </th>
      <th
        role="columnheader"
        id="element-heading"
        aria-sort="none"
        aria-rowindex="1">
        Semantic Element
      </th>
    </tr>
  </thead>
  <tbody role="rowgroup">
    <tr role="row">
      <td role="cell" aria-rowindex="11">header</td>
      <td role="cell" aria-rowindex="11">h1</td>
    </tr>
    <tr role="row">
      <td role="cell" aria-rowindex="16">header</td>
      <td role="cell" aria-rowindex="16">h6</td>
    </tr>
    <tr role="row">
      <td role="cell" aria-rowindex="18">rowgroup</td>
      <td role="cell" aria-rowindex="18">thead</td>
    </tr>
    <tr role="row">
      <td role="cell" aria-rowindex="24">term</td>
      <td role="cell" aria-rowindex="24">dt</td>
    </tr>
  </tbody>
</table>
```

```js
let el = document.getElementById("role-heading");
console.log(el.ariaColIndexText); // "Aria Role"
el.ariaColIndexText = "New column name";
console.log(el.ariaColIndexText); // "New column name"
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- [ARIA: table role](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/table_role)
