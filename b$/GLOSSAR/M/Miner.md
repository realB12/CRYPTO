# Miner

* [Difficulty Adjustment](../D/Difficulty-Adjustment.md)
* [Hashrate](../H/Hashrate.md)

Ein Miner füllt im Rahmen des [Minings](Mining.md) einen provisorischen Block mit den Daten pendenter, von ihm "handverlesener" Transaktionen. 

Wenn es ihm gelingt, durch Verändern der Nonce einen Blockhash mit der  aktuell durchs System vorgegebene Anzahl führender Nullen zu erzeugen, wird dieser Block zum nächsten gültigen Block der Blockchain. 

Damit erhält der Miner einerseits eine (alle vier Jahre halbierte) Anzahl Bitcoins für das Minen plus sämtliche [Tansaktionsgebühren](../T/Transaction/TransactionFee.md) aller im Block zusammengefassten Transaktionen. 

Deshalb wählen Miner Transaktionen mit den höheren Fees (die, notabene,  jeder Absender selber festlegt, resp. festlegen muss), und reichen Transaktionen mit zu wenig Fees immer wieder neu ans hintere Ende des MemPools Warteraums wo sie u.U. ewig stecken bleiben (bis man die Transaktionfee nachträglich mittels [RBF](../R/RBF.md)-Verfahren erhöht oder die Transaktion wieder löscht). 

1. A node is not always a miner.
2. A miner does not have to be a node.

A miner can simply connect to a full node to get the information they need to build a candidate block, and then send the block back to the full node when they're done.

Natürlich sitzt ein Miner grundsätzlich auch nicht - wie eine Bank - zwischen dem Absender und dem Empfänger einer Transaktion um eine Transaktion z.B. aus politischen Gründen zu sperren, und wenn dann sicherlich nicht anonym und damit so, dass sich der Betreffende für das Sperren verantworten müsste.  

> Theoretisch könnten natürlich sich sämtliche Miner dieser Welt zumsammentun, um eine bestimme Transaktion explizit NICHT in Blocks zu packen. Aber das ist so noch nie passiert und ist aus verschiedensten Gründen die wir hier nicht erläutern organisatorisch auch kaum machbar. Zum Beispiel ist es kaum möglich innerhalb der nächsten 10 Minuten bis zum nächsten Block eine Transaktion a) soweit zu analysieren und b) SAEMTLICHE nächsten Miner im Pool zu überzeugen damit sie zur selben Conclusion kämen. Und wenn das so wäre, dann hätte halte die Mehrheit des Netzwerks in diesem Sinne eines normalen, demokratisch gefällten Consensus im Interesse ALLER genau so  entschieden. 
