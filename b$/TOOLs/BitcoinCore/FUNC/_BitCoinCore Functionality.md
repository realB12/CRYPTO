# BitCoinCore Funktionalität

## Bitcoins an sich selbst überweisen
In der BitCoinCore Wallet ist es sehr einfach sich selber Bitcoins zu überweisen. 

1. BitCoinCore im richtigen Netzwerk (Life oder TestNetz) starten. 

2. Eine Wallet auswählen und sicherstellen dass sie Geld drauf hat (Available Balance). 

3. In der Konsole mit dem [***getnewaddress***](../RPC-Calls/G/getnewaddress.md)-Kommando eine neue "bcrt"-Adressse wie z.b. "*bcrt1qjpcyg4hlyux6wcvqgrjrc4kl6pwp29mftc5eta*" generieren, und diese in die Zwischenablage kopieren. 

4. Im Menu "SEND" wählen und das Formular wie folgt ausfüllen: 
![Bit Coin Zahlung Veranlassen](../zPIC/BitCoinZahlungVeranlassen.png)

**Parameter:** 

* **Pay To**: Eine mit ***bcrt..***. beginnende, hexadezimale Empfängeradresse, die man entweder vom Empfänger erhalten hat oder die man sich z.B. mit dem [getnewaddress](../RPC-Calls/G/getnewaddress.md)-Kommando (zu Testzwecken) selbst erstellt hat. 

* **Label**: freiwillige und rein persönliche Notiz zur Empfängeradresse die dann auch so in deinem persönlichen Transaktionsprotokoll erscheinen, aber nicht auf der Blockchain verbucht wird.

* **Amount**: Den zu überweisenden Betrag in wahlweise BTC oder Satoshis. Zudem kann man hier wählen ob die Transaktionsfees automatisch abgezogen weden sollen. 

* **Custom Transaction Fee**: Im Testsystem kann man hier was Beliebibes eingeben. 1000 Satoshisi haben sich hier als "normal" eingebürgert. 

5. Mit der Betätigung des **SEND-Buttons**, werden eine Sender- und eine andere Receiver- Transaktion mit jeweils identischem Betrag erstellt:  

Nach der Ueberweisung fehlen dann natürlich die Transaktionskosten im Konto (weil die Transaktion noch nicht auf die Blockchain geschrieben wurde, können die diesbezüglichen  Transaktionsfees auch noch nicht dem Miner gutgeschrieben werden). 

## Echte Bitcoin auf der RealChain senden
Wenn man Bitcoin auf der LifeBlockchain versenden möchte, dann ist das analog zu oben mit den folgenden Unterschieden: 
1. BCore im LifeModus starten (dabei erscheint as Icon organe, statt blau)
2. Sicherstellen dass Du eine gültige Empfängeradresse (Public Key des Empfängers) hast (verifiziere ob diese tatsächlich existiert)
3. Die Transactionfee kannst du zwar immer noch selbst bestimmen aber du bekommst aktuelle Fees vorgeschlagen 
4. Die Transaktion wird nicht gleich lokal ausgeführt sondern geht in den Mempool wo sie verifiziert und dann mal in einen neu zu erstellenden Block in die LifeBlockchian übernommen wird. 


 

