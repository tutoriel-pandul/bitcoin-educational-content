---
term: INITIAL BLOCK DOWNLOAD (IBD)
---

Si riferisce al processo mediante il quale un nodo scarica e verifica la blockchain a partire dal blocco Genesis e si sincronizza con altri nodi nella rete Bitcoin. L'IBD deve essere eseguito quando si avvia un nuovo nodo completo. All'inizio di questa sincronizzazione iniziale, il nodo non ha informazioni sulle transazioni precedenti. Pertanto, scarica ogni blocco dagli altri nodi nella rete, ne verifica la validità e poi lo aggiunge alla sua versione locale della blockchain. È importante notare che l'IBD può essere lungo e richiedere molte risorse a causa della crescente dimensione della blockchain e del set di UTXO. La velocità della sua esecuzione dipende dalle capacità di calcolo del computer che ospita il nodo, dalla capacità della RAM, dalla velocità del dispositivo di archiviazione e dalla larghezza di banda. Per darvi un'idea, se avete una potente connessione internet e il nodo è ospitato sull'ultimo MacBook con abbondante RAM, l'IBD richiederà solo poche ore. Al contrario, se utilizzate un microcomputer come un Raspberry Pi, l'IBD potrebbe richiedere una settimana o più.

> ► *In francese, è generalmente accettato riferirsi direttamente a un IBD. La traduzione talvolta utilizzata è "synchronisation initiale" o "téléchargement initial des blocs".*