# BitCoin Core installieren und testen

* ^- [Aufbau der Entwicklungsumgebung](_Aufbau%20der%20Entwicklungsumgebung.md)

* [Running a Full Node von Bitcoin.org](https://bitcoin.org/en/full-node)

* [Bit Coin Core Development Setup](BitCoinCoreDevelopmentSetup.md): BitCoin Core Konfiguration für Entwickler. 

* [bitcoind](bitcoind.md): Der im Hintergrund laufende BitcoinCore Server Dienst

* [bitcoin qt](bitcoin-qt.md): die Bitcoin Core Shell App

* [bitcoin cli](bitcoin-cli.md) das gegen den [bitcoind](bitcoind.md)-Server laufende Kommandozeilentool (für das Programmieren von Batchprogrammen)

* [BCore Verzeichnisse und Dateien](BCore_FileSystem.md)  

## 1. Hardware Setup
Die Installation von BitcoinCore kann u.U. Tage, ja sogar WOCHEN dauern wenn die Hardware dafür nicht mitmacht: 

1. **schnelle SSD-Disk mit mindestens 2TB**  (MUSS SSD sein, alles andere ist zu langsam, die 2TB nicht weil man die braucht, aber weil die Prozesse schneller laufen wenn genügend Platz auf der Disk ist und auch langfristig bleibt ohne dass intern dauernd Diskspace optimiert werden muss).   

2. **moderner Computer** mit genügend RAM und vernünftig schnellem Prozessor der auch mal ein paar Tage unter Vollast laufen kann (und dabei sehr heiss wird und deshalb gute Kühlung benötigt -> Laptops sind da eher weniger zu empfehlen).   

3. **Kein anderer Workload**: Während der Synchronisation ist es von Vorteil, wenn man sonst nichts am PC tut und er auch für nichts anderes verwendet wird. 

4. **Kein HochsicherheitsPC**: Da man während der Intstallation den Antivirus-Service abschaltet sollte es sich um KEINEN Hochsicherheits-PC handeln!!

5. **Schnelles Internet**: Dass man dafür ein stabiles und möglichst schnelles Internet benötigt, versteht sich von selbst - also nichts für unterwegs oder aus einem Hotelzimmer. Dass man nebenbei vielleicht nicht auch noch streamen sollte ebenfalls.  

## 2. BitcoinCore-App installieren

### Was installiert wird
BitcoinCore umfasst die folgenden "Tools": :

* **bitcoind**: Ein in der Windows Kommandozeile gestarteter Deamon(Service) (man beachte das  "d" am Ende des Kommandos) zur Valildierung von Transaktionen. 

* **bitcoin-cli**: das in der Winows-Console laufende Kommandozeilen-Interface (cli) für RPC-Calls gegen den zuvor gestarteten Daemon

* **bitcoin core qt**: Das Bitcoin Core GUI mit dem die Blockchain synchronisiert, Wallets installiert und verwaltet werden. 

Alle drei Komponenten werden über das die gleiche ***bitcoin.config* Datei** im ***C:\Users\RealB12\AppData\Local\Bitcoin*** Verzeichnis konfiguriert. 

### Installationsvorgang
1. **Download the latest version from https://bitcoin.org/en/download**

> Intern verwende ich für den Download das "C:\me\TOOLS\BitcoinCore"-Verzeichnis welches nach dem Download wieder gelöscht werden kann. 

2. **Unzip** the such downloaded files and **delete the *.zip-file** afterwards. 

3. Remove the **bitcoin-28.1-win64-folder** by moving its containing "**/bitcoin-28.1**"-folder into the BitcoinCore-Root folder and finally deleting the now emptied bitcoin-28.1-win64-folder (to reduce click- and typing-overhead) . 

4. **Antivirus anhalten**: Der Download würde mit eingeschaltetem Antivirus (nicht Firewall!) Jahre dauern. Deshalb habe ich den automatischen/realtime-scanning Antivirus ausgeschaltet. Ich denke das ist safe wenn ich während dieser Zeit darauf achte nichts runterzuladen und nur Vertrauenswürdiges zu klicken. <span style="color:red; font-weight:bold">ACHTUNG</span>: bei einem nächtlichen ComputerUpdate wird der Antivirus neu gestartet!! -> Jeden Morgen checken ob er wieder ausgeschaltet ist. 

4. Run ***bitcoin-qt.exe*** in the above created ..\TOOLS\BitcoinCore\bitcoin-28.1 folder with the following options: ![B T C Installation Options](./zPIC/BTCInstallationOptions.png) 

    * As the installation requires 620GB!! of free storage, I have put this on **a fresh external 2TeraByte SSD Drive in the *D:\@ME\DATA\BitcoinBlockchainData*-folder**  

    * I have **limited the final blockchain storage to 10 GB** (for 30 Days backup)  

    * When you **click "ok"** you will be asked to **open your firewall for external apps** to connect your computer: **say NO!** (You can open it later when you know what you are doing).  

    * **This downloads the entire history of Bitcoin transactions**: depending on the speed of your computer and network connection, the synchronization process can take hours to days.  
  
    * the following window tells you about progress and remaining download time: ![B T C Core Installation Progress](./zPIC/BTCCoreInstallationProgress.png)

5. **Ausführungspriorität von *bitcoin-qt.exe* erhöhen**: im Windows Taksmanager den BitCoin-Prozess anklicken. Mit Rechtsklick "Details" klicken und dort die **Priorität auf "*Hoch*" oder sogar "*RealTime*" setzen**. 

9. Antivirus wieder aktivieren! (Am besten durch einen Neustart der Maschine

**Tip**: die laufende **Synchronisierung kann jederzeit beendet werden** und mit einem **Neustart der bitcoin-qt.exe** Applikation wieder angestossen werden. Die Synchronisation läuft dann automatisch dort weiter, wo sie aufgehört hat. 

For this tutorial, **we'll use regtest mode—Bitcoin's built-in testing environment** where you're the only miner, blocks generate instantly, and you can experiment safely.

### Umgebungsvariable festlegen
Falls du *bitcoind.exe* starten möchtest und du die Fehlermeldung "*executionable not found*" erhältst, liegt es daran, dass du vermutlich zuerst den Pfad zu den bitcoin Apps festlegen musst. 

Mit dem Consolen-Kommando...

> echo %PATH%

...kannst Du den aktuellen Pfad checken. Falls der Bitcoin Pfad fehlt, musst Du ihn unter Windows 11 wie folgt hinzufügen: 

* In der Windows11 Suchzeile nach **"**edit sytem environment variables**" suchen.** 
![Environment Variables](./zPIC/EnvironmentVariables.png)
Dort mit [Edit...] den Path "C:\me\TOOLS\BitcoinCore\bitcoin-28.1\bin" hinzufügen: 

* Verifiziere den Eintrag indem Du in der Console den folgenden Command eingibst: 

## 2. BitCoin Daemon starten und testen

1. Starte den Bitcon Daemon im Regtest-Modus
* > bitcoind -regtest

**Tip**: Anders als in der offiziellen Doku vermerkt, kann muss man **unter Windows 11 den -daemon Parameter weglassten** weil man ansonsten die Fehlermeldung "-daemon is not supported on this operating system" erhält. 

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


## Verzeichnisse
Nach der Installation finden sicht BitCoin-Daten in den folgenden drei Verzeichnisssen (bei denen mir noch nicht klar ist, was genau sie enthalten). 

Detaillierte Infos zu den BitcoinCore Standardverzeichnissen findet man auf https://github.com/bitcoin/bitcoin/blob/master/doc/files.md

### Installationsverzeichnis
Dies ist das selbst gewählte Downloadverzeichnis mit den entpackten Executables zum Starten  die GUI-APP ([bitcoin-qt](bitcoin-qt.md)), dem Daemon/Server ([bitcoind](bitcoind.md)) und den Kommandozeilentools ([bitcoin cli](bitcoin-cli.md)) sowie der initialen (Muster) [bitcoin.config](bitcoin.config.md) Datei. 

> **C:\me\TOOLS\BitcoinCore\bitcoin-28.1**

Aktuell umfasste das Verzeichnis 94MB

### Default BitcoinCore DATEN-Verzeichnis
Bei der Installation werden auch dann, wenn explizit ein anderes Verzeichnis gewählt wurde, im folgenden Defaultverzeichnis massiv Daten (130GB) hinterlegt: 

> **C:\Users\RealB12\AppData\Local\Bitcoin**

Aktuell umfasste das Verzeichnis 127GB

Das aktuelle Bitcoin DatenVerzeichnis findet man mit dem Kommando

> %LOCALAPPDATA%\Bitcoin

-> [Details zu den darin enthaltenen Unterverzeichnisse](BCore_FileSystem.md)

### EXPLIZIT Gewähltes Datenverzeichnis
Das folgende Verzeichnis hatte ich bei der Installation von BitcoinCore als Defaultverzeichnis angegeben und ging davon aus, dass die Blockchain in dieses Verzeichnis geladen wird. War aber nicht der Fall.  

> **D:\@ME\DATA\BitcoinBlockchainData**

Aktuell umfasste das Verzeichnis 10 GB

Das aktuelle Bitcoin DatenVerzeichnis findet man mit dem Kommando

> %LOCALAPPDATA%\Bitcoin

Sowohl bitcoind als auch bitcon-qt können mit dem ***-datadir* Parameter** in einem neuen Verzeichnis starten (wobei dann automatisch wieder mit dem Synchronisieren der Blockchain begonnen wird!).


### Dokumentationsfiles
Die mit MarkdownMonster erstgellten Installations-  und Konfigurationsbeschreibung sowie UserGuides liegen bei mir im Verzeichnis: 

> **C:\me\REPO\CRYPTO\b$\TOOLs\BitcoinCore**

### Probleme mit Nicht-Default Verzeichnissen
When the Bitcoin Core data path is different from the default, the software MIGHT not automatically find its existing data (blockchain, wallet files, configuration, etc.) in the new location. This can lead to a variety of issues, including: 
1. Failure to load existing data: Bitcoin Core will start as if it were a fresh installation and begin the Initial Block Download (IBD) process from scratch in the default directory if you do not specify the new location!

2. Data directory conflicts: You may end up with data in two places (some in the default, some in the new path), leading to confusion or errors if only parts of the data are moved.

3. Wallet issues: If the wallet.dat file is in a different directory that isn't specified, the wallet will not load, and you will not see your funds or transaction history.

4. Configuration file problems: Bitcoin Core typically looks for the bitcoin.conf file in the default data directory. If the .conf file is in the new data directory, it might be ignored unless the new datadir is specified via command line argument or other specific settings. 

**How to Prevent Issues**:

To run Bitcoin Core from a non-default data path without issues, you must use the ***-datadir=<path>*** argument to specify the new location.  


## Konfigurations-Datei
Die bitcoin.config datei findet man IMMER im lokalen BitCoin-Datenverzeichnis **..\Users\RealB12\AppData\Local\Bitcoin**, notabene auch dann, wenn man bei der BitcoinCore Installation einen anderen Pfad eingegeben hat! (der nur für den Pfad der bitcoin.config Datei gilt sowie nachträglich installierte Test-NetzwerkDaten, aber, so wie es aussieht nicht für die Main-Blockchain). 



## Network Configuration
Beim Sart verbindet sich BitcoinCore automatisch mit 10 anderen FullNodes  (outbound connections), um die letzten Blocks und Transactions runterzuladen, und sich so auf den neusten Stand zu bringen. Das reicht, um den Knoten lediglich als Wallet und/oder Test- oder Schulungszwecken zu verwenden. 

### Port 8333 für Outbound Connections
Um aber AKTIVER Knoten im globalen Netzwerk zu werden und um damit mit eigenen Resourcen das BitCoin-Ding zu unterstützen, oder um LightWeight Clients zu unterstützen, müssen wir zusätzlich sogenannte **Inbound Connections** definieren, damit diese "von aussen" dediziert und kontrolliert auf unseren Knoten zugreifen können: Konkret müssen wir den Poert 8333 dafür öffnen: 


 
