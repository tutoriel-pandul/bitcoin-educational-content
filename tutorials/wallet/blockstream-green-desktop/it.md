---
name: Blockstream Green - Desktop
description: Utilizzo del software Green Wallet su un computer
---

![cover](assets/cover.webp)

In questo tutorial, esploreremo come utilizzare il software Blockstream Green su un computer per gestire un portafoglio sicuro su un hardware wallet. Quando si utilizza un hardware wallet, è essenziale usare un software sul proprio computer per gestire questo portafoglio. Questo software di gestione non ha accesso alle chiavi private; viene utilizzato solo per controllare il saldo del tuo portafoglio, generare indirizzi per ricevere pagamenti e costruire e trasmettere transazioni che saranno firmate dall'hardware wallet. Green rappresenta una delle molte soluzioni disponibili per gestire il tuo Bitcoin hardware wallet.

Nel 2024, Blockstream Green è compatibile solo con Ledger Nano S (versione precedente), Ledger Nano X, Trezor One, Trezor T e i dispositivi Blockstream Jade.

## Introduzione a Blockstream Green

Blockstream Green è un software disponibile sia per dispositivi mobili che desktop. In precedenza noto come Green Address, questo portafoglio è diventato un progetto Blockstream a seguito della sua acquisizione nel 2016.

Green è un'applicazione molto user-friendly, rendendola particolarmente adatta ai principianti. Offre varie funzionalità, come la gestione di hot wallets, hardware wallets, così come portafogli sulla sidechain Liquid. Puoi anche usarlo per configurare un portafoglio in sola visualizzazione.

![GREEN-DESKTOP](assets/fr/01.webp)

In questo tutorial, ci concentreremo esclusivamente sull'uso del software su un computer. Per esplorare altri utilizzi di Green, ti invito a consultare i nostri altri tutorial dedicati:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Installazione e configurazione del software Blockstream Green

Inizia installando il software Blockstream Green sul tuo computer. Vai sul [sito ufficiale](https://blockstream.com/green/) e clicca sul pulsante "*Scarica Ora*". Segui poi il processo di installazione in base al tuo sistema operativo.

![GREEN-DESKTOP](assets/fr/02.webp)

Avvia l'applicazione, poi spunta la casella "*Accetto i termini...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Quando apri Green per la prima volta, appare la schermata iniziale senza nessun portafoglio configurato. In seguito, se crei o importi portafogli, appariranno in questa interfaccia. Prima di passare alla creazione di un portafoglio, ti consiglio di regolare le impostazioni dell'applicazione secondo le tue aspettative. Clicca sull'icona delle impostazioni in basso a sinistra.

![GREEN-DESKTOP](assets/fr/04.webp)

Nel menu "*Generale*", puoi cambiare la lingua del software e abilitare le funzionalità sperimentali se lo desideri.

![GREEN-DESKTOP](assets/fr/05.webp)
Nel menu "*Rete*", puoi abilitare la connessione tramite Tor, una rete che cripta tutte le tue connessioni e rende le tue attività difficili da tracciare. Sebbene questa opzione possa rallentare leggermente le prestazioni dell'applicazione, è altamente consigliata per proteggere la tua privacy, specialmente se non stai utilizzando il tuo nodo completo.
![GREEN-DESKTOP](assets/fr/06.webp)

Per gli utenti che hanno il proprio nodo completo, Green offre la possibilità di connettersi ad esso tramite un server Electrum, garantendo il pieno controllo sulle informazioni della rete Bitcoin e sulla trasmissione delle transazioni. Per fare ciò, clicca sul menu "*Server personalizzati e validazione*", poi inserisci le informazioni del tuo server Electrum.

![GREEN-DESKTOP](assets/fr/07.webp)
Un'altra funzionalità alternativa è l'opzione "*SPV Verification*", che consente la verifica diretta di alcuni dati della blockchain, riducendo così la necessità di fidarsi del nodo predefinito di Blockstream, anche se questo metodo non offre tutte le garanzie di un nodo completo. Questa opzione si trova anche nel menu "*Custom servers and validation*".
![GREEN-DESKTOP](assets/fr/08.webp)

Una volta che queste impostazioni sono state regolate secondo le tue necessità, puoi uscire da questa interfaccia.

## Importare un Portafoglio Bitcoin in Blockstream Green

Ora sei pronto per importare il tuo portafoglio Bitcoin. Clicca sul pulsante "**Get Started**".

![GREEN-DESKTOP](assets/fr/09.webp)

Hai la scelta tra creare un portafoglio software locale o gestire un cold wallet tramite un hardware wallet. Per questo tutorial, ci concentreremo sulla gestione di un hardware wallet, quindi dovrai selezionare l'opzione "*On Hardware Wallet*".

L'opzione "*Watch-only*", d'altra parte, ti permette di importare una chiave pubblica estesa (`xpub`) per visualizzare le transazioni di un portafoglio senza essere in grado di spendere i fondi associati.

![GREEN-DESKTOP](assets/fr/10.webp)

Se stai utilizzando un Jade, clicca sul pulsante corrispondente. Altrimenti, seleziona "*Connect a different Hardware Device*". Nel mio caso, sto utilizzando un Ledger Nano S. Per gli utenti Ledger, assicurati di installare l'applicazione "*Bitcoin Legacy*" sul tuo hardware wallet, poiché Green supporta solo questa versione.

![GREEN-DESKTOP](assets/fr/11.webp)

Collega il tuo hardware wallet al computer e selezionalo su Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Attendi mentre Green importa le informazioni dal tuo portafoglio, dopo di che potrai accedervi.

![GREEN-DESKTOP](assets/fr/13.webp)

A questo punto, sono possibili due scenari. Se avevi già utilizzato il tuo hardware wallet in precedenza, dovresti vedere il tuo account apparire sul software. Ma se, come me, hai appena inizializzato il tuo hardware wallet generando una frase mnemonica senza averlo ancora utilizzato, dovrai creare un account. Clicca su "*Create Account*".
![GREEN-DESKTOP](assets/fr/14.webp)
Scegli "*Standard*" se desideri utilizzare un portafoglio classico.

![GREEN-DESKTOP](assets/fr/15.webp)

Ora hai accesso al tuo account.

![GREEN-DESKTOP](assets/fr/16.webp)

## Utilizzare un hardware wallet con Blockstream Green

Ora che il tuo portafoglio Bitcoin è configurato, sei pronto per ricevere i tuoi primi satoshi! Per farlo, basta cliccare sul pulsante "*Receive*".

![GREEN-DESKTOP](assets/fr/17.webp)

Clicca sul pulsante "*Copy address*" per copiare l'indirizzo, oppure scansiona il suo codice QR.

![GREEN-DESKTOP](assets/fr/18.webp)

Una volta che la transazione è trasmessa sulla rete, apparirà nel tuo portafoglio. Attendi di ottenere abbastanza conferme per considerare la transazione come immutabile.

![GREEN-DESKTOP](assets/fr/19.webp)

Con i bitcoin nel tuo portafoglio, ora sei in grado di inviarli. Clicca sul pulsante "*Send*".

![GREEN-DESKTOP](assets/fr/20.webp)

Nella pagina seguente, inserisci l'indirizzo del destinatario. Puoi inserirlo manualmente o scansionare un codice QR con la tua webcam.

![GREEN-DESKTOP](assets/fr/21.webp)

Scegli l'importo del pagamento.

![GREEN-DESKTOP](assets/fr/22.webp)
In fondo allo schermo, puoi selezionare la tariffa per questa transazione. Hai l'opzione di seguire le raccomandazioni dell'applicazione o personalizzare le tue tariffe. Più alte sono le tariffe rispetto ad altre transazioni in sospeso, più velocemente verrà elaborata la tua transazione. Per conoscere il mercato delle tariffe, puoi visitare [Mempool.space](https://mempool.space/) nella sezione "*Transaction Fees*".
![GREEN-DESKTOP](assets/fr/23.webp)

Se desideri selezionare specificamente quali UTXO utilizzare nella tua transazione, clicca sul pulsante "*Manual coin selection*".

![GREEN-DESKTOP](assets/fr/24.webp)

Controlla le impostazioni della tua transazione e, se tutto è come ti aspetti, clicca su "*Next*".

![GREEN-DESKTOP](assets/fr/25.webp)

Verifica ancora una volta che l'indirizzo, l'importo e le tariffe siano corretti, poi clicca su "*Confirm transaction*".

![GREEN-DESKTOP](assets/fr/26.webp)

Assicurati che tutti i parametri della transazione siano corretti sullo schermo del tuo hardware wallet, poi firma la transazione utilizzandolo.

![GREEN-DESKTOP](assets/fr/27.webp)

Una volta che la transazione è firmata dall'hardware wallet, Green la trasmette automaticamente sulla rete Bitcoin. La tua transazione apparirà quindi sulla dashboard del tuo portafoglio Bitcoin, in attesa di conferma.

![GREEN-DESKTOP](assets/fr/28.webp)

Ed ecco fatto, ora sai come configurare facilmente il software Blockstream Green per gestire il tuo portafoglio Bitcoin su un hardware wallet.
Se hai trovato utile questo tutorial, apprezzerei se potessi lasciare un pollice in su qui sotto. Sentiti libero di condividere questo articolo sui tuoi social network. Grazie mille!
Raccomando anche di consultare questo tutorial completo sull'app mobile Blockstream Green per configurare un hot wallet:

https://planb.network/tutorials/wallet/blockstream-green