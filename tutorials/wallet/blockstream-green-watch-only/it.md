---
name: Blockstream Green - Solo Visualizzazione
description: Configurazione di un portafoglio solo visualizzazione
---
![cover](assets/cover.webp)

In questo tutorial, imparerai come configurare facilmente un portafoglio solo visualizzazione su mobile utilizzando l'app Blockstream Green.

## Cos'è un Portafoglio Solo Visualizzazione?

Un portafoglio solo visualizzazione, o "watch-only wallet", è un tipo di software progettato per permettere all'utente di osservare le transazioni associate a una o più chiavi pubbliche Bitcoin specifiche, senza avere accesso alle corrispondenti chiavi private.

Questo tipo di applicazione conserva solo i dati necessari per monitorare un portafoglio Bitcoin, inclusi la visualizzazione del suo saldo e della cronologia delle transazioni, ma non ha accesso alle chiavi private. Pertanto, è impossibile spendere i bitcoin detenuti nel portafoglio sull'app solo visualizzazione.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Il solo visualizzazione è generalmente utilizzato in aggiunta a un hardware wallet. Quest'ultimo permette la conservazione sicura delle chiavi private del portafoglio su un dispositivo non connesso a Internet, che ha una superficie di attacco minima, isolando così le chiavi private da ambienti potenzialmente vulnerabili. L'app solo visualizzazione, d'altra parte, conserva esclusivamente la chiave pubblica estesa (`xpub`, `zpub`, ecc.) del portafoglio Bitcoin. Questa chiave madre non permette di scoprire le chiavi private associate e, di conseguenza, non permette la spesa dei bitcoin. Tuttavia, permette la derivazione di chiavi pubbliche figlie e indirizzi di ricezione. Con la conoscenza degli indirizzi del portafoglio protetto dall'hardware wallet, l'app solo visualizzazione può tracciare queste transazioni sulla rete Bitcoin, offrendo all'utente la possibilità di monitorare il proprio saldo e generare nuovi indirizzi di ricezione, senza dover connettere ogni volta il proprio hardware wallet.

In questo tutorial, propongo di scoprire una delle soluzioni di portafoglio solo visualizzazione più popolari su mobile: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Introduzione a Blockstream Green

Blockstream Green è un software disponibile su mobile e computer. In precedenza noto come Green Address, questo portafoglio è diventato un progetto Blockstream in seguito alla sua acquisizione nel 2016.

Green è un'applicazione molto facile da usare, rendendola particolarmente adatta ai principianti. Offre varie funzionalità, come la gestione di hot wallet, hardware wallet, così come portafogli sulla sidechain Liquid.

In questo tutorial, ci concentreremo esclusivamente sulla creazione di un portafoglio solo visualizzazione. Per esplorare altri usi di Green, ti invito a consultare i nostri altri tutorial dedicati:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Installazione e Configurazione dell'App Blockstream Green
Il primo passo è naturalmente scaricare l'app Green. Vai al tuo app store:
- [Per Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Per Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Per gli utenti Android, hai anche l'opzione di installare l'app tramite il file `.apk` [disponibile sul GitHub di Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Avvia l'app, poi spunta la casella "*Accetto i termini...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Quando apri Green per la prima volta, la schermata iniziale appare senza un portafoglio configurato. Più tardi, se crei o importi portafogli, appariranno in questa interfaccia. Prima di passare alla creazione di un portafoglio, ti consiglio di regolare le impostazioni dell'app in base alle tue aspettative. Clicca su "*Impostazioni Applicazione*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

L'opzione "*Privacy Migliorata*", disponibile solo su Android, migliora la privacy disabilitando gli screenshot e nascondendo le anteprime dell'app. Blocca anche automaticamente l'accesso all'app non appena il telefono viene bloccato, rendendo i tuoi dati più difficili da esporre.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Per coloro che desiderano migliorare la propria privacy, l'app offre la possibilità di instradare il proprio traffico attraverso Tor, una rete che cripta tutte le tue connessioni e rende le tue attività difficili da tracciare. Sebbene questa opzione possa rallentare leggermente le prestazioni dell'app, è altamente consigliata per proteggere la tua privacy, specialmente se non stai utilizzando il tuo nodo completo.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Per gli utenti che possiedono il proprio nodo completo, Green Wallet offre la possibilità di connettersi ad esso tramite un server Electrum, garantendo il pieno controllo sulle informazioni della rete Bitcoin e sulla trasmissione delle transazioni.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Un'altra funzionalità alternativa è l'opzione "*Verifica SPV*", che consente la verifica diretta di alcuni dati della blockchain, riducendo così la necessità di fidarsi del nodo predefinito di Blockstream, anche se questo metodo non fornisce tutte le garanzie di un nodo completo.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Una volta che queste impostazioni sono state regolate secondo le tue esigenze, clicca sul pulsante "*Salva*" e riavvia l'app.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Creazione di un portafoglio solo-visualizzazione su Blockstream Green
Ora sei pronto per creare un portafoglio solo-visualizzazione. Clicca sul pulsante "*Inizia*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Avrai la scelta tra diversi tipi di portafogli. Per questo tutorial, vogliamo creare un portafoglio solo-visualizzazione, quindi clicca sul pulsante corrispondente.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Scegli l'opzione "*Firma Singola*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Poi seleziona "*Bitcoin*". Per quanto mi riguarda, sto conducendo questo tutorial su un portafoglio testnet, ma la procedura rimane la stessa sul mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Ti verrà chiesto di fornire o una chiave pubblica estesa (`xpub`, `zpub`, ecc.), o un descrittore dello script di output.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Dovrai recuperare queste informazioni dal portafoglio che desideri seguire tramite il tuo portafoglio solo-visualizzazione. La chiave pubblica estesa non è sensibile in termini di sicurezza, in quanto non consente l'accesso alle chiavi private, ma è sensibile per la tua privacy, poiché rivela tutte le tue chiavi pubbliche e quindi tutte le tue transazioni Bitcoin.

Immagina di utilizzare Sparrow Wallet per gestire il tuo portafoglio su un hardware wallet, troverai queste informazioni nella sezione "*Impostazioni*". Trovare queste informazioni dipenderà dal software di gestione del portafoglio che stai utilizzando, ma generalmente si trovano nelle impostazioni.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Copia la tua chiave pubblica estesa e inseriscila nell'app Green, poi clicca su "*Connetti*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Potrai quindi vedere il saldo associato a questa chiave così come la cronologia delle transazioni.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Cliccando su "*Ricevi*", puoi generare un indirizzo di ricezione per ricevere bitcoin sul tuo portafoglio hardware. Tuttavia, consiglio di non utilizzare questa opzione senza prima verificare sullo schermo del portafoglio hardware che detiene la chiave privata associata all'indirizzo generato, prima di usarlo per bloccare i bitcoin. Questa è una buona pratica da seguire.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

L'opzione "*Sweep*" ti permette di inserire manualmente una chiave privata per spendere fondi direttamente dalla tua applicazione Green. Tranne in casi molto specifici, raccomando di non utilizzare questa funzione, poiché richiede di rivelare la tua chiave privata su un telefono, il quale è molto più vulnerabile agli attacchi informatici rispetto al tuo portafoglio hardware.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Ed ecco fatto, ora sai come impostare facilmente un portafoglio watch-only sul tuo smartphone! È uno strumento molto utile per monitorare un portafoglio su un portafoglio hardware senza doverlo collegare e sbloccare ogni volta.

Se hai trovato utile questo tutorial, apprezzerei se potessi lasciare un pollice in su qui sotto. Sentiti libero di condividere questo articolo sui tuoi social network. Grazie mille!

Raccomando anche di consultare questo tutorial completo sull'applicazione Blockstream Green per impostare un hot wallet:

https://planb.network/tutorials/wallet/blockstream-green