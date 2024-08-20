---
term: CPFP (CHILD PAYS FOR PARENT)
---

Ein Transaktionsmechanismus, der darauf abzielt, die Bestätigung einer Bitcoin-Transaktion zu beschleunigen, ähnlich wie es Replace-by-Fee (RBF) tut, jedoch von der Seite des Empfängers aus. Wenn eine Transaktion mit zu niedrigen Gebühren im Vergleich zum Markt in den Mempools der Knoten stecken bleibt und nicht schnell genug bestätigt wird, kann der Empfänger eine neue Transaktion durchführen, indem er die in der blockierten Transaktion erhaltenen Bitcoins ausgibt, obwohl diese noch nicht bestätigt ist. Diese zweite Transaktion erfordert notwendigerweise, dass die erste abgebaut wird, um bestätigt zu werden. Miner sind somit gezwungen, beide Transaktionen gemeinsam einzuschließen. Die zweite Transaktion wird viel mehr an Transaktionsgebühren zuweisen als die erste, auf eine Weise, dass die durchschnittliche Gebühr die Miner dazu ermutigt, beide Transaktionen einzuschließen. Die Kind-Transaktion (die zweite) zahlt für die feststeckende Eltern-Transaktion (die erste). Deshalb wird es als "CPFP" bezeichnet.

CPFP ermöglicht es somit dem Empfänger, seine Gelder schneller zu erhalten, trotz der niedrigen anfänglichen Gebühren, die vom Sender verursacht wurden, im Gegensatz zu RBF (*Replace-By-Fee*), das es dem Sender ermöglicht, die Initiative zu ergreifen, um seine eigene Transaktion durch Erhöhung der Gebühren zu beschleunigen.