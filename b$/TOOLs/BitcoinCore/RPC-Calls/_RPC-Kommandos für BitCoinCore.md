# Remote Procedure Call (RPC) Kommandos für BitCoinCore (BCore)

* [Offizielle und vollständige RPC Dokumentation](https://developer.bitcoin.org/reference/rpc/index.html#)

* **[BitCoinCore FullNode](../_BitCoinCore-FullNode.md)**: Eine **Uebersicht was BitCoinCore ist** und wofür man einen eigenen Knoten verwendet: 

* [RPC Authentication](RPC%20Authentication.md)  

---

In diesem Verzeichnis kommentiere ich **die für mich momentan wichtigsten HTTP JSON-RPC-Calls für den BitCoin Core Server**. 

Damit kann man direkt entweder aus dem Windows-Kommandofenster mittels oder in der eingebauten Konsole des GUIs ([bitcoin qt](../bitcoin-qt.md)) auf den mit BitCoinCore (BCore) lokal installierten und aktiv gestarteten resp. im Hintergrund laufenden Bitcoin Knoten resp. den BitCoinCore Daemon zugreifen kann. 

## JSON-RPC Calls: ein Ueberblick
Mit [bitcoind](../bitcoind.md) wird immer auch ein HTTP JSON-RPC Server gestartet.  

Anderst als auf der Kommandozeilte mittels [bitcoin cli](../bitcoin-cli.md) oder in der GUI-Konsole [bitcoin qt](../bitcoin-qt.md) müssen RPC Calls mittels UserID und Passwort authentifiziert werden (da diese, obwohl nicht empfohlen, auch von ausserhalb der lokalen maschien erfolgen könnten). 

Hierfür kann man mit Hilfe des [Config-File Generator](https://jlopp.github.io/bitcoin-core-config-generator) einen Hash generieren den man wie folgt im BCore [bitcoin.config](../bitcoin.config.md) einfügt: 

> **rpcauth=Rene:3f57e7c5182e5aeb8f50b940025e982b$fd763f207b0722ae15b35b6d23f39ea1f97ffd1b58aeb13d9a6eff33ab2b3d26**

Details dazu findet man im [RPC Authentication Doc](../../../DEV/DEV_Setup/RPC%20Authentication.md)

If your HTTP or JSON library requires you to specify which 'realm' is authenticated, use 'jsonrpc'.

Bitcoin supports SSL (https) JSON-RPC connections beginning with version 0.3.14. See the rpcssl wiki page for setup instructions and a list of all bitcoin.conf configuration options.

Allowing arbitrary machines to access the JSON-RPC port (using the rpcallowip configuration option) is dangerous and strongly discouraged-- access should be strictly limited to trusted machines.

## RPC-Calls nach Thema

### Wallets

---

## Generischer JSON-RPC-Request
Alle JSON-RPC Calls sind alle nach demselben Prinzip aufgebaut die immer auf den gleichen Eingabedaten basieren. Lediglich die Formatierung, verwendeten Metazeichen, Datentypen und Feldnamen können sich von Programmiersprache zu Programmierstrache unterscheiden, sind aber in der Regel immer zuweisbar. 

![RPC Calls](./zPIC/RPC%20Calls.png)

### Parameter

#### host:  
"WalletULR" nach dem Schema: '**http://** serverAdresse **:** PortNummer **/wallet/**' Wallet_Name

Für den überlicherweise lokalen Aufruf ist es die **StandardAdresse für lokale Server = 127.0.0.1** ansonsten eine remote Netzwerkadresse oder eine Server URL. 

Die **Portnummer** hängt von der verwendeten Chain up: die regTest-Chain ist normalerweise auf Port 18443, kann aber im [bitcoin.config](../bitcoin.config.md) überschrieben werden.

Under der WalletName ist der Name der Wallet wie sie in BCore GUI angezeigt wird.

<span style="color:red; font-weight:bold">ACHTUNG</span>:Für Wallet-Namen sollte man aus Gründen der besseren Programmierbarkeit (StringHandling) möglichst einfache Namen ohne Spaces und Sonderzeichen verwenden!

#### methos:  
immer 'POST'

#### headers:
Im {headers]-Objekt muss man lediglich die beiden Eiträge für "*user*" und "*pass*" mit den initial erstellten [Authentication Credentials](RPC%20Authentication.md) ersetzen. 

Diese werden bei der Ausführung vom Server gehashed und mit dem entsprechenden HashWert in der  [bitcoin.config](../bitcoin.config.md)-Datei verglichen wird. 

#### body
Das {body}-Objekt enthält den eigentlichen Call

* **"jsonrpc: 1.0"**: Im Body Object bedeuted "jsonrpc: 1.0" dass die Version 1.0 der RPC Syntax verwendet wird. Mittlerweile gibt es auch eine Version 2.0. 

* **id**: das kann ein beliebiger String sein. Da diese id unverändert in der Response zurückgesendet wird, dient sie der Zuordnung der (asynchron eintreffenden) Response zum ursprünglichen/zugehörigen Call. 

* **method**: Der Name der RPC-Calls wie z.B. getnewaddress, gettransaction, ...

* **params**: Die Liste der Eingabeparameter in der Form eines Arrays. 












