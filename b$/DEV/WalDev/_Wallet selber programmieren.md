# Selber eine (Kommandozeilen) Wallet programmieren

* [Wallet](../../GLOSSAR/W/Wallet.md) im Glossar
* [Bitcoin API Doc](https://developer.bitcoin.org/reference/rpc/)
## Intro
Da ich mich nun täglich mit Crypto befasse, und ich mich deshalb auch um die möglichst sichere Aufbewahrung meiner Keys kümmern muss, und ich das nur kann, wenn ich im DETAIL verstehe, wie GENAU das funktioniert, habe ich im September 2025 beschlossen, mir eine eigene Wallet zu bauen. 

Dabei ist es nicht mein primäres Ziel damit zu arbeiten, sondern einfach nur mal auf der Bit Und Byte-Ebene zu verstehen wie man a) mit der BitCoin-Blockchain und zu einem späteren Zeitpunkt man mit dem b) Lightning Netzwerk interagiert. 

## Resourcen
Im Internet gibt es zahlreiche Ressourcen die zeigen wie das geht. 

* [Code a Metamask clone (Crypto wallet) - Full tutorial](https://www.youtube.com/watch?v=yplXNd0gt2sf)

* extensive [**BitCoin Developer GUIDE**](https://developer.bitcoin.org/devguide/index.html) and [Developer Reference](https://developer.bitcoin.org/reference/intro.html) (komprimierte, datenfokussierte Sicht). 

* https://developer.bitcoin.org/devguide/index.html
## Aufbau einer WalletApp
![Aufbau einer Wallet](./zPIC/Aufbau%20einer%20Wallet.png)
Grundsätzlich interagiert die App den [**APIs**](https://developer.bitcoin.org/reference/rpc/) der jeweiligen Blockchains. 

Intern benötigt die App eine **Konfigurationsdatei** in der die persönlichen Zugriffsdetails (worauf soll wie zugegriffen werden), resp. Defaultwerte, damit insbesondere beim Testen dieselben Daten nicht immer wieder neue eingegeben werden müssen oder die KommandozeilenApp auch ohne UserInteraktion getestet werden kann. 

Ausserdem enthält die App den "privaten Schlüssel" (sozusagen das Passwort zu deinem CryptoKonto) in verschlüsselter Form. Dieser Private Key wird benötigt um auf deine Satz zugreifen und Transaktionen verschlüsseln zu können. 

Last but not least sollte die App mittels einem weiteren API Zugriff auf einen externen KursDatenAnbieter wie z.B. Coingecko haben. 







