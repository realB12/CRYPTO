# BitCoinCore Entwickler Setup

* [BitCoinCore installieren](BitCoinCore-installieren.md)

---


Im folgenden erläutere ich **wie wir die GUI-Konsole in den für Entwickler benötigten RegTest-Modus schalten** resp. wir wir damit lokale **eine rein private, nicht synchronisierte und damit leere Test-Blockchain erstellen**. 


## 1. GUI in den Entwicklermodus switchen
Nachdem man BitCoinCore gem. [Installationsanleitung](BitCoinCore-installieren.md) installiert hat, kann man das **GUI in den EntwicklerModus switchen** indem man die ***bitcoin.conf*-Datei** (bei mir aktuell im *D:\@ME\DATA\BitcoinBlockchainData* Verzeichnis) **mit folgenden Werten überschreibt**:


```plaintext
regtest = 1
server = 1
txindex = 1
```
> Details zu diesen **Optionen findet man in meiner [bitcoin.config Beschreibung](bitcoin.config.md)**

> Den **aktuellen Pfad** für die bitcoin.config KonfigDatei erhält man indem man im GUI auf "**Settings**" -> "**Options**" und dort auf dem  Button **[Open Configuratoin File]** klickt. 

Nach einem **Restart** des BitCoin GUIS (ACHTUNG: nicht mit dem in der Windows Konsole mit bitcoind gestarteten Daemons verwechseln, der nach wie vor auf das "main"-Netz zeigt) erscheint nun an Stelle des orangen Startschirms (main-Netz) ein blauer, resp. **zeigt das GUI oben links nun ein BLAUES Icon**. 

Die dabei aufpoppenden OutOfSync Warnung beim Starten einfach wegklicken!

## 2. Eine Wallet erstellen
* Im Menu des GUIS "**File**" wählen und darin -> "**Create Wallet**"
* Ich nenne sie "***myTestWallet***"

## 3. GUI Kommandozeilen Konsole
Im Folgenden sollte man die Konsole des GUIS verwenden: Ctrl+T (T für Terminal) oder über das Menu "Windows" -> "Console". Diese GUI Konsole bietet in der Kommandozeile eine Eingabehilfe für bitcoin-Komandos. 

Ausserdem muss man in dieser Konsole auch nicht bitcoin-cli voranstellen. 

<span style="color:red; font-weight:bold">ACHTUNG</span>:die WindowsKonsole läuft i.d.R. immer noch gegen das mit "*domaind*" defaultmässig gestartete "main" Netzwerk!

## 4. RegTestnetz testen
Mit der Eingabe von 

> getblockchaininfo

erhälte man den folgenden Output

```plaintext
{
  "chain": "regtest",
  "blocks": 0,
  "headers": 0,
  "bestblockhash": "0f9188f13cb7b2c71f2a335e3a4fc328bf5beb436012afca590b1a11466e2206",
  "difficulty": 4.656542373906925e-10,
  "time": 1296688602,
  "mediantime": 1296688602,
  "verificationprogress": 1,
  "initialblockdownload": true,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000000002",
  "size_on_disk": 293,
  "pruned": false,
  "warnings": [
  ]
}
```

Wichtig ist hier, **dass wir bei "chain" den Wert "regtest" stehen haben** um so sicher zu gehen dass wir nicht auf der life-chain sind. 





