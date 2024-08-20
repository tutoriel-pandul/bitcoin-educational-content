---
term: СЖАТЫЙ ПУБЛИЧНЫЙ КЛЮЧ
---

Публичный ключ используется в скриптах (напрямую в виде публичного ключа или как адрес) для получения и защиты биткойнов. Сырой публичный ключ представлен точкой на эллиптической кривой, состоящей из двух координат (`x, y`), каждая из которых имеет 256 бит. В сыром формате публичный ключ, таким образом, имеет размер 512 бит, не считая дополнительного байта для идентификации формата. С другой стороны, сжатый публичный ключ является более компактной формой представления публичного ключа. Он использует только координату `x` и префикс (`02` или `03`), который указывает четность координаты `y` (четная или нечетная).

Если упростить это до поля действительных чисел, учитывая, что эллиптическая кривая симметрична относительно оси x, для любой точки $P$ (`x, y`) на кривой, существует точка $P'$ (`x, -y`), которая также будет на этой же кривой. Это означает, что для каждой `x` существуют только два возможных значения `y`, положительное и отрицательное. Например, для данной абсциссы `x` на эллиптической кривой будут две точки $P1$ и $P2$, имеющие одинаковую абсциссу, но противоположные ординаты:

![](../../dictionnaire/assets/29.png)
Чтобы выбрать между двумя потенциальными точками на кривой, к `x` добавляется префикс, указывающий, какую `y` выбрать. Этот метод позволяет уменьшить размер публичного ключа с 520 бит до всего 264 бит (8 бит префикса + 256 бит для `x`). Это представление известно как сжатая форма публичного ключа.

Однако, в контексте криптографии на эллиптических кривых, мы используем не действительные числа, а конечное поле порядка `p` (простое число). В этом контексте "знак" `y` определяется его четностью, то есть, является ли `y` четным или нечетным. Префикс `0x02` тогда указывает на четное `y`, в то время как `0x03` указывает на нечетное `y`.

Рассмотрим следующий пример сырого публичного ключа (точка на эллиптической кривой) в шестнадцатеричном формате:
```plaintext
K = 04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f
6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f
```

Мы можем выделить префикс, `x` и `y`:
```plaintext
Префикс = 04
Чтобы определить четность `y`, мы рассматриваем последний шестнадцатеричный символ `y`:
```plaintext
База 16 (шестнадцатеричная): f
База 10 (десятичная): 15
y нечетное
```

Префикс для сжатого публичного ключа будет `03`. Сжатый публичный ключ в шестнадцатеричном формате становится:
```plaintext
K = 03678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb6
```