---
term: ТИХИЕ ПЛАТЕЖИ
---

Метод использования статических адресов Bitcoin для приема платежей без повторного использования адреса, без взаимодействия и без видимой связи в блокчейне между различными платежами и статическим адресом. Эта техника устраняет необходимость генерировать новые, неиспользованные адреса получения для каждой транзакции, тем самым избегая обычного взаимодействия в Bitcoin, где получатель должен предоставить новый адрес плательщику.

С Тихими Платежами плательщик использует публичные ключи получателя (ключ публичного расхода и ключ публичного сканирования) и сумму своих собственных приватных ключей в качестве входных данных для генерации свежего адреса для каждого платежа. Только получатель, имея свои приватные ключи, может вычислить приватный ключ, соответствующий этому платежному адресу. ECDH (*Эллиптическая кривая Диффи-Хеллмана*), алгоритм обмена криптографическими ключами, используется для установления общего секрета, который затем используется для получения адреса и приватного ключа (только на стороне получателя). Чтобы идентифицировать Тихие Платежи, предназначенные для них, получатели должны сканировать блокчейн и проверять каждую транзакцию, соответствующую критериям протокола. В отличие от BIP47, который использует транзакцию уведомления для установления платежного канала, Тихие Платежи устраняют этот шаг, экономя транзакцию. Однако компромисс заключается в том, что получателю необходимо сканировать все потенциальные транзакции, чтобы определить, адресованы ли они им, применяя ECDH.

Например, статический адрес Боба $B$ представляет собой конкатенацию его публичного ключа сканирования и его публичного ключа расхода:

$$ B = B_{\text{scan}} \text{ ‖ } B_{\text{spend}} $$

Эти ключи просто получаются из следующего пути:

```text
scan : m / 352' / 0' / 0' / 1' / 0
spend : m / 352' / 0' / 0' / 0' / 0
```

Этот статический адрес публикуется Бобом. Алиса извлекает его, чтобы совершить Тихий Платеж Бобу. Она вычисляет платежный адрес Боба $P_0$ следующим образом:

$$  P_0 = B_{\text{spend}} + \text{hash}(\text{inputHash} \cdot a \cdot B_{\text{scan}} \text{ ‖ } 0) \cdot G  $$

Где:

$$  \text{inputHash} = \text{hash}(\text{outpoint}_L \text{ ‖ } A)  $$

С:
* $B_{\text{scan}}$: публичный ключ сканирования Боба (статический адрес);
* $B_{\text{spend}}$: публичный ключ расхода Боба (статический адрес);
* $A$: Сумма публичных ключей на входе (модификация);
* $a$: Приватный ключ модификации, то есть сумма всех пар ключей, используемых в `scriptPubKey` UTXO, потребляемых в качестве входов в транзакции Алисы;
* $\text{outpoint}_L$: Самый маленький UTXO (лексикографически) используемый в качестве входа в транзакции Алисы;
* $\text{ ‖ }$: Конкатенация (операция соединения операндов конец к концу);
* $G$: Точка генератора эллиптической кривой `secp256k1`;
* $\text{hash}$: Функция хеширования SHA256 с тегом `BIP0352/SharedSecret`;
* $P_0$: Первый публичный ключ / уникальный адрес для платежа Бобу;
* $0$: Целое число, используемое для генерации множества уникальных платежных адресов.

Боб сканирует блокчейн, чтобы найти свой Тихий Платеж следующим образом:
$$  P_0 = B_{\text{spend}} + \text{hash}(\text{inputHash} \cdot b_{\text{scan}} \cdot A \text{ ‖ } 0) \cdot G  $$

С учетом:
* $b_{\text{scan}}$: приватный сканирующий ключ Боба.

Если он находит $P_0$ как адрес, содержащий Тихий Платеж, адресованный ему, он вычисляет $p_0$, приватный ключ, позволяющий ему тратить средства, отправленные Алисой на $P_0$:

$$ p_0 = (b_{\text{spend}} + \text{hash}(\text{inputHash} \cdot b_{\text{scan}} \cdot A \text{ ‖ } 0)) \mod n $$

С учетом:
* $b_{\text{spend}}$: приватный ключ расходов Боба;
* $n$: порядок эллиптической кривой `secp256k1`.

В дополнение к этой базовой версии, метки также могут быть использованы для генерации нескольких различных статических адресов из одного и того же базового статического адреса с целью разделения множественных использований без необоснованного увеличения работы, требуемой при сканировании.