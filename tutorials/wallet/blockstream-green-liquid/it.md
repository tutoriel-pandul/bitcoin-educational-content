---
name: Blockstream Green - Liquid
description: Configurazione di un portafoglio sulla sidechain Liquid Network
---
![cover](assets/cover.webp)
Il protocollo Bitcoin presenta delle limitazioni tecniche intenzionali che aiutano a mantenere la decentralizzazione della rete e a garantire una distribuzione della sicurezza tra tutti gli utenti. Tuttavia, questi limiti possono talvolta frustrare gli utenti, specialmente durante la congestione causata da un alto volume di transazioni simultanee. Il dibattito sulla scalabilità di Bitcoin ha a lungo diviso la comunità, in particolare durante la Blocksize War. Da quell'episodio, è ampiamente riconosciuto all'interno della comunità Bitcoin che la scalabilità deve essere garantita da soluzioni off-chain, su sistemi di secondo livello. Tra queste soluzioni ci sono le sidechain, che sono ancora relativamente sconosciute e sottoutilizzate rispetto ad altri sistemi come la Lightning Network.

Una sidechain è una blockchain indipendente che opera in parallelo alla blockchain principale di Bitcoin. Utilizza bitcoin come unità di conto attraverso un meccanismo chiamato "*two-way peg*". Questo sistema consente di bloccare bitcoin sulla catena principale per replicarne il valore sulla sidechain, dove circolano come token supportati dai bitcoin originali. Questi token normalmente mantengono una parità di valore con i bitcoin bloccati sulla catena principale, e il processo può essere invertito per recuperare i fondi su Bitcoin.

L'obiettivo delle sidechain è offrire funzionalità aggiuntive o miglioramenti tecnici, come transazioni più veloci, commissioni ridotte o supporto per smart contract. Queste innovazioni non possono sempre essere implementate direttamente sulla blockchain di Bitcoin senza comprometterne la decentralizzazione o la sicurezza. Le sidechain consentono quindi di testare ed esplorare nuove soluzioni preservando l'integrità di Bitcoin. Tuttavia, questi protocolli spesso richiedono compromessi, in particolare in termini di decentralizzazione e sicurezza, a seconda del modello di governance e del meccanismo di consenso scelti.

Oggi, la sidechain probabilmente più conosciuta è Liquid. In questo tutorial, vi introdurrò prima a cosa sia Liquid, e poi vi guiderò su come iniziare facilmente a utilizzarla attraverso l'applicazione Blockstream Green, per sfruttarne i benefici.

![LIQUID GREEN](assets/fr/01.webp)

## Cos'è Liquid Network?

Liquid è una sidechain federata costruita su Bitcoin, sviluppata da Blockstream, con l'obiettivo di migliorare la velocità, la privacy e le funzionalità delle transazioni. Utilizza un meccanismo di ancoraggio bilaterale stabilito su una federazione per bloccare bitcoin sulla catena principale e creare, in cambio, Liquid-bitcoin (L-BTC), token che circolano su Liquid rimanendo supportati dai bitcoin originali.

![LIQUID GREEN](assets/fr/02.webp)
La rete Liquid si basa su una federazione di partecipanti, costituita da entità riconosciute dell'ecosistema Bitcoin, che validano i blocchi e gestiscono l'ancoraggio bilaterale. Oltre a L-BTC, Liquid consente anche l'emissione di altri asset digitali, come stablecoin o altre criptovalute.
![LIQUID GREEN](assets/fr/03.webp)

## Introduzione a Blockstream Green

Blockstream Green è un portafoglio software disponibile su mobile e desktop. In precedenza noto come *Green Address*, questo portafoglio è diventato un progetto Blockstream in seguito alla sua acquisizione nel 2016.

Green è un'applicazione particolarmente facile da usare, rendendola interessante per i principianti. Offre tutte le caratteristiche essenziali di un buon portafoglio Bitcoin, inclusa l'opzione RBF (*Replace-by-Fee*), un'opzione per connettersi tramite Tor, la possibilità di connettere il proprio nodo, l'opzione SPV (*Simple Payment Verification*), l'etichettatura e il controllo delle monete.

Blockstream Green supporta anche la rete Liquid, ed è questo che esploreremo in questo tutorial. Se desideri utilizzare Green per altre applicazioni, ti consiglio anche di consultare questi altri tutorial:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Installazione e configurazione dell'applicazione Blockstream Green

Il primo passo è naturalmente scaricare l'applicazione Green. Vai al tuo store di applicazioni:
- [Per Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Per Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Per gli utenti Android, è disponibile anche l'opzione di installare l'applicazione tramite il file `.apk` [disponibile sul GitHub di Blockstream](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Avvia l'applicazione, poi spunta la casella "*Accetto i termini...*".

![LIQUID GREEN](assets/fr/06.webp)

Quando apri Green per la prima volta, la schermata iniziale appare senza portafogli configurati. Più tardi, se crei o importi portafogli, appariranno in questa interfaccia. Prima di passare alla creazione di un portafoglio, ti consiglio di regolare le impostazioni dell'applicazione secondo le tue aspettative. Clicca su "*Impostazioni dell'applicazione*".

![LIQUID GREEN](assets/fr/07.webp)

L'opzione "*Privacy Migliorata*", disponibile solo su Android, migliora la privacy disabilitando gli screenshot e nascondendo le anteprime dell'applicazione. Blocca anche automaticamente l'accesso all'applicazione non appena il telefono viene bloccato, rendendo i tuoi dati più difficili da esporre.
![LIQUID GREEN](assets/fr/08.webp)
Per coloro che cercano di migliorare la propria privacy, l'app offre l'opzione di instradare il proprio traffico attraverso Tor, una rete che cripta tutte le tue connessioni e rende le tue attività difficili da tracciare. Sebbene questa opzione possa rallentare leggermente le prestazioni dell'app, è altamente raccomandata per proteggere la tua privacy, specialmente se non stai utilizzando il tuo nodo completo.

![LIQUID GREEN](assets/fr/09.webp)

Per gli utenti che possiedono il proprio nodo completo, Green Wallet consente di connettersi ad esso tramite un server Electrum, garantendo il pieno controllo sulle informazioni della rete Bitcoin e sulla trasmissione delle transazioni. Tuttavia, questa funzionalità è rilevante per i portafogli Bitcoin tradizionali, quindi non ne hai bisogno se stai utilizzando Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Un'altra funzionalità alternativa è l'opzione "*Verifica SPV*", che consente una verifica diretta di alcuni dati della blockchain, riducendo così la necessità di fidarsi del nodo predefinito di Blockstream, anche se questo metodo non fornisce tutte le garanzie di un nodo completo. Anche in questo caso, ciò riguarderà solo i tuoi portafogli Bitcoin onchain, e non Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Una volta regolate queste impostazioni secondo le tue esigenze, clicca sul pulsante "*Salva*" e riavvia l'app.

![LIQUID GREEN](assets/fr/12.webp)

## Creazione di un portafoglio Liquid su Blockstream Green

Ora sei pronto per creare un portafoglio Liquid. Clicca sul pulsante "*Inizia*".

![LIQUID GREEN](assets/fr/13.webp)

Hai la scelta tra creare un portafoglio software localmente o gestire un portafoglio freddo tramite un portafoglio hardware. Per questo tutorial, ci concentreremo sulla creazione di un hot wallet su Liquid, quindi dovrai selezionare l'opzione "*Su questo dispositivo*". Puoi anche utilizzare un portafoglio hardware compatibile, come il Blockstream Jade, per proteggere il tuo portafoglio Liquid.

![LIQUID GREEN](assets/fr/14.webp)
Puoi quindi scegliere di ripristinare un portafoglio Bitcoin esistente o crearne uno nuovo. Ai fini di questa guida, creeremo un nuovo portafoglio. Tuttavia, se hai bisogno di rigenerare un portafoglio Liquid esistente dalla sua frase mnemonica, ad esempio a causa della perdita del tuo hardware wallet, dovrai scegliere la seconda opzione.
![LIQUID GREEN](assets/fr/15.webp)

Avrai quindi la scelta tra una frase mnemonica di 12 parole o una di 24 parole. Questa frase ti permetterà di recuperare l'accesso al tuo portafoglio da qualsiasi software compatibile in caso di problemi con il tuo telefono. Attualmente, optare per una frase di 24 parole non offre più sicurezza di una frase di 12 parole. Pertanto, ti consiglio di scegliere una frase mnemonica di **12 parole**.
Green ti fornirà quindi la tua frase mnemonica. Prima di continuare, assicurati di non essere osservato. Clicca su "*Mostra frase di recupero*" per visualizzarla sullo schermo.
![LIQUID GREEN](assets/fr/16.webp)

**Questa frase mnemonica dà accesso completo e illimitato a tutti i tuoi bitcoin.** Chiunque sia in possesso di questa frase può rubare i tuoi fondi, anche senza accesso fisico al tuo telefono.

Ti permette di ripristinare l'accesso ai tuoi bitcoin in caso di perdita, furto o danneggiamento del tuo telefono. Pertanto, è molto importante salvarla con cura **su un supporto fisico (non digitale)** e conservarla in un luogo sicuro. Puoi scriverla su un pezzo di carta, o, per maggiore sicurezza, se questo portafoglio è significativo, ti consiglio di inciderla su un supporto in acciaio inossidabile per proteggerti dai rischi di incendi, alluvioni o crolli (per un hot wallet destinato a proteggere una piccola quantità di bitcoin, un semplice backup su carta è probabilmente sufficiente).

*Ovviamente, non dovresti mai condividere queste parole su internet, al contrario di quanto sto facendo in questa guida. Questo esempio di portafoglio verrà utilizzato solo sul Liquid Testnet e verrà cancellato al termine della guida.*

![LIQUID GREEN](assets/fr/17.webp)

Dopo aver correttamente annotato la tua frase mnemonica su un supporto fisico, clicca su "*Continua*". Green Wallet ti chiederà quindi di confermare alcune parole della tua frase per verificare che tu le abbia registrate correttamente. Compila gli spazi vuoti con le parole mancanti.

![LIQUID GREEN](assets/fr/18.webp)

Scegli il codice PIN per il tuo dispositivo, che verrà utilizzato per sbloccare il tuo portafoglio Green. Si tratta quindi di una protezione contro l'accesso fisico non autorizzato. Questo codice PIN non gioca un ruolo nella derivazione delle chiavi crittografiche del tuo portafoglio. Pertanto, anche senza accesso a questo codice PIN, il possesso della tua frase mnemonica di 12 o 24 parole ti permetterà di riguadagnare l'accesso ai tuoi bitcoin.

Si consiglia di scegliere un codice PIN di 6 cifre il più casuale possibile. Inoltre, assicurati di salvare questo codice per non dimenticarlo, altrimenti sarai costretto a recuperare il tuo portafoglio dalla frase mnemonica. Più tardi, potrai aggiungere un'opzione di blocco biometrico per evitare di inserire il PIN ogni volta che lo usi. In generale, la biometria è molto meno sicura del PIN stesso. Pertanto, di default, sconsiglio di impostare questa opzione di sblocco.

![LIQUID GREEN](assets/fr/19.webp)

Inserisci il tuo PIN una seconda volta per confermarlo.

![LIQUID GREEN](assets/fr/20.webp)
Attendi la creazione del tuo portafoglio, poi clicca sul pulsante "*Crea un account*".
![LIQUID GREEN](assets/fr/21.webp)
Nel riquadro "*Assets*", seleziona "*Liquid Bitcoin*". Avrai quindi la scelta tra un portafoglio a firma singola standard, che utilizzeremo in questo tutorial, o un portafoglio protetto da autenticazione a due fattori (2FA).
![LIQUID GREEN](assets/fr/22.webp)

Ed ecco fatto, il tuo portafoglio Liquid è stato creato con successo utilizzando l'app Green!

![LIQUID GREEN](assets/fr/23.webp)

Prima di ricevere i tuoi primi bitcoin sul tuo portafoglio Liquid, **ti consiglio vivamente di eseguire un test di recupero a vuoto**. Annota un'informazione di riferimento, come il tuo xpub o il primo indirizzo di ricezione, poi elimina il tuo portafoglio sull'app Green mentre è ancora vuoto. Successivamente, prova a ripristinare il tuo portafoglio su Green utilizzando i tuoi backup cartacei. Verifica che le informazioni di testimone generate dopo il ripristino corrispondano a quelle che avevi inizialmente annotato. Se così è, puoi essere sicuro che i tuoi backup cartacei sono affidabili. Per saperne di più su come eseguire un test di recupero, ti consiglio di consultare questo altro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Configurazione del tuo Portafoglio Liquid

Se desideri personalizzare il tuo portafoglio, clicca sui tre piccoli punti in alto a destra.

![LIQUID GREEN](assets/fr/24.webp)

L'opzione "*Rinomina*" ti permette di personalizzare il nome del tuo portafoglio, il che è particolarmente utile se gestisci più portafogli sulla stessa applicazione.

![LIQUID GREEN](assets/fr/25.webp)

Il menu "*Unità*" ti dà l'opzione di cambiare l'unità di base del tuo portafoglio. Ad esempio, puoi scegliere di visualizzarlo in satoshi piuttosto che in bitcoin.

![LIQUID GREEN](assets/fr/26.webp)

Il menu "*Impostazioni*" fornisce l'accesso alle diverse opzioni del tuo portafoglio Bitcoin.

![LIQUID GREEN](assets/fr/27.webp)

Qui troverai, ad esempio, il tuo *descrittore* che può essere utile se prevedi di impostare un portafoglio solo visualizzazione da questo portafoglio Liquid.

![LIQUID GREEN](assets/fr/28.webp)

Puoi anche cambiare il codice PIN del tuo portafoglio e abilitare l'accesso biometrico.

![LIQUID GREEN](assets/fr/29.webp)

## Utilizzo del tuo Portafoglio Liquid

Ora che il tuo portafoglio Liquid è configurato, sei pronto per ricevere i tuoi primi L-sat!
Se non possiedi ancora L-BTC, hai diverse opzioni a tua disposizione. La prima è farti inviare direttamente L-BTC. Se qualcuno vuole pagarti in bitcoin su Liquid, semplicemente dagli un indirizzo di ricezione. L'altra soluzione è scambiare i tuoi bitcoin onchain o quelli sulla rete Lightning per L-BTC. Per fare ciò, puoi utilizzare [un ponte come Boltz](https://boltz.exchange/). Inserisci semplicemente il tuo indirizzo Liquid sul sito, poi effettua il pagamento sia tramite la rete Lightning che onchain.
![LIQUID GREEN](assets/fr/30.webp)

Per generare un indirizzo Liquid, clicca sul pulsante "*Ricevi*".

![LIQUID GREEN](assets/fr/31.webp)

Green mostrerà quindi il primo indirizzo di ricezione vuoto del tuo portafoglio. Puoi sia scansionare il codice QR associato sia copiare direttamente l'indirizzo per inviare L-BTC ad esso.

![LIQUID GREEN](assets/fr/32.webp)

Quando la transazione viene trasmessa sulla rete, apparirà nel tuo portafoglio.

![LIQUID GREEN](assets/fr/33.webp)

Attendi di ottenere abbastanza conferme per considerare la transazione come definitiva. Su Liquid, le conferme dovrebbero essere rapide, poiché un blocco viene pubblicato ogni minuto.

![LIQUID GREEN](assets/fr/34.webp)
Con gli L-sats nel tuo portafoglio Liquid, ora puoi anche inviarli. Clicca su "*Invia*".
![LIQUID GREEN](assets/fr/35.webp)

Nella pagina successiva, inserisci l'indirizzo Liquid del destinatario. Puoi inserirlo manualmente o scansionare il loro codice QR.

![LIQUID GREEN](assets/fr/36.webp)

Scegli l'importo del pagamento.

![LIQUID GREEN](assets/fr/37.webp)

Clicca su "*Avanti*" per accedere a una schermata riassuntiva della tua transazione. Controlla che l'indirizzo, l'importo e le commissioni siano corretti.

![LIQUID GREEN](assets/fr/38.webp)

Se tutto ti sembra corretto, scorri il pulsante verde in fondo allo schermo verso destra per firmare e trasmettere la transazione sulla rete Bitcoin.

![LIQUID GREEN](assets/fr/39.webp)

La tua transazione apparirà ora nella dashboard del tuo portafoglio Bitcoin in attesa di conferma.

![LIQUID GREEN](assets/fr/40.webp)

Ed ecco fatto, ora sai come utilizzare facilmente la sidechain Liquid con l'applicazione Blockstream Green!

Se hai trovato utile questo tutorial, apprezzerei un pollice in su qui sotto. Sentiti libero di condividere questo articolo sui tuoi social network. Grazie mille!

Ti consiglio anche di scoprire questo altro tutorial completo sull'app mobile Blockstream Green per configurare un hot wallet Bitcoin onchain:

https://planb.network/tutorials/wallet/blockstream-green