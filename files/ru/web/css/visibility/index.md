---
title: visibility
slug: Web/CSS/visibility
---

{{CSSRef}}

Свойство **`visibility`** скрывает или показывает элемент без изменения разметки документа. Также скрывает строки и столбцы {{HTMLElement("table")}}.

{{InteractiveExample("CSS Demo: visibility")}}

```css interactive-example-choice
visibility: visible;
```

```css interactive-example-choice
visibility: hidden;
```

```css interactive-example-choice
visibility: collapse;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="transition-all" id="example-element">Hide me</div>
    <div>Item 2</div>
    <div>Item 3</div>
  </div>
</section>
```

```css interactive-example
.example-container {
  border: 1px solid #c5c5c5;
  padding: 0.75em;
  width: 80%;
  max-height: 300px;
  display: flex;
}

.example-container > div {
  background-color: rgba(0, 0, 255, 0.2);
  border: 3px solid blue;
  margin: 10px;
  flex: 1;
}

#example-element {
  background-color: rgba(255, 0, 200, 0.2);
  border: 3px solid rebeccapurple;
}
```

Чтобы скрыть и удалить элемент из разметки, установите свойству {{cssxref("display")}} значение `none`, вместо использования `visibility`.

## Синтаксис

```css
/* Значения */
visibility: visible;
visibility: hidden;
visibility: collapse;

/* Глобальные значения */
visibility: inherit;
visibility: initial;
visibility: unset;
```

Свойство `visibility` указывается в качестве одного из значений ниже.

### Значения

- `visible`
  - : Значение по умолчанию, элемент виден.
- `hidden`
  - : Элемент не виден (полностью прозрачный, ничего не отображается), но продолжает влиять на шаблон. Потомки элемента могут быть показаны с помощью свойства `visibility:visible`. Элемент не может получить focus (например, при навигации с помощью [tabindex](/ru/docs/Web/HTML/Reference/Global_attributes/tabindex)).
- `collapse`
  - : \* Для строк, столбцов, групп столбцов и групп строк в таблице, которые должны быть удалены (как с помощью `{{Cssxref("display")}}: none` применённого к столбцу/строке таблицы). Однако, размер других строк и столбцов должен продолжать вычисляться так, словно скрытые строки/столбцы присутствуют. Это создано для быстрого удаления строк/столбцов из таблицы без дополнительного вычисления ширины и высоты частей таблицы.
    - Для XUL элементов размер всегда равен 0, независимо от других стилей, влияющих на размер, хотя отступы продолжают учитываться.
    - Для других элементов `collapse` обрабатывается также, как `hidden`

## Формальное определение

{{cssinfo}}

## Формальный синтаксис

{{csssyntax}}

## Интерполяция

Значения видимости изменяются между _видим_ и _не видим_. Интерполяция будет, если одно из начальных или конечных значений будет видимо или нет. Если одно из значений `visible`, интерполируется как дискретный шаг, где значения временной функции от `0` до `1` для `visible` и другие значения временной функции (которые происходят только в начале/конце перехода, или как результат функции `cubic-bezier()` со значениями вне \[0, 1]) ближе к конечной точке.

## Примеры

### Базовый пример

#### HTML

```html
<p class="visible">Первый параграф виден.</p>
<p class="not-visible">Второй параграф не виден.</p>
<p class="visible">
  Третий параграф также виден. Заметь, второй параграф занимает место.
</p>
```

#### CSS

```css
.visible {
  visibility: visible;
}

.not-visible {
  visibility: hidden;
}
```

{{EmbedLiveSample('Базовый_пример')}}

### Пример с таблицей

#### HTML

```html
<table>
  <tr>
    <td>1.1</td>
    <td class="collapse">1.2</td>
    <td>1.3</td>
  </tr>
  <tr class="collapse">
    <td>2.1</td>
    <td>2.2</td>
    <td>2.3</td>
  </tr>
  <tr>
    <td>3.1</td>
    <td>3.2</td>
    <td>3.3</td>
  </tr>
</table>
```

#### CSS

```css
.collapse {
  visibility: collapse;
}

table {
  border: 1px solid red;
}

td {
  border: 1px solid gray;
}
```

{{EmbedLiveSample('Пример_с_таблицей')}}

## Соображения доступности

Использование `visibility` со значением `hidden` на элементе удалит его из [дерева доступности](/ru/docs/Learn/%D0%94%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C/What_is_accessibility#%D0%A1%D0%BF%D0%B5%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5_API_%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%B0). Это приведёт к тому, что элемент и все его дочерние элементы больше не будут показаны в скринридерах.

## Примечания

- Поддержка `visibility:collapse` отсутствует или частично не работает в некоторых современных браузерах. Во многих случаях может не корректно работать `visibility:hidden` со столбцами и строками.
- `visibility:collapse` может изменить шаблон таблицы, если таблица содержит вложенные таблицы, пока `visibility:visible` не указан явно для вложенной таблицы.

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}
