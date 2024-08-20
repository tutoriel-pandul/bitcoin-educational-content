Proposta per l'implementazione di un nuovo modificatore SigHash Flag in Bitcoin, introdotto con il BIP118. `SIGHASH_ANYPREVOUT` permette una maggiore flessibilità nella gestione delle transazioni, specialmente per applicazioni avanzate come i canali di pagamento sulla Lightning Network e l'aggiornamento Eltoo. Il `SIGHASH_ANYPREVOUT` consente alla firma di non essere vincolata a nessun UTXO precedente specifico (*Any Previous Output*). Utilizzato in combinazione con `SIGHASH_ALL`, permetterebbe di firmare tutti gli output di una transazione, ma nessuno degli input. Ciò consentirebbe il riutilizzo della firma per diverse transazioni, a patto che siano soddisfatte determinate condizioni specificate.

> ► *Questo modificatore SigHash SIGHASH_ANYPREVOUT deriva dall'idea di SIGHASH_NOINPUT inizialmente proposta da Joseph Poon nel 2016 per migliorare il suo concetto della Lightning Network.*