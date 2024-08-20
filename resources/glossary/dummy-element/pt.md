---
termo: ELEMENTO FICTÍCIO
---

Refere-se a um elemento adicional e desnecessário consumido pelos opcodes `OP_CHECKMULTISIG` e `OP_CHECKMULTISIGVERIFY` durante a verificação de assinaturas em uma transação. Devido a um bug histórico de deslocamento de unidade (erro de off-by-one), esses 2 opcodes removem um elemento extra da pilha além de sua função básica. Para evitar um erro, é, portanto, obrigatório incluir um valor fictício no início do `scriptSig` para satisfazer a remoção e contornar o bug. Este valor desnecessário é o que é chamado de "*elemento fictício*". O BIP11, que introduziu o padrão P2MS, aconselhou o uso de um `OP_0` como o valor fictício. No entanto, este padrão não foi imposto no nível de regra de consenso, significando que qualquer valor poderia ser colocado lá sem invalidar a transação. Assim, o elemento fictício foi um vetor para a maleabilidade de transações. O BIP147, introduzido com o soft fork SegWit, determinou que este elemento fictício seja estritamente um array de bytes vazio (`OP_0`), eliminando assim a maleabilidade associada a este elemento ao tornar qualquer transação não conforme inválida de acordo com as regras de consenso. Esta regra, denominada `NULLDUMMY`, aplica-se tanto a transações SegWit quanto a transações pré-SegWit.