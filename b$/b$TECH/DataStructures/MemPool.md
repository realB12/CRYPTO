# Mempool

-> [MemPool.space Webseite](https://mempool.space/de/) 

## Intro & Motivation sich mit dem MemPool zu befassen
Wie im Manual ["Warum Bitcoin schwer zu begreifen ist"](../../../1_INTRO/Warum%20Bitcoin%20schwer%20zu%20begreifen%20ist.md) erwähnt, scheint es mir wichtig, das Thema nicht nur Top-Down mit dem "Warum und Wofür Bitcoin überhaupt"-Ansatz zu erklären, sondern möglichst rasch auch aufzuzeigen, dass das "Ding" - auch wenn es Bitcoin als Münze oder greifbares Objekt nicht gibt - tatsächlich existiert, lebt und von jedermann öffentlich eingesehen werden kann. 

Der MomPool resp. seine visuelle Representation auf der [MemPool.space Webseite](https://mempool.space/de/) ist dafür ideal. 

## MemPool.space
Auf der [MemPool.space Webseite](https://mempool.space/de/) wir gloal JEDE aktuelle noch offene Transaktion (Generierung und Verschiebung von Bitcoins) in Form von wenigen Pixels angezeigt, resp. repräsentiert diese Bild die Summe dessen, was in genau diesem Moment Menschen rund um den Globus mit Bitcoins gerade so machen. 

![MemPool Screenshot](../zPIC/MemPool-Screenshot.png)

Diese Transaktionspixel lassen sich natürlich auf die einzelne Transaktion mit all ihren Details runterbrechen, resp. findest Du so immer auch DEINE Transaktion entweder in der Wertliste oder als Teil eines kürzlich erstellten neuen Blocks. 

> **ACHTUNG**: Das Erstellen eine (Daten-)Blocks und das Schürfen von Bitcoins (aus dem Nichts) haben zwar miteinander zu tun, sind aber zwei komplett verschiedene Dinge und dürfen nicht verwechselt werden (Auch wenn viele Medien und Einsteigerkurse fälschlicherweise suggerieren dass laufend Bitcoins an die BlockChain gehängt werden - obwohl es auch schon vom Namen her klar sein sollte, dass hier Blocks angehängt werden und keine Coins! 
> Respektive sind die damit aus dem Nichte generierten neuen Bitcoins der LOHN für die Erstellung des Blocks, aber nicht der Block selber.
> Ein **Block** ist lediglich ein neuer Datensatz der an das Ende der Blockchain gehängt wurde. 
> Der Blockminer (eine Einzelperson, eine Firma oder ein Verbund von beiden, die den DatenBlock als Erster an die Blockchain hängen durfte) erhält für das mit Strom- und Computerinfrastruktur-kosten erstellen des Blocks, resp. für das damit verbundene Lösen des dafür benötigten mathematischen Rätsels) eine gewisse Anzahl von Bitcoins (alle vier Jahre immer 50% weniger) in Form von neu aus dem Nichts erschaffenen Bitcoins plus Transaktionsgebühren in Form bereits bestehender Bitcoins welche ihm die Transaktionsbesitzer als Servicefee "überweisen") in sein persönliches Konto gut geschrieben.   

Und was sehen wir hier: 

### Oben: pendente (links) und erstellte (rechts) Blocks
Die Würfel im oberen Teil des Schirm repräsentieren die Blocks: rechts der Mitte die breits erstellten blauen Blocks mit ihrer Blocknummer (darüber) und links davon die auf ihre Fertigstellenden wartenden Blocks die je nach Auslastung der Blockchain resp. Anzahl der gesamhaft pendenten Transaktionen grün (wenig ausgelastet), gelb (mittle), orange (gut) und rot (überlastet) angezeigt werden. 

### Unten Links: wie sich der aktuelle Block mit Transaktionen füllt
Unten Links kann man live mitverfolgen wie sich **der aktuelle Block laufend mit Transaktionen füllt** (jede Transaktion (resp. ihre Transaktionsdaten) wird in einen Block gepackt der dann an die Blockchain gehängt wird). Dabei werden Transaktionen nicht nach dem Prinzip fist come first serve eingepackt sondern diejenigen mit den höchsten Transaktionsgebühren die der Transaktionsowner selber festgelegt hat. 

### Unten rechts: Minimale Transaktionekosten pro DatenMengenEinheit
Um in den aktuellen Block zu kommen, muss einer Transaktion immer eine minimale Transaktionsgebühr zugewiesen werden deren Höhe sich nach der Menger der an der Transaktion beteiligten Daten sowie der aktuellen Auslastung der Blockchain (grün, gelb, organge, rot) richten: Je mehr Transaktionen GLOBAL gleichzeitig anstehen, umso höher die Gebühren pro Transaktionen resp. der mit der Transaktion verbundenen Datenmenge (unabhängig davon wieviele Bitcoins damit überwiesen werden). 

> **ACHTUNG**: Die Transaktionskosten sind keine "Prozent" des übermittelten BitCoin-Betrages, sondern richten sich  
> a) nach der mit der Transaktion verbundenen Datenmenge (im Wesentlichen die Anzahl der für den Transaktionsbetrag benötigten UXOS) und  
> b) nach der aktuellen Auslastung des Blockchain-Netzwerkes durch seine Nutzer  
> <span style="color:red; font-weight:bold">
>Damit können die Transaktionskosten einer Transaktion den FIAT-Wert des transferierten (Klein)Betrags auch mal um dem Faktor 10 und mehr übersteigen!
</span>: 

Die Mindestgebühr wird in sat/VB angegeben. 

