# Das Bitcoin Core DateiSystem

* [Dok zum BCore Dateisytsem auf GitHub](https://github.com/bitcoin/bitcoin/blob/master/doc/files.md)

----

## Inhalt
Im Folgenden beschreibe ich das von BitCoinCore verwendet Dateisystem. 

Dieses wird von allen drei BCore-Komponenten (GUI ([bitcoin qt](bitcoin-qt.md)), Daemon ([bitcoind](bitcoind.md)) und Kommandozeilentool ([bitcoin cli](bitcoin-cli.md)), gleichermassen verwendet. 

#### Out of Scope
> Nebst dem hier beschriebenen DATEN-Verzeichnis sind für den Betrieb auch noch Installationsverzeichnis und das Verzeichnis mit den Dokumentationen relevant - auf die wir hier aber nicht eingehen werden und verweisen hier auf die [BitCoinCore Installations Doku](BitCoinCore-installieren.md). 

> Wir gehen hier **nur auf Windows** ein

## Zusammenfassung
* **Installationsverzeichnis**: C:\me\TOOLS\BitcoinCore\bitcoin-28.1
* **DEFAULT DATEN-Verzeichnis**: C:\Users\RealB12\AppData\Local\Bitcoin
* **Customized DATEN-Verzeichnis**: D:\@ME\DATA\BitcoinBlockchainData

## Installationsverzeichnis
Das sogenannte Installationsverzeichnis (aktuell auf **C:\me\TOOLS\BitcoinCore\bitcoin-28.1**) ist dasjenige Verzeichnis, worin man die BitCoinCore-App heruntergeladen, entpackt und installiert hat und von wo die drei Komponenten 
1. GUI ([bitcoin qt](bitcoin-qt.md))

2. Daemon ([bitcoind](bitcoind.md)) und 

3. KommandozeilenTool ([bitcoin cli](bitcoin-cli.md)) 

gestartet werden. 

Dieses Verzeichnis darf somit nicht gelöscht werden und wird als einziges bei einem Update der BitCoinCore-App upgedated, resp. enthält es keine BlockchainDaten.

<span style="color:red; font-weight:bold">ACHTUNG</span>: Die ***[bitcoin.config](bitcoin.config.md)*** Konfigurationsdatei ist nicht hier, sondern ebenfalls im nachfolgend erläuterten DATEN-Verzeichnis. 

Im folgenden die **Liste der von BitCoinCore im Installationsverzeichnis installierten Dateien:**

Aktuell liegt mein Installationsverzeichnis auf folgendem Pfad

> **C:\me\TOOLS\BitcoinCore\bitcoin-28.1**

### root
* **README.md** oder **readme.txt**:Project information and instructions
* **bitcoin.conf	Generated configuration file

### /bin
Das /bin Verzeichnis enthält die ausführbaren Programme für Bitcoin Core's GUI, Kommandozeile, Daemon u.a.

* **bitcoin-cli**: Das Kommandozeilentool mit dem man einen laufenden [bitcoind Daemon/Server ](bitcoind.md) über RPC-Calls ansteuern kann.

* **[bitcoin qt](bitcoin-qt.md)**: Bitcoin Core GUI App die im Main-Modus mit einem Orangen und im Testmodus mit einem blauen Icon angezeigt wird  

* **bitcoin-tx**: Tool for creating and modifying transactions

* **bitcoin-util**: Miscellaneous utilities

* **bitcoin-wallet**: Bitcoin wallet tool

* **[bitcoind](bitcoind.md)**: Bitcoin Daemon/Server der nur über die [bitcoin cli](bitcoin-cli.md) angesprochen werden kann und nicht parallel zur GUI auf dieselben Daten zugreifen kann. 

### /lig
libbitcoinkernel.so**: 	Shared library containing core consensus and validation code
lib/pkgconfig/libbitcoinkernel.pc**: 	Pkg-config metadata for linking to libbitcoinkernel

### /libexec
* **bench_bitcoin**: 	Benchmarking tool for measuring node performance
* **bitcoin-chainstate**: 	Tool to validate and connect blocks
* **bitcoin-gui**: 	IPC-enabled alternative to bitcoin-qt
* **bitcoin-node**: 	IPC-enabled alternative to bitcoind
* **test_bitcoin**: 	Unit test binary
* **test_bitcoin-qt**: 	GUI-specific unit tests

### /share
* **man/man1/**: 	Man pages for command-line tools like bitcoin-cli, bitcoind, and others
* **rpcauth/**: 	Documentation and scripts for RPC authentication setup

## DATEN-Verzeichnis (Standard)
Die standardmässige [BitCoinCore Installation](BitCoinCore-installieren.md) speichert unter Windows 

1. Die ***[bitcoin.config](bitcoin.config.md)*** Konfigurationsdatei

2. sämtliche zu synchronisierende BlockchainDaten im folgendem **Standard DatenVerzeichnis**: 
> %LOCALAPPDATA%\Bitcoin

In meinem Fall im Verzeichnis

> **C:\Users\RealB12\AppData\Local\Bitcoin**

Dieses umfasst nach vollständiger Synchronisation (Stand 2025) ungefähr **130 GigaByte (GB)**

**Tip**: Das aktuelle Bitcoin DatenVerzeichnis findet man mit dem Kommando: > *echo %LOCALAPPDATA%\Bitcoin*

Im Default Datenverzeichnis werden nebst der [bitcoin.config](bitcoin.config.md) Konfigurationsdatei auch die "MAIN"-Net Daten für die Synchronisation mit der LifeBitcoinBlockchian gespeichert, während die Daten für Non-Main-Netze in jeweils eigenen Unterverzeichnisssen (/testnet, /regnet, ...) gespeichert werden.

### Alternativer Datenpfad
Mittels ***-datadir Parameter*** kann man jedes der 3 Tools in einem alternativen Verzeichnis starten. Sofern dieses nicht vorhanden ist, wird es neu erstellt und der Synchronisationsprozess mit der "main"-Chain sofort von Grund auf neu gestartet (-> IBD (Initial Blockchain Download))!

Entsprechend sorgfältig ist dieser ***-datadir Parameter*** zu verwenden. Zusätzlich sollte man, falls man nicht defaultmässig das "main"-Netz verwenden will (um damit die Daten direkt ins /Bitcoin Wurzelverzeichnis zu schreiben) beim Starten auch die Parameter für die entsprechenden [alternativen **Test-Netze](#test-netze)** angeben

## Test-Netze
Defaultmässig synchronisiert sich BitCoinCore nach der Installatino automatisch mit der Life Bitcoin-Blockchain deren Daten im Wurzelverzeichnis des DATEN-Verzeichnis gespeichert werden.

Daten für alternative Netze werden in jeweils eigenen SubVerzeichnisssen gespeichert: 

* **-chain=main / default**: synchronisiert die Daten der life BitCoin Blockchain ins /Bitcoin Wurzelverzeichnis

* **-chain=test resp. -testnet**: erzeugt im ***/testnet3*-Subverzeichnis** eine eigene, private und damit leere Blockchain.

* **-chain=regtest resp. -regtest**: 

* **-chain=signet resp. -signet**: 

* **-chain=testnet4 resp. -testnet4**: 

> <span style="color:red; font-weight:bold">ACHTUNG "Test"-Netz Inkonsistenzen</span>: während bei allen anderen Netzalternativen die NamingKonventionen für config, Kommandozeile und damit erstelltes SubVerezichnis identisch und damit logich sind, gibt es beim **-chain=test** Test-Netz **Abweichungen** (die man nicht begründen kann, aber wissen sollte): 
> 1. Im [bitcoin.config](bitcoin.config.md) lautet die Option: **-chain=test**
> 2. in der Kommandozeile hingegen: **-testnet**
> 3. das damit erzeuge Verzeichnis heisst **/testnet3** 

## Verzeichnisstruktur
Die folgenden Verzeichnisstrukturen für BitcoinCore-Daten-Verzeichnisse sind sowohl für das Main-Netz im Wurzelverzeichnis wie für die SubNetze in den entsprechenden Unterverzeichnisssen identisch. 

### /blocks
Zur Speicherung der Blocks der BitcoinBlockchian
Name und Location dieses Verzeichnisses können mit der ***-blocksdir* Option** (mit Ausnahme des *blocks/index/*-Verzeichnisses) verändert werden. 

Diese Blocks kommen als 2.dat Typen in den folgenden drei Varianten: 

1. **blkNNNNN.dat**: Die aktuellen, 128 MiB grossen Bitcoin Blöcke im BitCoin NetworkFormat

2. **revNNNNN.dat**: Block undo data (custom format)

3. **xor.dat**: für rolling XOR pattern for block and undo data files

<span style="color:red; font-weight:bold">ACHTUNG</span>:Versuche nicht diese *.dat files mit einem Tool zu öffnen weil es wegen der grossen Datenmenge zu lange dauern könnte um "nur" mal schnell reinzusehen! 
 
> **Anmerkung zu "MiB"** (Mebibyte): Ein MiB sind genau 1,048,576 bytes (resp. 1024 KiloBytes). Die Verwendung der 2er-Potenz ist im Digitalen Umfeld genauer als die Verwendung von MBs (Megabytes), welche 1,000,000 bytes (decimal) entsprechen.

#### /blocks/index
In diesem Verzeichnis befindet sich der sogenannte BlockIndex in der Form von auf diverse **.ldb* (die einfachen Key/Value-Liste), **.log* und andere Dateien aufgeteilte [LevelDB](https://github.com/google/leveldb). Diese Files sollten niemals verändert oder mit Tools bearbeitet werden!

Dieses Verzeichnis kann mit der ***-blocksdir* Option** nicht verändert werden resp. bleibt dieses Verzeichnis durch die ***-blocksdir* Option** unberührt!

#### /chainstate
[LevelDB](https://github.com/google/leveldb) Dateien für die Abbildung des aktuellen Blockchain States (a compact representation of all currently unspent transaction outputs (UTXOs) and metadata about the transactions they are from)

#### /indexes
In diesem Verzeichnis findet man die z.T. optionalen und erst mit gewissen Optionen aktivierten Indixes zum Schnelleren Auffinden gewisser Daten. 

* **/txindex**:   
Eine LevelDB für den **Transaktions-Index**. Dieses Verzeichnis existiert **nur mit gesetzter *-txindex=1* Option** was aber auch immer längere Synchronisationszeiten erfordert.

* **/blockfilter/basic/db**: Eine optionale LevelDB für den BlockfilterIndex für einfache Filtertypen falls die *-blockfilterindex=basic* Option eingeschaltet ist. 

* **/blockfilter/basic**: eine	fltrNNNNN.dat Datei für den BlockfilterIndex für einfache Dateitypen bei eingeschalteter *-blockfilterindex=basic* Option.

* **coinstatsindex/db**: Eine LevelDB für den CoinstatsIndex falls -coinstatsindex=1 gesetzt wurde.

#### wallets
Contains wallets; can be specified by *-walletdir* option; 
Falls das wallets Verzeichnis fehlt werden wallets direkt im DATEN-Verzeichnis gespeichert.
