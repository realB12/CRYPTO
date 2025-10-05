# Difficulty Adjustment
* [Miner](../M/Miner.md) / [Mining](../M/Mining.md)
* [Hashrate](../H/Hashrate.md)
* [Target](../T/Target.md)
* [Nonce](../N/Nonce.md)  

Mit dem sogenannten "Difficulty Adjustment" verändert das BitCoin-Netzwerk automatisch nach 2016 Blöcken die Schwierigkeit für Miner den nächsten Block zu generieren, so dass auch weiterhin im Schnitt alle 10 Minuten, unabhängig von der Anzahl Miner und der globale verfügbaren Rechenpower, immer nur genau ein Block erstellt wird. 

Um den Zuschlag für das Minen eines nächsten Blocks zu erhalten, lösen Miner ein sogenanntes Blockrätsel, welches darin besteht, im Blockheader ein  "Nonce" benanntes Datenfeld solange zufällig zu mutieren bis der SHA-256 Hashwert des Blockheaders (inklusive der Nonce), vereinfacht gesagt,  eine gewisse Anzahl führender Nullen aufweist: Je mehr Nullen, umso schwieriger. (Technisch ausgedrückt muss der SHA-256-Hashwert des Headers kleiner als eine "[Target](../T/Target.md)" genannte 256-Bit Zahl sein. 

Wenn zum Beispiel Miner immer stärkere Computer einsetzen um damit schneller eine gültige Nounce zu "raten", dann werden maximal noch 2016 Blocks in diesem Schnellzugtempo erstellt. Ab dann stellt das System durch Anpassung der [Target-Zahl](../T/Target.md)aber dann bewirken, dass alle Miner ab dann eine oder zwei  zustäzliche Nullen generieren müssen, und damit natürlich einfach mehr Energie einsetzen müssen als davor während sich die Zeit wieder auf 10 Minuten einpendelt. 

Gleiches gilt wenn Energiekosten steigen und Minder deswegen aufgeben, die Zeit sich verlängert und deshalb bewirkt dass wieder nach maximal 2016 Blocks die Anzahl der Nullen reduziert wird um das "Raten" zu erleichtern. 

Weil Energie kostet, sind Miner gar nicht interessiert mehr Energie ins Minen zu investieren als sie - sofern sie dann auch den Zuschlag bekommen - mit der CoinBase und den Transaktionsgebühren verdienen würden. 

Dass sich die Geschwindigkeit mit der alle 10 Minuten ein neuer Block erstellt wird, durch diesen Automatismus die letzten 15 Jahre halten konnte, zeigt, wie genial dieser fix ins Netzwerkprotokoll eingebaute selbstregulierende / selbstheilende Algorithmus ist.