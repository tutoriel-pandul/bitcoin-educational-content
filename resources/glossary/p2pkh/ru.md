---
term: P2PKH
---

P2PKH означает *Pay to Public Key Hash* (Оплата на Хеш Публичного Ключа). Это стандартная модель скрипта, используемая для установления условий расходования UTXO. Она позволяет блокировать биткойны на хеше публичного ключа, то есть на адресе получателя. Этот скрипт ассоциируется со стандартом Legacy и был введен в ранних версиях Биткойна Сатоши Накамото.

В отличие от P2PK, где публичный ключ явно включен в скрипт, P2PKH использует криптографический отпечаток публичного ключа. Этот скрипт включает в себя хеш `RIPEMD160` от `SHA256` публичного ключа и предписывает, что для доступа к средствам получатель должен предоставить публичный ключ, который соответствует этому хешу, а также действительную цифровую подпись, сгенерированную из соответствующего приватного ключа. Адреса P2PKH кодируются с использованием формата `Base58Check`, который обеспечивает их устойчивость к опечаткам за счет использования контрольной суммы. Эти адреса всегда начинаются с цифры `1`.