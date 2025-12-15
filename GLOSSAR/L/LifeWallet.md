# LifeWallet
* [Wallet](../W/Wallet.md)
* [Mini Wallet](../M/MiniWallet.md) // [Paper Wallet](../P/PaperWallet.md)
* [Seed Verwaltung](../../../PRIV/_KEY/Admin/PW/SeedVerwaltung.md)
* 
---

LifeWallets sind meine persönliche Bezeichnung für **seedless Cold/Hardware-[Wallets](../W/Wallet.md)**, die ich ausschliesslich für meine verschiedenen (Alters-)Anlage-Konten ab CHF 5000.-- aufwärts verwende die möglichst **anonym bleiben und möglichst wenig angefasst** werden sollen, wenn z.B. alle paar Monate  "überschüssiges" Geld (minimum 1000.-- um die Transaktionskosten zu rechtfertigen) von meinen [Mini Wallets](../M/MiniWallet.md) auf diese LifeWallets übertragen werden. 

Aktuell (Stand November 2025) implementiere ich LifeWallets in der Form von [Tangem Karten ](../../Assets/Products/Hardware/T/Tangem/_Tangem.md). 

Mittlerfristig werde ich sie durch noch sichere [BitKeys](#bitkey-wallet) für BTC und [Cypherock X1 Lösung](#cypherock-x1-vault-mit-4-karten-kombi) für Altcoins ablösen. 

Allen LifeWallet-Lösungen gemeinsam ist, dass sie 
1. **seedless** arbeiten (eine SeedPhrases wird man niemals sehne und muss sie darum auch nicht verwalten)
2. realtiv teuer sind (um die 150$) 
3. nicht immer verfügbar sind (weil ausverkauft).
4. es proprietäre Lösungen sind, deren Firmen man sich auf Gedeih und verderben ausliefert und man sich in deren (hackbaren und ev. vom Staat einsehbaren) Kundendatenbank als CryptoOwner outed.

## Implementierung
Zur Zeit implementiere ich LifeWallets in der Form von [TangemKarten](../../../PRIV/_KEY/Assets/Products/Hardware/T/Tangem/_Tangem.md)

Mittelfristig werde ich sie durch noch sichere [BitKeys](#bitkey-wallet) für BTC und [Cypherock X1 Lösungen](#cypherock-x1-vault-mit-4-karten-kombi) für Altcoins ablösen. 

Untenstehend findet man ein paar Notizen zu den für mich relevantesten ColdStorageLösungen

## Technologieauswahl für ColdStorageLösungen

### TANGEM für LifeSeeds
* **Webseite** = https://tangem.com/en/
* **[Handelsregister](https://www.moneyhouse.ch/de/company/tangem-ag-14771977121)**  

Tangem geht den umgekehrten Weg: Man erhälte eine Chipkarte mit einer hardcodierten BitCoin-Adresse zusammen mit einer MobileWallet-App, welche den Schlüssel immer nur direkt via (Blootooth-Connection??) von der Karte liest, aber niemals elektronisch (zwischen-)speichert. 

Die Firma wurde 2017 in Zug gegründet und ist 2025 nach Luzern gezügelt. 

Mehr Details zu meinem TangemKonto resp. Karten [in der AssetVerwaltung](../../Assets/Products/Hardware/T/Tangem/_Tangem.md)


### Cypherock X1 (Vault mit 4 Karten Kombi)

Diese von vielen als sicherste beschriebene Hardware-Lösung generiert bis zu 4 neue Wallets, wobei die **Seedphrase direkt zerstückelt und die Bruchstücke direkt auf die Vault und die 4 Karten übertragen werden**, so dass im Folgenden Transaktionen immer nur noch mit zwei der 5 Teile bestätigt - i.d.R mittels Vault und einer der vier Karten - bestätigt werden oder die Seedphrase wieder auf einer neuen Wallet wiederhergestellt werden kann.  
Leider kostet diese Lösung beim [Schweizer Online Händler](https://hodl.swiss/collections/hardwarewallets/products/cypherock-x1-die-sicherste-krypto-hardware-wallet-der-welt) um die CHF 120.-- plus Importzoll. 

#### Die Vault
Mittels OLED-Display und Joystick erlaubt die Vault auch Offline einfache Navigation und Verifizierung direkt am Gerät.

#### CySync-App
Die mitgelieferte OpenSource PC App (Mobile ist in der Entwicklung) bietet ein sichere und intuitive Verwaltung der damit verwaltbaren rund 9.000 häufigsten Coins und Tokens, wie z.B.  Bitcoin (BTC), Ethereum (ETH) oder Dogecoin (DOGE).

#### CONS
* Kann nur 4 Wallets und damit lediglich 4 BitCoin-Adressen verwalten (to be verified). 
* Teuer
* MobileApp erst in der Entwicklung -> nice to have weil ich für diese Art von Transaktionen immer den Laptop mit dabei habe
* Zusatzaufwand für die Verwaltung und sichere Aufbewahrung der 4 Karten
* Kein Fingerabdrucksensor. 

#### PROS
* **Sich nie mehr eine PassPhrase merken müssen** und sie damit auch nirgends mehr aufschreiben. Die Passphrase existiert ausserhalb der 5 X1-Teile nirgends - weder physich als Papier etc. noch virtuell auf einem Gerät und kann deshalb weder gehackt noch sonst irgendwie zufällig "gefunden" werden. 

* Coole Integration von Vault und PC-APP

### BitKey Wallet
[BitKey](https://bitkey.build/) ist DER stylische RollsRoyce der BitCoin-Wallets aus Granit mit einem goldenen Ueberzug mit Fingerabdrucksensor und ohne Screen.  
So interessant wie die Hardware sind auch die Blog- und Supportbeiträge dazu welche z.T. tief in die Details genereller Cryptotransaktionen gehen.  
![Bit Key](./zPIC/BitKey.png)

#### CON
Aktuell kann man mit dieser Wallet lediglich BTCs verwalten. 

## Technische weiter-Entwicklungen und damit verbundene Chancen und Risiken

### Quantenhacks
Im Zug der fortschreitenden Entwicklung von Quantencomputern ist die CryptoCommunity bestrebt Blockchains auch vor QuantenHacks zu sichern. Deshalb sind diesbezügliche Aenderungen bez. der grundlegenden Sicherheitstechnologien zu erwarten bei denen sich Standards erst noch etablieren müssen. Damit verbunden ist anzunehmen dass sich auch ColdWallet-Technologie anpassen muss und "alte" ColdWallets durch neue ersetzt werden müssen oder sollten. 