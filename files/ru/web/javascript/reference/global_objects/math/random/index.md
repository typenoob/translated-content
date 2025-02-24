---
title: Math.random()
slug: Web/JavaScript/Reference/Global_Objects/Math/random
l10n:
  sourceCommit: 27180875516cc311342e74b596bfb589b7211e0c
---

{{JSRef}}

Статический метод **`Math.random()`** возвращает псевдослучайное число с плавающей запятой, которое больше или равно нулю и меньше единицы с приблизительно равномерным распределением в этом диапазоне. В дальнейшем это число можно «отмасштабировать», привести к нужному диапазону. Выбор начального числа для алгоритма генерации случайных чисел происходит автоматически (зависит от реализации) и не может быть изменён пользователем.

> [!NOTE]
> Метод `Math.random()` _не предоставляет_ криптографически стойкие случайные числа. Не используйте его ни для чего, связанного с безопасностью. Для таких целей используйте Web Crypto API и более точный метод {{domxref("Crypto/getRandomValues", "window.crypto.getRandomValues()")}}.

{{InteractiveExample("JavaScript Demo: Math.random()")}}

```js interactive-example
function getRandomInt(max) {
  return Math.floor(Math.random() * max);
}

console.log(getRandomInt(3));
// Expected output: 0, 1 or 2

console.log(getRandomInt(1));
// Expected output: 0

console.log(Math.random());
// Expected output: a number from 0 to <1
```

## Синтаксис

```js-nolint
Math.random()
```

### Параметры

Нет.

### Возвращаемое значение

Псевдослучайное число с плавающей запятой от 0 (включительно) до 1 (не включая).

## Примеры

Обратите внимание, что поскольку числа в JavaScript являются числами с плавающей запятой стандарта IEEE 754 с округлением к ближайшему чётному, используемые в приведённых функциях диапазоны (исключая диапазон с простым вызовом `Math.random()`), не точны. Если заданы очень большие границы (2<sup>53</sup> или выше), возможен _крайне_ редкий случай достижения обычно исключённой верхней границы.

### Получение случайного числа от 0 (включительно) до 1 (не включая)

```js
function getRandom() {
  return Math.random();
}
```

### Получение случайного числа в заданном интервале

Этот пример возвращает случайное число в заданном интервале. Возвращаемое значение не менее (и может быть равно) `min` и не более (и не равно) `max`.

```js
function getRandomArbitrary(min, max) {
  return Math.random() * (max - min) + min;
}
```

### Получение случайного целого числа в заданном интервале

Этот пример возвращает случайное _целое_ число в заданном интервале. Возвращаемое значение не менее `min` (или следующее целое число, которое больше `min`, если `min` не целое) и не более (но не равно) `max`.

```js
function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min) + min); // Максимум не включается, минимум включается
}
```

> [!NOTE]
> Может показаться заманчивым использовать [`Math.round()`](/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/round) для округления, но это может сделать распределение неравномерным и оказаться не тем, что вам нужно.

### Получение случайного целого числа в заданном интервале, включительно

Функция `getRandomInt()` выше включает минимальное значение, но не включает максимальное. Но что если вам нужно, чтобы включалось и минимальное, и максимальное значение? Функция `getRandomIntInclusive()` решает этот вопрос.

```js
function getRandomIntInclusive(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1) + min); // Максимум и минимум включаются
}
```

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- {{domxref("Crypto/getRandomValues", "window.crypto.getRandomValues()")}}
