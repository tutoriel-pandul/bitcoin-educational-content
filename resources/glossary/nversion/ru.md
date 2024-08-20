---
term: NVERSION
---

Поле `nVersion` в транзакции Bitcoin используется для указания версии используемого формата транзакции. Оно позволяет сети различать разные эволюции формата транзакции со временем и применять соответствующие правила. Это поле не оказывает влияния на правила консенсуса. Это означает, что любое значение, присвоенное этому полю, не приводит к аннулированию транзакции. Однако, поле `nVersion` имеет правила стандартизации, которые в настоящее время принимают только значения `1` и `2`. На данный момент это поле полезно только для активации поля `nSequence`.