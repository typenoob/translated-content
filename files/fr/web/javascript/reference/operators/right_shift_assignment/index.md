---
title: Affectation après décalage à droite (>>=)
slug: Web/JavaScript/Reference/Operators/Right_shift_assignment
---

{{jsSidebar("Operators")}}

L'opérateur de décalage à droite et d'affectation (`>>=`) décale la séquence de bits indiquée par l'opérande gauche d'autant de bits qu'indiqués par l'opérande droit puis affecte le résultat obtenu à la variable représentée par l'opérande gauche.

{{InteractiveExample("JavaScript Demo: Expressions - Right shift assignment operator")}}

```js interactive-example
let a = 5; //  00000000000000000000000000000101

a >>= 2; //  00000000000000000000000000000001
console.log(a);
// Expected output: 1

let b = -5; //  11111111111111111111111111111011

b >>= 2; //  11111111111111111111111111111110
console.log(b);
// Expected output: -2
```

## Syntaxe

```js
Opérateur: x >>= y;
Signification: x = x >> y;
```

## Exemples

### Utiliser l'opérateur de décalage à droite et d'affectation

```js
let a = 5; //   (00000000000000000000000000000101)
a >>= 2; // 1 (00000000000000000000000000000001)

let b = -5; //  (-00000000000000000000000000000101)
b >>= 2; // -2 (-00000000000000000000000000000010)
```

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- [Les opérateurs d'affectation dans le guide JavaScript](/fr/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment)
- [L'opérateur de décalage à droite](/fr/docs/Web/JavaScript/Reference/Operators/Right_shift)
