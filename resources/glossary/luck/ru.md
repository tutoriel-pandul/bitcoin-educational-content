---
term: УДАЧА
---

Индикатор, используемый в майнинг-пулах для измерения производительности пула по отношению к его теоретическим ожиданиям. Как следует из названия, он оценивает удачу пула в нахождении блока. Удача рассчитывается путем сравнения количества акций (shares), теоретически необходимых для нахождения действительного блока, исходя из текущей сложности Bitcoin, с фактическим количеством акций, произведенных для нахождения этого блока. Количество акций меньше ожидаемого указывает на хорошую удачу, в то время как большее количество указывает на плохую удачу.

Сопоставляя сложность на Bitcoin с его количеством акций, производимых каждую секунду, и сложностью каждой акции, пул может рассчитать количество акций, теоретически необходимых для нахождения действительного блока. Например, предположим, что теоретически для нахождения блока пулу необходимо 100 000 акций. Если пул фактически производит 200 000 акций перед нахождением блока, его удача составляет 50%:

```text
100,000 / 200,000 = 0.5 = 50%
```

Наоборот, если этот пул находит действительный блок после производства всего 50 000 акций, то его удача составляет 200%:

```text
100,000 / 50,000 = 2 = 200%
```

Удача - это индикатор, который может быть обновлен только после обнаружения блока пулом, делая его статическим индикатором, который обновляется периодически.