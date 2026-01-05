# bitcoin-cli

* [BitCoinCore installieren](BitCoinCore-installieren.md)

## Was ist die BlockChain CLI?

Bitcoin-cli ist das mit dem [BitCoinCore FullNode](_BitCoinCore-FullNode.md) mitinstallierte KommandozeilenTool zum Ausführen von die lokale Blockchain betreffenden Kommandos wie das Auslesen gewisser Daten, Erstellen neuer Schlüssel etc. 

## Starten
### 1. CMD-Fenster
Unter Winows 11 mit "***CMD***" ein schwarzes Control-Fenster öffnen und das Tool mit folgenden Kommando starten: 

> bitcoin-cli

Dieses Kommando listet die Syntax und eine Kurzbeschreibung sämtlicher Parameter/Optionen, resp. prüfst Du so, ob das Tool überhaupt installiert ist. Falls nicht gehe zurück zur [BitCoinCore Installationsanleitung](BitCoinCore-installieren.md)

### 2. den BitCoin Daemon starten
Mit 
> bitcoind
Startest du den Daemon den Du wieder mit Ctrl+C beenden kannst

Falls Du ihn versuchst nochmals zu starten erhältst du eine etwas irreführende Meldung dass des Tool keinen Zugriff auf ein Verzeichnis hätte (was zwar stimmt, aber nicht auf den expliziten Mehrfachstart des Deamons verweist). 

## BlockchainInfo
Mit 

> bitcoin-cli blockchaininfo 

erhält man den Status des lokal laufenden Bitcoin Daemons. Falls dieser nicht gestartet wurde erhält man eine Meldung dass der Server nicht gefunden wurde: 

    "bitcoind server is running and that you are connecting to the correct RPC port."

