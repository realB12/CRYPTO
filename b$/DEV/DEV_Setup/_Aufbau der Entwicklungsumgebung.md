# Aufbau der Crypto Entwicklungsumgebung

* [BitCoinCore **Installationsanleitung**](BitCoinCore-installieren.md)

* [BitCoin Buch Kapitel 3 zum Thema Entwicklungsumgebung](https://cypherpunks-core.github.io/bitcoinbook/ch03.html)

Diese Anleitung für Entwickler führt durch den Aufbau einer Entwicklungsumgebung für Bitcoin Apps.  

## 1. BitcoinCore-Konten lokal installieren
Siehe hierzu die dafür in einem eigenen Dokument erstellte -> **[BitCoinCore Installationsanleitung](BitCoinCore-installieren.md)**. 

Beachte dabei, dass die Installation, resp. die Synchronisation mit der Blockchain TAGE dauern kann und entsprechende Hardware und Connectivity vorraussetzt. Details dazu in der **[ Installationsanleitung](BitCoinCore-installieren.md)**. 

## 2. BitCoin Daemon starten

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
Um einerseits auf der Life-Chain keinen Schaden anzurichten oder echtes Geld zu verlieren und andererseits um beim Testen nicht in Echtzeit 10Minuten und mehr warten zu müssen, erstellen Entwickler auf ihren eigenen lokalen Maschinen, fix von der [_BitCoinCore Software ](../../TOOLs/BitcoinCore/_BitCoinCore-FullNode.md) zur Verfügung gestellte Testnetzwerke wie z.B. regtest (Testnet3) oder testnet4. 

Bei denen ist z.B. die Difficulte zum Minen neuer Blocks defaultmässig 0 und das Mining bleibt deshalb dann auch sehr schnell. 



