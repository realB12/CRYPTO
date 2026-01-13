# Remote Procedure Call (RPC) Kommandos für BitCoinCore (BCore)

* [Offizielle und vollständige RPC Dokumentation](https://developer.bitcoin.org/reference/rpc/index.html#)

* **[BitCoinCore FullNode](../_BitCoinCore-FullNode.md)**: Eine **Uebersicht was BitCoinCore ist** und wofür man einen eigenen Knoten verwendet: 

---

In diesem Verzeichnis kommentiere ich **die für mich momentan wichtigsten RPC-Calls** mit denen man direkt entweder aus dem Windows-Kommandofenster mittels [bitcoin cli](../bitcoin-cli.md) oder in der eingebauten Konsole des GUIs ([bitcoin qt](../bitcoin-qt.md)) auf den mit BitCoinCore (BCore) lokal installierten und aktiv gestarteten resp. im Hintergrund laufenden Bitcoin Knoten resp. den BitCoinCore Daemon zugreifen kann. 

## JSON-RPC Introb
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
Momentan weiss ich nicht ob wir hier von irgendwelchen standardisierten RPC calls reden. 

Mir scheint es so, als würden wir hier einfach ein paar JSON-Objekte beschreiben die an den BitCoinCore-Server gesendet werden: 

![RPC Calls](./zPIC/RPC%20Calls.png)

### Parameter

#### host:  
"WalletULR" nach dem Schema: '**http://** serverAdresse **:** PortNummer **/wallet/**' Wallet_Name

Für den überlicherweise lokalen Aufruf ist es die Standardadresse 127.0.0.1 ansonsten eine remote Netzwerkadresse oder eine Server URL. 

Die Portnummer hängt von der verwendeten Chain up: regTest ist normalerweise auf Port 18443

Under der WalletName ist der Name der Wallet wie sie in BCore GUI angezeigt wird.

#### methos:  
immer 'POST'

#### headers:



* **host**: für lokalen Aufruf "http://127.0.0.1:18443/







