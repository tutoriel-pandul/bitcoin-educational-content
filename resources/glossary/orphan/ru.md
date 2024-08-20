---
term: ORPHAN
---

Теоретически, под "сиротским блоком" понимается валидный блок, полученный узлом, который еще не получил предыдущий блок в цепочке, то есть родительский блок. Несмотря на свою валидность, этот блок остается изолированным локально как сирота.

Однако в общем употреблении термин "сиротский блок" часто относится к блоку без потомка: валидный блок, но не сохраненный в основной цепочке Bitcoin. Это происходит, когда два майнера находят валидный блок на одной и той же высоте цепочки в короткий период времени и транслируют его по сети. Узлы в конечном итоге выбирают только один блок для включения в цепочку, основываясь на принципе цепочки с наибольшим накопленным объемом работы, делая другой "сиротой".

![](../../dictionnaire/assets/9.png)

> ► *Лично я предпочитаю использовать термин "сиротский блок" для обозначения блока без родителя и термин "устаревший блок" для обозначения блока, не имеющего потомка. Я нахожу это более логичным и понятным, хотя большинство биткоинеров не придерживаются этого использования.*