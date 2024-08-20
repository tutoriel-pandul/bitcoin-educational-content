---
term: BIP147
---

Предложение, включенное в мягкое разветвление SegWit, направленное на решение проблемы изменчивости, связанной с фиктивным элементом, используемым операциями `OP_CHECKMULTISIG` и `OP_CHECKMULTISIGVERIFY`. Из-за исторической ошибки сдвига на единицу (ошибка сдвига единицы измерения), эти 2 операции удаляют дополнительный элемент из стека помимо их основной функции. Чтобы избежать ошибки, поэтому обязательно включать фиктивное значение в начало `scriptSig` для удовлетворения удаления и обхода ошибки. Это значение не нужно, но оно должно быть там, чтобы скрипт был действительным. BIP11, который ввел стандарт P2MS, рекомендовал помещать `OP_0` в качестве ненужного значения. Однако этот стандарт не был обязательным на уровне правил консенсуса, что означает, что любое значение могло быть помещено там без аннулирования транзакции. Таким образом, `OP_CHECKMULTISIG` и `OP_CHECKMULTISIGVERIFY` содержали вектор изменчивости. BIP147 вводит новое правило консенсуса, названное `NULLDUMMY`, требующее, чтобы этот фиктивный элемент был пустым байтовым массивом (`OP_0`). Любое другое значение приводит к немедленному сбою оценки скрипта. Это изменение применяется как к скриптам до SegWit, так и к скриптам P2WSH и требовало мягкого форка.