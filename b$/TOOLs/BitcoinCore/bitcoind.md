# bitcoind - the BitcoinCore Package's Headless Daemon

* 
***bitcoind*** (mind the "d" at its end for Daemon) was the original, one and only BitCoin Core App before it got with *bitcoin-qt* an additional GUI on top and before (version 0.9) its commandline-interface (cli) was split into the *bitcoin-cli* app. 

Today ***bitcoind* is just the server-logic and code-base that is used by bitcoin-qt and bitcoin-cli** which are supporting and running an identical set of RPC-calles against it. 

However, **bitcoin-qt GUI runs bitcoind within its own process** and not by spawning a separate bitcoind process! Therefore you can launch the GUI without previously launching the  bitcoind daemon in the console. 

The bitcoin-cli - in contrast - depends on an already running bitcoind daemon which therefore needs previously to be launched in a separate/seconde Windows console before the bitcoin-cli commandline-tool can be used (otherwise it will respond with an error about "not being ab able to connect to the server).

One **cannot run the bitcoin-qt GUI and bitcoind Daemon upon the same data directory**, as they both are locking the database to prevent conflicts and bugs. However you can run them in paralle on different data directories (for instance to run the GUI for a testnet and the daemon for serious/real stuff). 

Both use the same bitcoin.conf configuration file by default, although some of Bitcoin-Qt's specific settings might be stored separately (e.g., in the system registry on Windows). 







## Setting the execution path

> bitcoind -datadir=/mnt/hdd2/Bitcoin/

Es ist super wichtig dass der Ausführungspfad auf das Verzeichnis mit der runtergeladenen/synchroniseirten Blockchain-Dateien zeigt. 

## Notizen
**Bitcoin-Qt does not launch its own separate bitcoind daemon**. Instead, the Bitcoin Core software package includes both bitcoin-qt (the graphical user interface, or GUI) and bitcoind (the headless daemon), but they run as distinct programs that both utilize the same underlying core libraries and share the same data directory. 