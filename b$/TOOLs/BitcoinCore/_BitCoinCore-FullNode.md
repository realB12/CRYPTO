# BitCoin-Core (BCore) SPE Doc für Enduser

> [CRYPTO/**b$/TOOLs/BitCoinCore**-Verzeichnis]
---

**Bitcoin.org OriginalQuellen**

* [BCores **offizielle Webseite**](https://bitcoincore.org/)  

* [Libra BitcoinChat](https://web.libera.chat/#bitcoin)

* [UserInterface](https://bitcoin.org/en/bitcoin-core/features/user-interface)  

**eigene BCore Docs**
* [BitCoinCore **Installationsanleitung**](BitCoinCore-installieren.md): wie man sich auf dem lokalen Rechner einen eigenen Full-Node instlalliert. 

* [BitCoinCore Functionality](FUNC/_BitCoinCore%20Functionality.md): BCore Funktionalität aus Benutzersicht


**SoftwareEntwicklung**: 

* [EntwicklerInfos](../../DEV/_EntwicklerInfos.md): Programmieranleitungen auf Basis der hier beschriebenen CryptoTools. 

* Lokale [BCore Development Setup](BitCoinCoreDevelopmentSetup.md) konfigurieren

* [BCore Dateisystem](BCore_FileSystem.md): was ist wo

* [bitcoin cli](bitcoin-cli.md): Kommandozeilen Tool

* [bitcoin qt](bitcoin-qt.md): die GUI-APP

* [bitcoind](bitcoind.md): der BCore-Server

* [RPC-Kommandos für BitCoinCore](RPC-Calls/_RPC-Kommandos%20für%20BitCoinCore.md)

* [Github: Original Entwickler Docs](https://github.com/bitcoin-dot-org/developer.bitcoin.org)

* [Original Bitcoin.org Developer-Page](https://developer.bitcoin.org/devguide/index.html)  

---

**SPE Doc zum Thema BitCoinCore**. In diesem Dokument beschränken wir uns primär auf eine reine Benutzersicht. Auf Technische Docs und Docs für Entwickler wird obenstehend in der Linkliste verwiesen.

---

## Was ist ein BitCoin Core Full-Node?

## I. Technische Sicht
    
### Technisch Abstrakt
Eine auf dem lokalen PC BitCoinCore-Instanz (entweder von der Taskleiste als GUI- ([bitcoin qt](bitcoin-qt.md)) oder in einem Windows-KommandozeilenScreen als DAEMON ([bitcoind](bitcoind.md) gestartet - beide parallel nicht möglich), ist ein gleichberechtigter, aktiver Knoten DES dezentral verwalteten Bitcoin Blockchain Netzwerks (genau das Milliardenschwere Netz, von dem alle reden!), welcher sofort versucht sich von nun an laufend im Hintergrund mit diesem Netzwerk zu synchronisieren und deshalb unmmittelbar nach dem Start beginnt, sich laufende mit (bis zu 10) anderen Knoten zu vernetzen und Daten auszutauschen und zu verifizieren.

Im BCore-Kontext können nun interaktiv im GUI oder via im GUI eingebauter Konsole oder in der Windows Kommandozeile Wallets erstellt oder BitCoin Informationsabfragen und Transaktionen getätigt werden, die DIREKT und damit sehr schnell mit dem lokal laufenden Knoten interagieren. 

[Wallets](../../GLOSSAR/W/Wallet.md) sind dabei diejenigen Objekte mit denen man nicht nur konkret mit Blockchains interagiert (resp. man sich mit den in der Wallet gespeicherten Privaten umd Public-Keys Zugang zur Chain verschafft), sondern suchen als eine Art Filter sich aus den permanent anrollenden Transaktionsdaten die zur Wallet passenden heraus. 

Zudem kann BCore mittels entsprechender Optionen/Eingabeparameter beim Start auch mit adhoc erstellten, lokalen TestNetzen verbunden werden, um so - entkoppelt von der Life Chain - verschiedene Dinge (Abfragen, Wallets, Transaktionen, etc.) zu testen ohne damit irgendwo Schaden anzurichten. 

### Dokumentation 
Die BitcoinCore-Dokumentation ist leider über drei verschiedenen Orte verteilt: 
1. Bitcoin Core App Beschreibung, 
2. dem Bitcoin Wiki, 
3. auf der Webseite von Bitcoin.org wie folgt: 

#### BitcoinCore Docs 
Das [GitHub Docs Verzeichnis auf developer.bitcoin.org](https://github.com/bitcoin-dot-org/developer.bitcoin.org) richtet sich vor allem an Entwickler und Test und weniger an Enduser.

#### Bitcoin Wiki
The [Bitcoin Wiki](https://bitcoin.org/en/bitcoin-core/contribute/documentation#bitcoin-wiki)
uses the popular MediaWiki software

#### Bitcoin.org RPC/REST API Reference
The [Bitcoin.org developer reference](https://developer.bitcoin.org/) contains over 100 printed pages worth of documentation for the Bitcoin Core RPC and REST interfaces, which are mainly used by Bitcoin Core command line users and developers of apps depending on Bitcoin Core.

#### Bandwidth Sharing Guide
The [Bitcoin.org bandwidth sharing guide](https://bitcoin.org/en/full-node) currently provides instructions for how to install Bitcoin Core on multiple operating systems, configure it to automatically start at boot, and manually open port 8333 so it accepts incoming connections.


## II. BenutzerSicht
Mit BitcoinCore (im Folgenden kurz BCore genannt) kann mittels Benutzeroberfläche einfach eigene Wallets erstellen und verwalten, BTC überweisen und in einer eigenen Konsole auch noch spezifischere Kommandos ausführen.  

Zudem unterstützt der BCore-Server-Dienst auch externe Lightweight Wallets. 

![BCoreUI](./zPIC/BCoreUI.png)

> <span style="color:red; font-weight:bold">ACHTUNG</span>:: you only get the security and privacy benefits in supported lightweight wallets if they make a secure and private connection to your Bitcoin Core every time you use them. This usually requires special configuration!

### Funktionalität der grafischen Benutzeroberläche 
#### Konto-Uebersicht
In der Uebersicht werden, sobald dein Konto eingerichtet ist, dein aktueller Kontostand, sowie deine letzten Transaktionen angezeigt. 

#### Fee-Slider
Hier kann man Kosten (low fees) versus Ausführungszeit (fast confirmation) selber einstellen

#### Coin Control
Mehr Privacy und tiefere Fees durch manuelle Auswahl der an einer Transaktion beteiligten Tokens.

#### QR Codes
QR-Codes für das Empfangen von Bitcoins

#### Invoicing
Uebersicht wer dich wann bezahlt hat

#### Proxy
verwende TOR oder einen Proxy um deine Identität besser zu schützen

#### NetzMonitoring
Ueberwachung der von dir beanspruchten Netzkapazität

#### WatchOnly support  
Verwalten von Offline gespeicherten Coins -> Cold Wallets


### Funktionalität der GUI-Konsole
Die BCore GUI/Bentuzeroberfläche enthält eine eigene Konsole, wo man sämtliche durch BCore zur Verfügung gestellten API-Kommandos ausführen kann. Im Gegensatz zur Kommandozeilen-API verfügt die eingebaute Konsole um eine automatische AutoComplete-Funktion was Eingabefehler verhindert. Zudem hat man mit der GUI-Konsole auch alles zur Hand was man braucht, resp. kann man sich die Auswirkungen der Kommandos dann auch im GUI bestätigen lassen. 

Diese Kommandos werden im [Doc "RPC-Kommandos für BitCoinCore" ](RPC-Calls/_RPC-Kommandos%20für%20BitCoinCore.md) beschrieben während man im Dokument ["EntwicklerInfos"](../../DEV/_EntwicklerInfos.md) Tips und Tricks zur generellen BitCoin-Entwicklung findet. 



