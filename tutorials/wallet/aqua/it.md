---
name: Aqua
description: Bitcoin, Lightning e Liquid in un unico portafoglio
---
![cover](assets/cover.webp)

Aqua è un'applicazione mobile che consente la facile creazione di un hot wallet per Bitcoin e Liquid, e offre anche la possibilità di utilizzare Lightning senza la complessità di gestire un nodo, grazie agli swap integrati. Supporta inoltre la gestione di stablecoin USDT su vari network.

Sviluppata dalla compagnia JAN3 sotto la guida di Samson Mow, l'applicazione Aqua è stata inizialmente progettata specificamente per le esigenze degli utenti in America Latina, sebbene sia adatta a qualsiasi utente in tutto il mondo. È particolarmente interessante per i principianti e coloro che utilizzano Bitcoin quotidianamente per i loro pagamenti.

In questo tutorial, esploreremo come utilizzare le numerose funzionalità di Aqua. Ma prima di ciò, prendiamoci un momento per capire cosa sia una sidechain su Bitcoin e come funziona Liquid, il che ci permetterà di comprendere appieno l'interesse di Aqua.

![AQUA](assets/fr/01.webp)

## Cos'è una sidechain?

Il protocollo Bitcoin ha delle limitazioni tecniche intenzionali che aiutano a mantenere la decentralizzazione della rete e assicurano una distribuzione della sicurezza tra tutti gli utenti. Tuttavia, questi limiti possono talvolta frustrare gli utenti, specialmente durante la congestione causata da un alto volume di transazioni simultanee. Il dibattito sulla scalabilità di Bitcoin ha a lungo diviso la comunità, in particolare durante la Blocksize War. Da quell'episodio, è ampiamente riconosciuto all'interno della comunità Bitcoin che la scalabilità deve essere garantita da soluzioni off-chain, su sistemi di secondo livello. Tra queste soluzioni ci sono le sidechain, che sono ancora relativamente sconosciute e sottoutilizzate rispetto ad altri sistemi come la Lightning Network.

Una sidechain è una blockchain indipendente che opera in parallelo alla blockchain principale di Bitcoin. Utilizza bitcoin come unità di conto attraverso un meccanismo chiamato "*two-way peg*". Questo sistema consente di bloccare bitcoin sulla catena principale per replicare il loro valore sulla sidechain, dove circolano come token supportati dai bitcoin originali. Questi token normalmente mantengono una parità di valore con i bitcoin bloccati sulla catena principale, e il processo può essere invertito per recuperare i fondi su Bitcoin.
L'obiettivo delle sidechain è offrire funzionalità aggiuntive o miglioramenti tecnici, come transazioni più veloci, commissioni ridotte o supporto per smart contract. Queste innovazioni non possono sempre essere implementate direttamente sulla blockchain di Bitcoin senza comprometterne la decentralizzazione o la sicurezza. Le sidechain consentono quindi di testare ed esplorare nuove soluzioni preservando l'integrità di Bitcoin. Tuttavia, questi protocolli spesso richiedono compromessi, in particolare in termini di decentralizzazione e sicurezza, a seconda del modello di governance e del meccanismo di consenso scelti.
## Cos'è Liquid?

Liquid è una sidechain federata costruita su Bitcoin, sviluppata da Blockstream, con l'obiettivo di migliorare la velocità, la privacy e le funzionalità delle transazioni. Utilizza un meccanismo di ancoraggio bilaterale stabilito su una federazione per bloccare bitcoin sulla catena principale e creare in cambio Liquid-bitcoin (L-BTC), token che circolano su Liquid rimanendo supportati dai bitcoin originali.

![AQUA](assets/fr/02.webp)

La rete Liquid si basa su una federazione di partecipanti, composta da entità riconosciute dell'ecosistema Bitcoin, che validano i blocchi e gestiscono l'ancoraggio bilaterale. Oltre a L-BTC, Liquid consente anche l'emissione di altri asset digitali, come lo stablecoin USDT o altre criptovalute.

![AQUA](assets/fr/03.webp)

## Installare l'App Aqua

Il primo passo è naturalmente scaricare l'app Aqua. Vai al tuo app store:
- [Per Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Per Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
Per gli utenti Android, avete anche l'opzione di installare l'app tramite il file `.apk` [disponibile sul loro GitHub](https://github.com/AquaWallet/aqua-wallet/releases).

Avvia l'app, poi spunta la casella "*Ho letto e accettato i Termini di Servizio & la Privacy Policy*".

## Creare il Tuo Portafoglio su Aqua

Clicca sul pulsante "*Crea Portafoglio*".

Ed ecco fatto, il tuo portafoglio è già creato!

Ma prima di tutto, poiché questo è un portafoglio di auto-custodia, è imperativo fare un backup fisico della tua frase mnemonica. **Questa frase mnemonica fornisce accesso completo e illimitato a tutti i tuoi bitcoin**. Chiunque sia in possesso di questa frase può rubare i tuoi fondi, anche senza accesso fisico al tuo telefono.
Ti permette di ripristinare l'accesso ai tuoi bitcoin in caso di perdita, furto o danneggiamento del tuo telefono. È quindi molto importante eseguire un backup con attenzione su un supporto fisico (non digitale) e conservarlo in un luogo sicuro. Puoi scriverla su un pezzo di carta, o, per maggiore sicurezza, se questo portafoglio è significativo, ti consiglio di incidere su un supporto in acciaio inossidabile per proteggere dai rischi di incendi, alluvioni o crolli (per un hot wallet destinato a proteggere una piccola quantità di bitcoin, un semplice backup su carta è probabilmente sufficiente).
Per fare ciò, clicca sul menu delle impostazioni.

Poi clicca su "*Visualizza Frase Seed*". Fai un backup fisico di questa frase di 12 parole.

In questo stesso menu delle impostazioni, puoi anche cambiare la lingua dell'applicazione così come la valuta fiat utilizzata.

Prima di ricevere i tuoi primi bitcoin nel tuo portafoglio, **ti consiglio vivamente di eseguire un test di recupero a secco**. Annota un'informazione di riferimento, come il tuo xpub o il primo indirizzo di ricezione, poi cancella il tuo portafoglio sull'app Aqua mentre è ancora vuoto. Successivamente, prova a ripristinare il tuo portafoglio su Aqua usando i tuoi backup su carta. Controlla che le informazioni di testimonianza generate dopo il ripristino corrispondano a quelle che avevi inizialmente annotato. Se è così, puoi essere sicuro che i tuoi backup su carta sono affidabili. Per saperne di più su come eseguire un test di recupero, ti consiglio di consultare questo altro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Ricevere bitcoin su Aqua

Ora che il tuo portafoglio è configurato, sei pronto per ricevere i tuoi primi satoshi! Semplicemente clicca sul pulsante "*Ricevi*" nel menu "*Portafoglio*".

Puoi scegliere di ricevere bitcoin onchain, su Liquid, o tramite Lightning.

Per le transazioni onchain, Aqua genererà un indirizzo specifico di ricezione dove puoi ricevere i tuoi satoshi.

Allo stesso modo, optando per Liquid, Aqua ti fornirà un indirizzo Liquid.

Se preferisci ricevere fondi tramite Lightning, dovrai prima specificare l'importo desiderato.

Poi, clicca su "*Genera Fattura*".
Aqua creerà una fattura per ricevere fondi da un portafoglio Lightning. È importante notare che, a differenza delle opzioni onchain e Liquid, i fondi ricevuti tramite Lightning verranno automaticamente convertiti in L-BTC su Liquid utilizzando lo strumento Boltz, poiché Aqua non è un nodo Lightning. Questo processo ti permette di ricevere e inviare fondi tramite Lightning, ma senza mai mantenere i tuoi bitcoin su Lightning. ![AQUA](assets/fr/18.webp)

Personalmente, inizierò inviando bitcoin tramite Lightning ad Aqua. Una volta completata la transazione con la fattura fornita, si riceve una conferma.

![AQUA](assets/fr/19.webp)

Per seguire il progresso dello swap, torna alla homepage del tuo portafoglio e clicca sul conto "*L2 Bitcoin*", che elenca le transazioni Lightning (tramite swap) e Liquid.

![AQUA](assets/fr/20.webp)

Qui, puoi visualizzare la tua transazione così come il tuo saldo in L-BTC.

![AQUA](assets/fr/21.webp)

## Scambiare bitcoin con Aqua

Ora che hai asset nel tuo portafoglio Aqua, hai l'opzione di scambiarli direttamente dall'app, sia per trasferirli alla blockchain principale di Bitcoin sia su Liquid. Puoi anche convertire i tuoi bitcoin nella stablecoin USDT (o altre). Per fare ciò, accedi al menu "*Marketplace*".

![AQUA](assets/fr/22.webp)

Clicca su "*Swaps*".

![AQUA](assets/fr/23.webp)

Nella casella "*Transfer from*", scegli l'asset che vuoi scambiare. Attualmente, ho solo L-BTC, quindi è quello che seleziono.

![AQUA](assets/fr/24.webp)

Nella casella "*Transfer to*", scegli l'asset di destinazione del tuo scambio. Per quanto mi riguarda, ho optato per USDT sulla rete Liquid.

![AQUA](assets/fr/25.webp)

Inserisci l'importo che desideri convertire.

![AQUA](assets/fr/26.webp)

Conferma cliccando su "*Continue*".

![AQUA](assets/fr/27.webp)

Assicurati che le impostazioni dello scambio siano di tuo gradimento, poi conferma scorrendo il pulsante "*Swap*" in fondo allo schermo.

![AQUA](assets/fr/28.webp)

Il tuo scambio è ora confermato.

![AQUA](assets/fr/29.webp)

Se torniamo al nostro portafoglio, possiamo vedere che ora abbiamo USDT su Liquid.

![AQUA](assets/fr/30.webp)

## Inviare bitcoin con Aqua

Ora che hai bitcoin nel tuo portafoglio Aqua, hai l'opzione di inviarli. Clicca sul pulsante "*Send*".

![AQUA](assets/fr/31.webp)

Scegli l'asset che vuoi inviare o seleziona la rete per eseguire la transazione. Per quanto mi riguarda, invierò bitcoin tramite Lightning.

![AQUA](assets/fr/32.webp)
Successivamente, inserisci le informazioni necessarie per l'invio del pagamento: per Bitcoin onchain o Liquid, devi inserire un indirizzo di ricezione; per Lightning, è richiesta una fattura. Puoi incollare queste informazioni direttamente nel campo designato o usare l'icona del codice QR per aprire la tua fotocamera e scansionare l'indirizzo o la fattura. Poi clicca su "*Continue*".
![AQUA](assets/fr/33.webp)

Clicca su "*Continue*" di nuovo se tutte le informazioni appaiono corrette.

![AQUA](assets/fr/34.webp)
Aqua ti presenta quindi un riepilogo della transazione. Assicurati che tutte le informazioni siano corrette, specialmente l'indirizzo di destinazione, le commissioni e l'importo. Per confermare la transazione, scorri il pulsante "*Scorri per inviare*" situato in fondo allo schermo.
![AQUA](assets/fr/35.webp)

Viene quindi fornita una conferma dell'invio.

![AQUA](assets/fr/36.webp)

Ed ecco fatto, ora sai come utilizzare l'app Aqua per ricevere e spendere fondi in Bitcoin, Lightning e Liquid, tutto da un'unica interfaccia.

Se hai trovato utile questo tutorial, apprezzerei se potessi lasciare un pollice in su qui sotto. Sentiti libero di condividere questo articolo sui tuoi social network. Grazie mille!

Ti consiglio anche di dare un'occhiata a questo altro tutorial completo sull'app mobile Blockstream Green, che rappresenta un'altra soluzione interessante per configurare il tuo portafoglio Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid