# Shares im Kontext von [Mining](../M/Mining.md)

Shares repräsentieren die Arbeitsleistung eines Miners innerhalb eines [Mining Pool](../M/MiningPool.md). 

Beim Mining versucht ein Miner, einen gültigen Block zu finden, der die von der Blockchain vorgegebene "Network Difficulty" erfüllt, resp. an Anfang eine vom Netzwerd dynamisch festgelegte Anzahl Nullen aufweist (Technisch: damit wird eine Zahl (die Nonce) gesucht deren Zahlenwert kleiner ist, als die die c repräsentierende Zahl).  

Da diese Schwelle sehr hoch ist, legt der Mining-Pools einen eigenen, niedrigeren Schwellenwert - sie sogenannte "**Share Difficulty**" - fest. Miner melden dann ihre Lösungen dieser einfacheren und damit häufigeren Share Difficulty an den Pool der sich dieser Meldungen in Form von den jeweiligen Minern zustehenden Shares merkt. 

Sobald einer der Pool-Miner die "Network Difficulty" löst und damit die CoinBase (aktuell 3.125 BTC) für den Pool gewinnt, werden diese BTC auf der Basis der dafür eingegangenen Shares an die jeweiligen Miner verteilt. 

**Beispiel:** 
Andy, Bruno und Claudio bilden einen Pool. 

Andy findet die Network Difficulty (mit 12 führenden Nullen) direkt nach 3 Minuten.

Bruno hat innerhalb dieser 3 Minuten zwei Lösungen für die Share Difficulty (mit 9 führenden Nullen) gefunden und an den Pool gemeldet.

Claudio mined zwar mit aber hat innerhalb dieser 3 Minuten keine Lösung für die Share Difficulty (9 Nullen) gefundenn. 

Die 3.125 BTC werden nun wie folgt verteilt: 

1. **Andy** erhält nur einen Drittel, also 1  BTC (obwohl ER die Network Difficulty gefunden hat). 

2. **Bruno** erhält zwei Drittel, also 2  BTC (obwohl ER die Network Difficulty NICHT gefunden hat). 

3. **Claudio** geht leer aus. 


**Zusammengefasst**: 
Miner generieren Blöcke die eine einfachere SHARE-Difficulty (weniger führende Nullen) erfüllen, bis jemand in globalen Netz die NETWORK-Diffculty erfüllt. 

Diese ShareDiff-Blöcke werden vom Pool gezählt, um die Arbeitsleistung des Miners in Form dafür ausgestellter Shares zu messen, um anschliessend, sollte der Pool die Network-Difficulty lösen, den Gewinn (Coinbase) anteilsmässig zu verteilen. 

Falls ein anderer Miner oder ein anderer MinerPool ausserhalb des eigenen Pools die Network Difficulty löst, erhält natürlich keiner was.

<span style="color:red; font-weight:bold">ACHTUNG</span>: Es ist deshalb wichtig, nicht nur die Share-Difficulty, sondern auch das Verhältnis von Network und Share-Difficulty zu kennen, um so abschätzen zu können, ob man als "Kleiner" in einem Pool überhaupt auch mal Shares generieren kann. 

Es empfielt sich, eine MiningPool-Platform zu wählen wo die Anzahl der eigenen Shares ausgewiesen und geloggt werden. 

### Rejected Shares
Shares die vom Miner zwar an den Pool übermittelt, jedoch nicht akzeptiert wurden, weil zB.

* euer Share eine zu geringe Difficulty aufweist (das Thema bei NerdMiner und Diff < 1)
* euer Share wegen hoher Latenzen zu spät eingereicht wurde und bereits ein neues Block Template verteilt wurde
* euer Share veraltet ist, dass heisst das zwischenzeitlich ein neuer Block gefunden wurde und dein Share somit auf einem veralteten Block Template erstellt wurde
* euer Share doppelt eingereicht wurde
* euer Share gegen Pool-Richtlinien verstösst (zB. blockt kano.is IP-Adressen von CPU-Miner)




