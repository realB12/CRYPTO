# Aufbau der Crypto Entwicklungsumgebung

* [BitCoinCore Installations- und Konfigurationsbeschreibung für Entwickler](../../TOOLs/BitcoinCore/BitCoinCoreDevelopmentSetup.md): Voraussetzung

* [RPC Programmers Reference](https://en.bitcoin.it/wiki/API_reference_(JSON-RPC)#Controlling_Bitcoin_Core): mit Mustercode für verschiedene Sprachen

* [BitCoinCore **Installationsanleitung**](BitCoinCore-installieren.md)

* [BitCoin Buch Kapitel 3 zum Thema Entwicklungsumgebung](https://cypherpunks-core.github.io/bitcoinbook/ch03.html)

* [RPC Authentication](RPC%20Authentication.md)

* [The Bitcoin Core documentation](https://github.com/bitcoin/bitcoin/blob/master/doc/JSON-RPC-interface.md#json-rpc-interface)

* [The Bitcoin Core RPC help for each call](https://bitcoincore.org/en/doc/)

* [The Bitcoin Core RPC error codes](https://github.com/bitcoin/bitcoin/blob/master/src/rpc/protocol.h)

* [Bitcoin Core RPC API version changes]( https://masonicboom.github.io/btcrpcapi/)

---

Diese **Anleitung für BitCoin Entwickler** führt durch die verschiedenen Möglichkeiten wie man die BitCoinBlockchain mit Programmierwerkzeugen direkt auslesen kann und wie man diese um eigene Blocks, Wallets und Transaktionen erweitern könnte. 

Das Ziel ist weder eigenes Mining noch die Weiterentwicklung, sondern **lediglich die Bitcoin-Technologie**

**1. auf der Basis des effektiven Codes und der öffentlich zugänglichen APIs im Detail zu verstehen so nach dem Motto: "Der Code lügt nie"**  

**2. Sie bestmöglich für eigene Ziele und Zwecke zu nutzen.** 

## Scope
Im Folgenden gebe ich **lediglich eine Uebersicht über die für die Entwicklung benötigten [Tools](../../TOOLs/_BitCoin_Tools.md)**. 

**Deren Funktionsweise, Installation, Konfiguration und Maintenance wird aber NICHT HIER, sondern in den jeweiligen Tool- und Servicebeschreibungen beschrieben!**

### BitcoinCore
Die meisten Programmierer werden vermutlich zuest mal BitCoinCore verwenden, um auf einer eigenen, lokal instlalierten TestChain mittels BitCoinCore Schnittstelle erste Gehversuche zu wagen. Hierzu bietet BCore ein mit [bitcoin cli](../../TOOLs/BitcoinCore/bitcoin-cli.md) ein Windows-KommandozeilenTool und innerhalb des [BCore-GUIS](../../TOOLs/BitcoinCore/bitcoin-qt.md) eine integrierte Konsole um mittels HTTP RPC-Calls Requests an den mit [bitcoind](../../TOOLs/BitcoinCore/bitcoind.md) in der Kommandozeile direkt oder indirekt mittels [BCore-GUIS](../../TOOLs/BitcoinCore/bitcoin-qt.md) gestarten BCore-Server zu senden. 

Eine Uebersicht zur Funktionalit, Installation und Konfiguration der BCore Entwicklungsumgebung findet man in den folgenden Docs: 

* [BitCoinCore FullNode](../../TOOLs/BitcoinCore/_BitCoinCore-FullNode.md): Intro und SPE Doc zum lokal installierten BitCoinCore FullNode. 

* [BitCoinCore installieren](../../TOOLs/BitcoinCore/BitCoinCore-installieren.md) wie man BCore ready-made für die Main-Chain installiert und mit der Life-Blockchain synchronisiert.

* [BCore Development Setup](../../TOOLs/BitcoinCore/BitCoinCoreDevelopmentSetup.md): wie man BCore für den Betrieb einer Test-Chain konfiguriert und startet. 


#### 1. BitcoinCore lokal installieren
Siehe hierzu die dafür in einem eigenen Dokument erstellte -> **[BitCoinCore Installationsanleitung](BitCoinCore-installieren.md)**. 

Beachte dabei, dass die Installation, resp. die Synchronisation mit der Blockchain TAGE dauern kann und entsprechende Hardware und Connectivity vorraussetzt. 

## 2. Credentials einrichten 
Anderst als auf der Kommandozeilte mittels [bitcoin cli](../bitcoin-cli.md) oder in der GUI-Konsole [bitcoin qt](../bitcoin-qt.md) müssen JSCON-RPC Calls zum mit [bitcoind](../../TOOLs/BitcoinCore/bitcoind.md) gestarteten BCoreServer mittels UserID und Passwort authentifiziert werden (da diese Calls, obwohl nicht empfohlen, auch von ausserhalb der lokalen Maschine erfolgen könnten).

Hierzu kann man sich im [Auth Generator](https://jlopp.github.io/bitcoin-core-rpc-auth-generator) auf der Basis einer adhoc gewählten UserID und eines Passworts (-> [_Credential Management](../../../../PRIV/_KEY/Admin/PW/_Credential-Management.md)) einen hexadezimal verschlüsselten Hash erstellen lassen den man ins wie folgt in die [bitcoin.config](../../TOOLs/BitcoinCore/bitcoin.config.md)-Datei einsetzt: 

![Passwortgenerator](./zPIC/Passwortgenerator.png)

Zum Beispiel generiert die UserID = Rene und das Passwort = Baron den folgenden Hash: 

> **rpcauth=Rene:3f57e7c5182e5aeb8f50b940025e982b$fd763f207b0722ae15b35b6d23f39ea1f97ffd1b58aeb13d9a6eff33ab2b3d26**


Details dazu findet man im -> [RPC Authentication Doc](RPC%20Authentication.md)

## 3. BitCoin Daemon starten

1. Starte den Bitcon Daemon im Regtest-Modus
* > bitcoind -regtest

**Tip**: Anders als in der offiziellen Doku vermerkt kann muss man unter Windows 11 den -daemon Parameter weglassten weil man ansonsten die Fehlermeldung "-daemon is not supported on this operating system" erhält. 

2. überprüfe ob der Daemon läuft
* > bitcoin-cli -regtest getnetworkinfo

Dies listet dir einen langen JSON-formatierten-Record mit allen wichtigen Parametern: 

```plaintext
{
  "version": 280100,
  "subversion": "/Satoshi:28.1.0/",
  "protocolversion": 70016,
  "localservices": "0000000000000c09",
  "localservicesnames": [
    "NETWORK",
    "WITNESS",
    "NETWORK_LIMITED",
    "P2P_V2"
    ....
  ]
}
```

**Pro tip**: Erstelle einen Alias damit du weniger tippen musst

* > alias bcli="bitcoin-cli -regtest"

Von nun an kannst du den Daemon einfach mit dem  *bcli*-Kommando starten

## Entwicklernetzwerke
Um einerseits auf der Main-Chain keinen Schaden anzurichten oder echtes Geld zu verlieren und andererseits um beim Testen nicht in Echtzeit 10Minuten und mehr warten zu müssen, erstellen Entwickler auf ihren eigenen lokalen Maschinen, fix von der [_BitCoinCore Software ](../../TOOLs/BitcoinCore/_BitCoinCore-FullNode.md) zur Verfügung gestellte Testnetzwerke wie z.B. regtest (Testnet3) oder testnet4. 

Bei denen ist z.B. die Difficulte zum Minen neuer Blocks defaultmässig 0 und das Mining bleibt deshalb dann auch sehr schnell. 



