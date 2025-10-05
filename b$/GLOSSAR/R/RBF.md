# Replace By Fee (RBF) Verfahren
* [BTC TransactionFees](../../b$TECH/Fees/BTC_TransactionFees.md)
* [CPFP](../C/CPFP.md)-Verfahren

Mittels der in Wallets eingebauten RBF-Mechanismen **lassen sich Transaktionsgebühren einer Transaktion nachträglich erhöhen**. 

Zudem kann man eine **Transaktion über RBF auch ganz abbrechen**. 

## Intro
Die Transaktionsgebühren von Bitcoin passen sich stets an die aktuelle Nachfrage im Netzwerk an. Schließlich ist der Speicherplatz in den Blöcken auf 4 MegaByte begrenzt, und Nutzer müssen entsprechend, ähnlich wie bei einer Auktion, möglichst hoch bieten, um von den Minern bevorzugt zu werden.

Schnell kann es passieren, dass man die Transaktionsgebühr zu niedrig wählt, oder die allgemeine Nachfrage plötzlich so stark zunimmt, sodass man von anderen schnell überboten wird. 

Mittels den zwei Verfahren
1. "Replace By Fee" (RBF) oder 
2. ["Child Pays For Parent" (CPFP)](../C/CPFP.md)

kann man relativ einfach die Gebühr der Transaktion nachträglich erhöhen und damit die Bestätigung einer "feststeckenden Transaktion" beschleunigen. 
Diese Funktionen werden zwar (noch) nicht von allen Wallets unterstützt, aber es gibt diese Verfahren. Und damit sollte man sich nie wegen feststeckenden Transaktionen sorgen, oder aus Angst, stecken zu bleiben, unnötig überhöhte Transaktionsgebühren bezahlen!

## RBF
Die meistverbreitete Methode, um die Gebühr einer Transaktion zu erhöhen, hört auf den Namen Replace By Fee (RBF) und kann vom Sender der Transaktion durchgeführt werden.

Auch wenn es hier wiederum verschiedene Ansätze gibt, ist das Grundprinzip immer dasselbe: Die ursprüngliche Transaktion wird durch eine neue Transaktion mit einer höheren Gebühr "ersetzt". 

Wir erinnern uns: Solange eine Transaktion nicht bestätigt ist, hat sie nie stattgefunden, also wurden die entsprechenden Bitcoin auch noch nicht ausgegeben. Es spricht also nichts dagegen, eine komplett neue Transaktion zu veröffentlichen, welche versucht, die gleichen Bitcoin wie die Alte auszugeben. Denn durch die höhere Gebühr wird diese von den Minern stets bevorzugt und schneller bestätigt, während die alte Transaktion damit automatisch ihre Gültigkeit verliert.

### Opt-In RBF
Der bisher beliebteste Ansatz von RBF ist im BIP-125 definiert und eine komplett optionale Funktion, die also nur dann funktioniert, wenn der Sender der Transaktion dies explizit mit der ursprünglichen Transaktion angekündigt hat. Dieses RBF-Signal wird mittlerweile von den allermeisten modernen Wallets automatisch bei jeder Transaktion gesetzt und ist auch in vielen Blockchain-Explorern sichtbar.

Konkret muss für Opt-in RBF sowohl die Gebührenrate, also wie viele Satoshi man pro verwendeten Speicherplatz zahlt (sat/vB), als auch die absolute, also gesamte, Gebühr eintragen, die logischerweise höher als diejenige der ursprünglichen Transaktion sein muss (um den Miner zu motivieren, sie Transaktion nun bevorzugt zu behandeln). 

### Full-RBF
Ein weiterer Ansatz, der allmählich beginnt sich durchzusetzen, ist Full-RBF. Wie der Name schon andeutet, kann hier grundsätzlich jede Transaktion mit einer höheren Gebühr ersetzt werden, ohne dass dies vorher explizit signalisiert werden muss. Solange sich Full-RBF noch nicht vollständig etabliert hat, ist es aber trotzdem sinnvoll, weiterhin für RBF zu signalisieren, was die allermeisten Wallets ja ohnehin schon tun.

### Transaktionsabbruch mittels RBF
Mittels RBF kann man Transaktionen auch abbrechen – natürlich nur solange diese noch nicht bestätigt sind. 

Dafür unterscheidet sich die neue, ersetzende, Transaktion nicht nur in der höheren Gebühr, sondern auch im Empfänger: Anstatt an die ursprüngliche Adresse, sendet man die Bitcoin jetzt einfach an sich selbst, also an eine eigene Adresse.

Die Gebühr muss dementsprechend dennoch erhöht werden, denn ansonsten würde die neue Transaktion von den Minern nicht bevorzugt werden.


> <span style="color:red; font-weight:bold">Merkpunkt</span>:: **Auch ein Transaktionsabbruch kostet**!!