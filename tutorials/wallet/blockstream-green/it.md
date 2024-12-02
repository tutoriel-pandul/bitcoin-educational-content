---
name: Blockstream Green - Mobile
description: Configurazione di un portafoglio software mobile
---

![cover](assets/cover.webp)

Un portafoglio software è un'applicazione installata su un computer, smartphone o qualsiasi altro dispositivo connesso a Internet, che consente la gestione e la sicurezza delle chiavi del proprio portafoglio Bitcoin. A differenza dei portafogli hardware, che isolano le chiavi private, i portafogli "caldi" operano quindi in un ambiente potenzialmente esposto a cyberattacchi, aumentando i rischi di hacking e furto.

I portafogli software sono da utilizzare per gestire quantità ragionevoli di bitcoin, specialmente per le transazioni quotidiane. Questa può essere anche un'opzione interessante per le persone con un portafoglio Bitcoin limitato, per le quali investire in un portafoglio hardware può sembrare sproporzionato. Tuttavia, la loro costante esposizione a Internet li rende meno sicuri per conservare i tuoi risparmi a lungo termine o fondi significativi. Per questi, è preferibile optare per soluzioni più sicure, come i portafogli hardware.

In questo tutorial, vi presenterò una delle migliori soluzioni di portafoglio software mobile: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Se sei interessato a imparare come usare Blockstream Green su un computer, ti preghiamo di fare riferimento a questo altro tutorial:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Introduzione a Blockstream Green

Blockstream Green è un portafoglio software disponibile sia su mobile che su computer. In precedenza noto come *Green Address*, questo portafoglio è diventato un progetto Blockstream a seguito della sua acquisizione nel 2016.

Green è un'applicazione particolarmente facile da usare, rendendola interessante per i principianti. Offre tutte le caratteristiche essenziali di un buon portafoglio Bitcoin, inclusi RBF (*Replace-by-Fee*), un'opzione per connettersi tramite Tor, la possibilità di connettere il proprio nodo, l'opzione SPV (*Simple Payment Verification*), l'etichettatura e il controllo delle monete.

Blockstream Green supporta anche la rete Liquid, una sidechain di Bitcoin sviluppata da Blockstream per effettuare transazioni veloci e riservate al di fuori della blockchain principale. Questo tutorial si concentra esclusivamente su Bitcoin, ma uno futuro tratterà l'uso di Liquid.

## Installazione e configurazione dell'app Blockstream Green

Il primo passo è naturalmente scaricare l'app Green. Vai al tuo app store:
- [Per Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Per Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Per gli utenti Android, avete anche l'opzione di installare l'applicazione tramite il file `.apk` [disponibile su GitHub di Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Avvia l'applicazione, quindi spunta la casella "*Accetto le condizioni...*".
![GREEN](assets/fr/04.webp)

Quando apri Green per la prima volta, appare la schermata iniziale senza portafogli configurati. In seguito, se crei o importi portafogli, appariranno in questa interfaccia. Prima di passare alla creazione di un portafoglio, ti consiglio di regolare le impostazioni dell'applicazione secondo le tue aspettative. Clicca su "*Impostazioni dell'applicazione*".

![GREEN](assets/fr/05.webp)

L'opzione "*Privacy avanzata*", disponibile solo su Android, migliora la privacy disabilitando gli screenshot e nascondendo le anteprime dell'applicazione. Blocca anche automaticamente l'accesso all'applicazione non appena il telefono viene bloccato, rendendo i tuoi dati più difficili da esporre.

![GREEN](assets/fr/06.webp)
Per coloro che desiderano migliorare la propria privacy, l'applicazione offre la possibilità di instradare il proprio traffico tramite Tor, una rete che cripta tutte le tue connessioni e rende le tue attività difficili da tracciare. Sebbene questa opzione possa rallentare leggermente le prestazioni dell'applicazione, è vivamente consigliata per proteggere la tua privacy, specialmente se non stai utilizzando il tuo nodo completo personale.
![GREEN](assets/fr/07.webp)

Per gli utenti che dispongono del proprio nodo completo, Green Wallet offre la possibilità di connettersi ad esso tramite un server Electrum, garantendo il pieno controllo sulle informazioni della rete Bitcoin e sulla trasmissione delle transazioni.

![GREEN](assets/fr/08.webp)

Un'altra funzionalità alternativa è l'opzione "*Verifica SPV*", che consente la verifica diretta di alcuni dati della blockchain, riducendo così la necessità di fidarsi del nodo Blockstream predefinito, anche se questo metodo non fornisce tutte le garanzie di un nodo completo.

![GREEN](assets/fr/09.webp)

Una volta che queste impostazioni sono state regolate secondo le tue necessità, clicca sul pulsante "*Salva*" e riavvia l'applicazione.

![GREEN](assets/fr/10.webp)

## Creazione di un Portafoglio Bitcoin su Blockstream Green

Ora sei pronto per creare un portafoglio Bitcoin. Clicca sul pulsante "*Inizia*".

![GREEN](assets/fr/11.webp)

Hai la scelta tra creare un portafoglio software localmente o gestire un portafoglio freddo tramite un portafoglio hardware. Per questo tutorial, ci concentreremo sulla creazione di un portafoglio caldo, quindi dovrai selezionare l'opzione "*Su Questo Dispositivo*". In un futuro tutorial, ti mostrerò come utilizzare l'altra opzione.

L'opzione "*Solo Visualizzazione*", d'altra parte, ti permette di importare una chiave pubblica estesa (`xpub`) per visualizzare le transazioni di un portafoglio senza essere in grado di spendere i fondi associati, il che è conveniente per monitorare un portafoglio su un portafoglio hardware, ad esempio.

![GREEN](assets/fr/12.webp)
Puoi quindi scegliere di ripristinare un portafoglio Bitcoin esistente o crearne uno nuovo. Ai fini di questo tutorial, creeremo un nuovo portafoglio. Tuttavia, se hai bisogno di rigenerare un portafoglio Bitcoin già esistente dalla sua frase mnemonica, ad esempio a causa della perdita del tuo portafoglio hardware, dovrai scegliere la seconda opzione.
![GREEN](assets/fr/13.webp)

Hai quindi la scelta tra una frase mnemonica di 12 parole o 24 parole. Questa frase ti permetterà di recuperare l'accesso al tuo portafoglio da qualsiasi software compatibile in caso di problemi con il tuo telefono. Attualmente, optare per una frase di 24 parole non offre più sicurezza di una frase di 12 parole. Pertanto, ti consiglio di scegliere una frase mnemonica di **12 parole**.

Green ti fornirà quindi la tua frase mnemonica. Prima di continuare, assicurati di non essere osservato. Clicca su "*Mostra frase di recupero*" per visualizzarla sullo schermo.

![GREEN](assets/fr/14.webp)

**Questa frase mnemonica dà accesso completo e illimitato a tutti i tuoi bitcoin.** Chiunque sia in possesso di questa frase può rubare i tuoi fondi, anche senza accesso fisico al tuo telefono.

Ti permette di ripristinare l'accesso ai tuoi bitcoin in caso di perdita, furto o danneggiamento del tuo telefono. È quindi molto importante salvarla con cura **su un supporto fisico (non digitale)** e conservarla in un luogo sicuro. Puoi scriverla su un pezzo di carta, o, per maggiore sicurezza, se questo portafoglio è importante, ti consiglio di incidere su un supporto in acciaio inossidabile per proteggere dai rischi di incendi, alluvioni o crolli (per un portafoglio caldo destinato a proteggere una piccola quantità di bitcoin, un semplice backup su carta è probabilmente sufficiente).
*Ovviamente, non dovresti mai condividere queste parole su internet, al contrario di quanto sto facendo in questo tutorial. Questo esempio di portafoglio verrà utilizzato solo sulla Testnet e verrà eliminato alla fine del tutorial.*
![GREEN](assets/fr/15.webp)

Dopo aver correttamente annotato la tua frase mnemonica su un supporto fisico, clicca su "*Continua*". Green Wallet ti chiederà quindi di confermare alcune parole della tua frase per verificare che tu le abbia registrate correttamente. Compila gli spazi vuoti con le parole mancanti.

![GREEN](assets/fr/16.webp)

Scegli il codice PIN per il tuo dispositivo, che verrà utilizzato per sbloccare il tuo portafoglio Green. Si tratta quindi di una protezione contro l'accesso fisico non autorizzato. Questo codice PIN non gioca un ruolo nella derivazione delle chiavi crittografiche del tuo portafoglio. Pertanto, anche senza accesso a questo codice PIN, il possesso della tua frase mnemonica di 12 o 24 parole ti permetterà di riguadagnare l'accesso ai tuoi bitcoin.
Si raccomanda di scegliere un PIN di 6 cifre il più casuale possibile. Inoltre, assicurati di fare un backup di questo codice per non dimenticarlo, altrimenti, sarai costretto a recuperare il tuo portafoglio utilizzando la frase mnemonica. Successivamente, puoi aggiungere un'opzione di blocco biometrico per evitare di inserire il PIN ad ogni utilizzo. Generalmente parlando, la biometria è molto meno sicura del PIN stesso. Pertanto, di default, sconsiglio di impostare questa opzione di sblocco.
![GREEN](assets/fr/17.webp)

Inserisci il tuo PIN una seconda volta per confermarlo.

![GREEN](assets/fr/18.webp)

Attendi la creazione del tuo portafoglio, poi clicca sul pulsante "*Crea un account*".

![GREEN](assets/fr/19.webp)

Hai quindi la scelta tra un portafoglio standard a firma singola, che utilizzeremo in questo tutorial, o un portafoglio protetto da autenticazione a due fattori (2FA).

![GREEN](assets/fr/20.webp)

L'opzione 2FA su Green crea un portafoglio multisignature 2/2, una delle cui chiavi è conservata da Blockstream. Questo significa che per effettuare una transazione, sono necessarie entrambe le chiavi: una chiave locale protetta dal tuo PIN sul telefono, e una chiave remota assicurata da 2FA sui server di Blockstream. In caso di perdita di accesso al 2FA o di indisponibilità dei servizi di Blockstream, meccanismi di recupero basati su script con time-lock assicurano la possibilità di recuperare in modo indipendente i tuoi fondi. Sebbene questa configurazione riduca significativamente il rischio di furto dei tuoi bitcoin, è più complessa da gestire e dipende parzialmente da Blockstream. Per questo tutorial, opteremo per un classico portafoglio a firma singola, con chiavi memorizzate localmente sul telefono.

Ed ecco fatto, il tuo portafoglio Bitcoin è stato creato con successo utilizzando l'app Green!

![GREEN](assets/fr/21.webp)

Prima di ricevere i tuoi primi bitcoin nel tuo portafoglio, **ti consiglio vivamente di eseguire un test di recupero a secco**. Annota un'informazione di riferimento, come il tuo xpub o il primo indirizzo di ricezione, poi elimina il tuo portafoglio sull'app Green mentre è ancora vuoto. Successivamente, prova a ripristinare il tuo portafoglio su Green utilizzando i tuoi backup cartacei. Verifica che le informazioni di testimonianza generate dopo il ripristino corrispondano a quelle che avevi inizialmente annotato. Se è così, puoi essere sicuro che i tuoi backup cartacei sono affidabili. Per saperne di più su come eseguire un test di recupero, ti consiglio di consultare questo altro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Configurazione del tuo portafoglio su Blockstream Green
Se vuoi personalizzare il tuo portafoglio, clicca sui tre piccoli punti in alto a destra.
![GREEN](assets/fr/22.webp)
L'opzione "*Rinomina*" ti permette di personalizzare il nome del tuo portafoglio, il che è particolarmente utile se gestisci più portafogli sulla stessa app.
![VERDE](assets/fr/23.webp)

Il menu "*Unità*" ti dà l'opzione di cambiare l'unità base del tuo portafoglio. Ad esempio, puoi scegliere di visualizzarlo in satoshi piuttosto che in bitcoin.

![VERDE](assets/fr/24.webp)

Il menu "*Impostazioni*" fornisce accesso alle diverse opzioni del tuo portafoglio Bitcoin.

![VERDE](assets/fr/25.webp)

Qui, ad esempio, troverai la tua chiave pubblica estesa e il suo *descrittore*, utile se prevedi di impostare un portafoglio solo visualizzazione da questo portafoglio.

![VERDE](assets/fr/26.webp)

Puoi anche cambiare il codice PIN del tuo portafoglio e abilitare l'accesso biometrico.

![VERDE](assets/fr/27.webp)

## Utilizzando Blockstream Green

Ora che il tuo portafoglio Bitcoin è configurato, sei pronto per ricevere i tuoi primi sat! Per fare ciò, basta cliccare sul pulsante "*Ricevi*".

![VERDE](assets/fr/28.webp)

Green mostrerà quindi il primo indirizzo di ricezione vuoto del tuo portafoglio. Puoi sia scansionare il codice QR associato sia copiare direttamente l'indirizzo per inviare bitcoin su di esso. Questo tipo di indirizzo non specifica l'importo da inviare da parte del pagatore. Tuttavia, puoi generare un indirizzo che richiede un importo specifico, cliccando sui tre piccoli punti in alto a destra, poi su "*Richiedi Importo*", e inserendo l'importo desiderato.

Poiché stai utilizzando un account Segwit v0 (BIP84), il tuo indirizzo inizierà con `bc1q...`. Nel mio esempio, sto utilizzando un portafoglio Testnet, quindi il prefisso è leggermente diverso.

![VERDE](assets/fr/29.webp)

Quando la transazione viene trasmessa sulla rete, apparirà nel tuo portafoglio.

![VERDE](assets/fr/30.webp)

Attendi di ottenere abbastanza conferme per considerare la transazione come definitiva.

![VERDE](assets/fr/31.webp)

Con i bitcoin nel tuo portafoglio, ora puoi anche inviarli. Clicca su "*Invia*".

![VERDE](assets/fr/32.webp)

Nella pagina successiva, inserisci l'indirizzo del destinatario. Puoi inserirlo manualmente o scansionare un codice QR.

![VERDE](assets/fr/33.webp)

Scegli l'importo del pagamento.

![VERDE](assets/fr/34.webp)
In fondo allo schermo, puoi selezionare la tariffa per questa transazione. Hai l'opzione di seguire le raccomandazioni dell'applicazione o di personalizzare le tue tariffe. Più alte sono le tariffe rispetto ad altre transazioni in sospeso, più velocemente verrà elaborata la tua transazione. Per comprendere il mercato delle tariffe, puoi visitare [Mempool.space](https://mempool.space/) nella sezione "*Tariffe Transazione*".
![VERDE](assets/fr/35.webp)

Clicca su "*Avanti*" per accedere a una schermata riassuntiva della tua transazione. Verifica che l'indirizzo, l'importo e le tariffe siano corretti.

![VERDE](assets/fr/36.webp)

Se tutto è di tuo gradimento, scorri il pulsante verde in fondo allo schermo verso destra per firmare e trasmettere la transazione sulla rete Bitcoin.

![VERDE](assets/fr/37.webp)

La tua transazione apparirà ora sulla dashboard del tuo portafoglio Bitcoin in attesa di conferma.

![VERDE](assets/fr/38.webp)
*Questo tutorial si basa su [una versione originale appartenente a Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) scritta da Loïc Morel. Bitstack è una neo-banca francese di Bitcoin che offre la possibilità di risparmiare in bitcoin, sia tramite DCA (Dollar Cost Averaging) che attraverso un sistema automatico di arrotondamento delle spese quotidiane.*