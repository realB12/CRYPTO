# Network Difficulty
Die Network Difficulty ist eine globale Metrik, die von der Bitcoin-Blockchain selbst festgelegt wird und den Schwierigkeitsgrad beschreibt, einen gültigen Block zu finden. Sie wird etwa alle 2016 Blöcke (etwa alle zwei Wochen) dynamisch angepasst, damit das Netzwerk im Durchschnitt alle 10 Minuten einen neuen Block generiert.

## Eigenschaften der Network Difficulty:
* **Global und für alle Miner gleich**:  Jeder Miner im Netzwerk muss sich an die aktuelle Network Difficulty halten, um einen gültigen Block zu finden.

* **Berechnung**: Die Difficulty ist proportional zur Zeit, die das Netzwerk benötigt hat, um die letzten 2016 Blöcke zu minen.

* **Formel**: Neue Schwierigkeit = Alte Schwierigkeit × (Zielzeit für 2016 Blöcke (10 Minuten) / Tatsächliche Zeit für 2016 Blöcke)

* **Beeinflusst den Mining-Prozess**: Eine höhere Network Difficulty bedeutet, dass Miner mehr Rechenleistung benötigen, um einen Block zu finden.

* **Ziel**: Die Blockzeit von 10 Minuten im Durchschnitt konstant halten, unabhängig von der Gesamt-Hashrate im Netzwerk.

* **Ausdruck in Zahlen**: Network Difficulty wird als eine große Zahl dargestellt, die das Verhältnis zwischen einem Ziel-Hash und dem maximal möglichen Hash beschreibt.

## Worker Difficulty
Die Worker Difficulty ist eine lokal von einem MiningPool festgelegte Schwierigkeit, die in Mining-Pools oder Solomining-Systemen verwendet wird, um zu bestimmen, wie schwer es für einen einzelnen Worker (einen Mining-Prozess oder -Gerät) ist, einen Share (einen Teilerfolg) zu finden.

### Eigenschaften der Worker Difficulty
* **Individuell anpassbar**: Die Worker Difficulty wird von einem Mining-Pool oder der Mining-Software festgelegt, um die Leistung einzelner Mining-Geräte zu berücksichtigen.

* **Ziel**: Ein gleichmäßiger Strom an Shares, unabhängig von der Rechenleistung des Miners.

* **Shares anstatt Blöcke:
Miner arbeiten mit einer lokal niedrigeren Schwierigkeit und reichen ihre gefundenen Shares an den Pool weiter. Der Pool aggregiert die Shares und arbeitet auf der Network Difficulty, um einen gültigen Block zu finden.

* **Warum gibt es Worker Difficulty?**
Unterschiedliche Miner haben unterschiedliche Hashraten. Ein Gerät mit geringer Leistung würde kaum Shares generieren, wenn es direkt mit der Network Difficulty arbeiten müsste. 

Daher wird die Worker Difficulty so angepasst, dass jedes Gerät regelmäßig Shares liefern kann.

* **Automatische Anpassung (Stratum-Protokoll)**:
Mining-Pools passen die Worker Difficulty dynamisch an (z.B. mit „vardiff“, variable difficulty), um sicherzustellen, dass ALLE Miner unabhängig von ihrer maximalen Hashrate ungefähr alle 5–10 Sekunden einen Share generieren.

* **Wert**: Worker Difficulty ist immer niedriger als die Network Difficulty, da sie für die lokale Rechenleistung optimiert ist.