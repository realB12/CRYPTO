# bitcoin-qt (the Bitcoin Core GUI) 

* [bitcoind](bitcoind.md)

die bitcoin-qt.exe im C:\me\TOOLS\BitcoinCore\bitcoin-28.1\bin Verzeichnis started einen darin implementierten, bit bitcoind CodeBase identischen Daemon/Server auf den über die GUI zugegriffen werden kann. 

Nebst über das Manü abrufbaren Funktionen bietet die GUI auch **eine eigene Konsole** auf der mit *bitcoin-cli* identische RPC Kommandos ausgeführt werden können (im Gegensatz zur *bitcoin-cli* bietet die bitcoin-qt eigene Konsole bei der Eingabe der RPC Calls **smarte Ergänzungshilfen**). 

Dafür lassen sich meines Wissens keine Batchjobs für die qt GUI schreiben. 

<span style="color:red; font-weight:bold">ACHTUNG</span>: Wenn Qt läuft kann man parallel dazu keine bitcoind Deamon starten der auf dieselben Daten verweist! Mehr dazu in der Beschreibung zu [bitcoind](bitcoind.md). 



