---
name: Blockstream Green - 2FA
description: Configurazione di un multisig 2/2 su Green Wallet
---
![cover](assets/cover.webp)

Un portafoglio software è un'applicazione installata su un computer, smartphone o qualsiasi altro dispositivo connesso a Internet, che consente la gestione e la sicurezza delle chiavi del proprio portafoglio Bitcoin. A differenza dei portafogli hardware, che isolano le chiavi private, i portafogli "caldi" operano quindi in un ambiente potenzialmente esposto a cyberattacchi, aumentando i rischi di hacking e furto.

I portafogli software sono da utilizzare per gestire quantità ragionevoli di bitcoin, specialmente per le transazioni quotidiane. Questa può essere anche un'opzione interessante per le persone con un portafoglio Bitcoin limitato, per le quali investire in un portafoglio hardware potrebbe sembrare sproporzionato. Tuttavia, la loro costante esposizione a Internet li rende meno sicuri per conservare i tuoi risparmi a lungo termine o fondi significativi. Per questi, è preferibile optare per soluzioni più sicure, come i portafogli hardware.

In questo tutorial, vi mostrerò come migliorare la sicurezza di un portafoglio caldo utilizzando l'opzione "2FA" su Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Introduzione a Blockstream Green

Blockstream Green è un portafoglio software disponibile su mobile e desktop. In precedenza noto come *Green Address*, questo portafoglio è diventato un progetto Blockstream a seguito della sua acquisizione nel 2016.

Green è un'applicazione particolarmente facile da usare, rendendola interessante per i principianti. Offre tutte le caratteristiche essenziali di un buon portafoglio Bitcoin, inclusi RBF (*Replace-by-Fee*), un'opzione per connettersi tramite Tor, la possibilità di connettere il proprio nodo, l'opzione SPV (*Simple Payment Verification*), l'etichettatura e il controllo delle monete.

Blockstream Green supporta anche la rete Liquid, una sidechain di Bitcoin sviluppata da Blockstream per condurre transazioni veloci e riservate al di fuori della blockchain principale. In questo tutorial, ci concentriamo esclusivamente su Bitcoin, ma ho anche realizzato un altro tutorial per imparare come usare Liquid su Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## L'opzione multisig 2/2 (2FA)

Su Green, puoi certamente creare un classico portafoglio caldo "singlesig". Ma hai anche l'opzione "multisig 2FA", che ti consente di migliorare la sicurezza del tuo portafoglio caldo senza complicarne eccessivamente la gestione quotidiana.
Imposterai quindi un portafoglio multisig 2/2, il che significa che ogni transazione richiederà la firma di due chiavi. La prima chiave, derivata dalla tua frase mnemonica di 12 o 24 parole, è protetta localmente con un codice PIN sul tuo telefono. Hai il pieno controllo su questa chiave. La seconda chiave è detenuta dai server di Blockstream, e il suo utilizzo per la firma richiede autenticazione, che può essere ottenuta tramite un codice ricevuto via email, SMS, chiamata telefonica o, come vedremo in questo tutorial, tramite un'app di autenticazione (Authy, Google Authenticator, ecc.).

Per garantire la tua autonomia in caso di fallimento di Blockstream (ad esempio, se l'azienda fallisce o i server che detengono la seconda chiave vengono distrutti), viene applicato un meccanismo di timelock al tuo multisig. Questo meccanismo trasforma il multisig 2/2 in un multisig 1/2 dopo circa un anno (o precisamente 51.840 blocchi, ma questo valore può essere modificato), dopo il quale il tuo portafoglio avrà bisogno solo della tua chiave locale per spendere i bitcoin. Quindi, se perdi l'accesso ai server di Blockstream o all'autenticazione 2FA, ti basta aspettare fino a un anno per poter utilizzare liberamente i tuoi bitcoin con la tua app, senza dipendere da Blockstream.
Questo metodo aumenta significativamente la sicurezza del tuo portafoglio online, mantenendoti al contempo in controllo dei tuoi bitcoin e facilitandone l'uso quotidiano. Tuttavia, richiede un aggiornamento regolare del timelock per mantenere la sicurezza del 2FA. Il conto alla rovescia di 360 giorni, durante il quale i tuoi fondi sono protetti dal 2FA, inizia non appena ricevi bitcoin. Se, 360 giorni dopo averli ricevuti, non hai effettuato una transazione spendendo quei fondi, i tuoi bitcoin saranno protetti solo dalla tua chiave locale, senza il 2FA.

Questa limitazione rende l'opzione 2FA più adatta a un portafoglio di spesa, dove le transazioni regolari rinnovano automaticamente i timelock. Per un portafoglio di risparmio a lungo termine, ciò può essere problematico, poiché dovrai pensare a eseguire una transazione di sweep verso te stesso ogni anno prima che il timelock scada.

Un altro svantaggio di questo metodo di sicurezza è che dovrai utilizzare schemi di script minoritari. Ciò significa che, da un punto di vista della privacy, le cose si complicano: pochissime persone utilizzano lo stesso tipo di script di te, permettendo a un osservatore esterno di identificare più facilmente l'impronta del tuo portafoglio. Inoltre, questi script comporteranno commissioni di transazione più elevate a causa della loro maggiore dimensione.
Se preferisci non utilizzare l'opzione 2FA e vuoi semplicemente configurare un portafoglio "singlesig" su Green, ti invito a consultare questo altro tutorial:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Installazione e configurazione del software Blockstream Green

Il primo passo è naturalmente scaricare l'app Green. Vai al tuo app store:
- [Per Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Per Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

Per gli utenti Android, hai anche l'opzione di installare l'app tramite il file `.apk` [disponibile su GitHub di Blockstream](https://github.com/Blockstream/green_android/releases).

Avvia l'app, poi spunta la casella "*Accetto i termini...*".

Quando apri Green per la prima volta, la schermata principale appare senza nessun portafoglio configurato. In seguito, se crei o importi portafogli, appariranno in questa interfaccia. Prima di passare alla creazione di un portafoglio, ti consiglio di regolare le impostazioni dell'app secondo le tue aspettative. Clicca su "*Impostazioni dell'applicazione*".

L'opzione "*Privacy Avanzata*", disponibile solo su Android, migliora la privacy disabilitando gli screenshot e nascondendo le anteprime dell'app. Blocca anche automaticamente l'accesso all'app non appena il telefono viene bloccato, rendendo i tuoi dati più difficili da esporre.

Per coloro che desiderano migliorare la loro privacy, l'app offre di instradare il tuo traffico attraverso Tor, una rete che cripta tutte le tue connessioni e rende le tue attività difficili da tracciare. Sebbene questa opzione possa rallentare leggermente le prestazioni dell'app, è altamente raccomandata per proteggere la tua privacy, specialmente se non stai utilizzando il tuo nodo completo.

Per gli utenti che hanno il proprio nodo completo, Green Wallet offre la possibilità di connettersi ad esso tramite un server Electrum, garantendo il pieno controllo sulle informazioni della rete Bitcoin e sulla trasmissione delle transazioni.
Un'altra funzionalità alternativa è l'opzione "*SPV Verification*", che consente la verifica diretta di alcuni dati della blockchain, riducendo così la necessità di fidarsi del nodo predefinito di Blockstream, anche se questo metodo non fornisce tutte le garanzie di un nodo completo.

Una volta che queste impostazioni sono state regolate secondo le tue esigenze, clicca sul pulsante "*Salva*" e riavvia l'applicazione.

## Creazione di un Portafoglio Bitcoin su Blockstream Green

Ora sei pronto per creare un portafoglio Bitcoin. Clicca sul pulsante "*Inizia*".

Hai la scelta tra creare un portafoglio software localmente o gestire un portafoglio freddo tramite un portafoglio hardware. Per questo tutorial, ci concentreremo sulla creazione di un portafoglio caldo, quindi dovrai selezionare l'opzione "*Su Questo Dispositivo*".

Successivamente, puoi scegliere di ripristinare un portafoglio Bitcoin esistente o crearne uno nuovo. Per gli scopi di questo tutorial, creeremo un nuovo portafoglio. Tuttavia, se hai bisogno di rigenerare un portafoglio Bitcoin esistente dalla sua frase mnemonica, ad esempio, a causa della perdita del tuo vecchio telefono, dovrai scegliere la seconda opzione.

Quindi hai la scelta tra una frase mnemonica di 12 parole o 24 parole. Questa frase ti permetterà di recuperare l'accesso al tuo portafoglio da qualsiasi software compatibile in caso di problemi con il tuo telefono. Attualmente, optare per una frase di 24 parole non offre più sicurezza di una frase di 12 parole. Pertanto, ti consiglio di scegliere una frase mnemonica di **12 parole**.

Green ti fornirà quindi la tua frase mnemonica. Prima di continuare, assicurati di non essere osservato. Clicca su "*Mostra frase di recupero*" per visualizzarla sullo schermo.

**Questa frase mnemonica dà accesso completo e illimitato a tutti i tuoi bitcoin**. Chiunque sia in possesso di questa frase può rubare i tuoi fondi, anche senza accesso fisico al tuo telefono (in condizioni di timelock scaduto o 2FA nel caso di un portafoglio 2/2 su Green).

Ti consente di ripristinare l'accesso alle tue chiavi locali in caso di perdita, furto o danneggiamento del tuo telefono. È quindi molto importante salvarla con cura **su un supporto fisico (non digitale)** e conservarla in un luogo sicuro. Puoi scriverla su un pezzo di carta, o, per maggiore sicurezza, se questo portafoglio è importante, ti consiglio di inciderla su un supporto in acciaio inossidabile per proteggerti dai rischi di incendi, alluvioni o crolli (per un portafoglio caldo destinato a proteggere una piccola quantità di bitcoin, un semplice backup su carta è probabilmente sufficiente).
*Ovviamente, non dovresti mai condividere queste parole su internet, a differenza di quanto sto facendo in questo tutorial. Questo portafoglio di esempio verrà utilizzato solo sulla Testnet e verrà cancellato alla fine del tutorial.*

Dopo aver correttamente annotato la tua frase mnemonica su un supporto fisico, clicca su "*Continua*". Green Wallet ti chiederà quindi di confermare alcune parole della tua frase per verificare che tu le abbia registrate correttamente. Compila gli spazi vuoti con le parole mancanti.
Scegli il codice PIN per il tuo dispositivo, che verrà utilizzato per sbloccare il tuo portafoglio Green. Si tratta quindi di una protezione contro l'accesso fisico non autorizzato. Questo codice PIN non gioca un ruolo nella derivazione delle chiavi crittografiche del tuo portafoglio. Pertanto, anche senza accesso a questo codice PIN, il possesso della tua frase mnemonica di 12 o 24 parole ti permetterà di riguadagnare l'accesso alle tue chiavi locali.
Si raccomanda di scegliere un codice PIN di 6 cifre il più casuale possibile. Inoltre, assicurati di salvare questo codice per non dimenticarlo, altrimenti sarai costretto a recuperare il tuo portafoglio dalla frase mnemonica. Puoi in seguito aggiungere un'opzione per il blocco biometrico per evitare di inserire il PIN ogni volta. Generalmente parlando, la biometria è molto meno sicura del PIN stesso. Pertanto, di default, sconsiglio di impostare questa opzione di sblocco.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Inserisci nuovamente il tuo PIN per confermarlo.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Attendi mentre il tuo portafoglio viene creato, poi clicca sul pulsante "*Crea un account*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Hai quindi la scelta tra un portafoglio a firma singola standard o un portafoglio protetto da autenticazione a due fattori (2FA). In questo tutorial, sceglieremo la seconda opzione.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Ed ecco fatto, il tuo portafoglio multisig Bitcoin è stato creato con successo utilizzando l'app Green!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Impostazione del 2FA

Clicca sul tuo account.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Clicca sul pulsante verde "*Aumenta la sicurezza del tuo account aggiungendo il 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Avrai quindi l'opzione di scegliere il metodo di autenticazione per accedere alla seconda chiave del tuo multisig 2/2. Per questo tutorial, utilizzeremo un'app di autenticazione. Se non sei familiare con questo tipo di app, ti consiglio di consultare il nostro tutorial su Authy:
https://planb.network/tutorials/others/authy

Seleziona "*Applicazione Authenticator*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green mostrerà quindi un codice QR e una chiave di recupero. Questa chiave ti permette di ripristinare l'accesso al tuo 2FA in caso di perdita della tua app Authy. Si raccomanda di fare un backup sicuro di questa chiave, anche se potrai sempre riguadagnare l'accesso ai tuoi bitcoin dopo la scadenza del timelock, come spiegato in precedenza.

Nella tua app di autenticazione, aggiungi un nuovo codice, poi scansiona il codice QR fornito da Green.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Ovviamente, non dovresti mai condividere questa chiave e codice QR su internet, contrariamente a quanto sto facendo in questo tutorial. Questo portafoglio di esempio verrà utilizzato solo sulla Testnet e verrà cancellato al termine del tutorial.*

Clicca sul pulsante "*Continua*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Inserisci il codice dinamico di 6 cifre presente sulla tua app di autenticazione.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

L'autenticazione a due fattori è ora abilitata.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Navigando in questo menu, puoi anche regolare la durata del timelock. Questo conto alla rovescia inizia al ricevimento di bitcoin e, una volta scaduto il timelock, i tuoi fondi possono essere spesi solo con la tua chiave locale, senza richiedere il 2FA. La durata predefinita è impostata a 12 mesi, ma per un portafoglio di risparmio, scegliere 15 mesi può essere saggio per minimizzare la frequenza dei rinnovi del timelock. Al contrario, per un portafoglio di spesa, un timelock di 6 mesi potrebbe essere preferibile, poiché verrà frequentemente rinnovato con le tue transazioni quotidiane, e un timelock più breve riduce l'attesa in caso di problemi con il 2FA. Sta a te determinare la durata del timelock che meglio si adatta alle tue esigenze.

![GREEN 2FA MULTISIG](assets/fr/30.webp)

Ora puoi uscire da questo menu. Il tuo portafoglio multisig è pronto!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Configurazione del tuo portafoglio su Blockstream Green

Se desideri personalizzare il tuo portafoglio, clicca sui tre piccoli punti in alto a destra.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
L'opzione "*Rinomina*" ti permette di personalizzare il nome del tuo portafoglio, il che è particolarmente utile se gestisci più portafogli sulla stessa applicazione.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

Il menu "*Unità*" ti dà l'opzione di cambiare l'unità base del tuo portafoglio. Ad esempio, puoi scegliere di visualizzarlo in satoshi piuttosto che in bitcoin.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

Il menu "*Impostazioni*" fornisce accesso alle diverse opzioni del tuo portafoglio Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Qui, ad esempio, troverai la tua chiave pubblica estesa e il suo *descrittore*, utile se prevedi di configurare un portafoglio solo visualizzazione da questo portafoglio.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Puoi anche cambiare il codice PIN del tuo portafoglio e abilitare l'accesso biometrico.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Utilizzo di Blockstream Green

Ora che il tuo portafoglio Bitcoin è configurato, sei pronto per ricevere i tuoi primi satoshi! Per fare ciò, basta cliccare sul pulsante "*Ricevi*".

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green mostrerà quindi il primo indirizzo di ricezione vuoto del tuo portafoglio. Puoi sia scansionare il codice QR associato sia copiare direttamente l'indirizzo per inviare bitcoin ad esso. Questo tipo di indirizzo non specifica l'importo da inviare da parte del pagatore. Tuttavia, puoi generare un indirizzo che richiede un importo specifico, cliccando sui tre piccoli punti in alto a destra, poi su "*Richiedi Importo*", e inserendo l'importo desiderato.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Quando la transazione viene trasmessa sulla rete, apparirà nel tuo portafoglio.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Attendi di ottenere abbastanza conferme per considerare la transazione come definitiva.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Con i bitcoin nel tuo portafoglio, ora puoi anche inviarli. Clicca su "*Invia*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Nella pagina seguente, inserisci l'indirizzo del destinatario. Puoi inserirlo manualmente o scansionare un codice QR.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Scegli l'importo del pagamento.
![GREEN 2FA MULTISIG](assets/fr/44.webp) In fondo allo schermo, puoi selezionare la tariffa per questa transazione. Hai l'opzione di seguire le raccomandazioni dell'applicazione o di personalizzare le tue commissioni. Più alte sono le commissioni rispetto ad altre transazioni in attesa, più velocemente verrà elaborata la tua transazione. Per comprendere il mercato delle commissioni, puoi visitare [Mempool.space](https://mempool.space/) nella sezione "*Transaction Fees*".

![GREEN 2FA MULTISIG](assets/fr/45.webp)

Clicca su "*Avanti*" per accedere a una schermata riassuntiva della tua transazione. Verifica che l'indirizzo, l'importo e le commissioni siano corretti.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Se tutto ti sembra corretto, scorri il pulsante verde in fondo allo schermo verso destra per firmare e trasmettere la transazione sulla rete Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Questo è il momento in cui devi inserire il tuo codice di autenticazione per sbloccare la seconda chiave del multisig detenuta da Blockstream. Inserisci il codice a 6 cifre visualizzato sulla tua app di autenticazione.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

La tua transazione apparirà ora sulla dashboard del tuo portafoglio Bitcoin in attesa di conferma.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Ed ecco fatto, ora sai come impostare facilmente un portafoglio multisig 2/2 utilizzando l'opzione 2FA di Blockstream Green!

Se hai trovato utile questo tutorial, apprezzerei se potessi lasciare un pollice verde qui sotto. Sentiti libero di condividere questo articolo sui tuoi social network. Grazie mille!

Raccomando anche di controllare questo altro tutorial completo sull'app mobile Blockstream Green per impostare un portafoglio Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid