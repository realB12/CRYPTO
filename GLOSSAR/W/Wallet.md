# Wallet
Uebersicht über Sinn, Zweck und den Gebrauch von (Bitcoin)Wallets

-> [BTC Wallet](../../b$/GLOSSAR/W/Wallet.md)
-> [Paper Wallet](../P/PaperWallet.md)

Technisch gesehen ist eine "Wallet" mal primär nichts anderes als die Speicherung von einem oder mehreren [Private](../P/PrivateKey.md) und dazugehörenden [Public Keys](../P/PublicKey.md) in Form einer lokal installierten oder online abrufbaren App. 

Diese Keys werden für den Zugriff auf Kryptowährungen und andere Tokens und dem signieren entsprechender Transaktionen benötigt.  

Dabei liegen die Crypto-Token selbst nicht in der Wallet sondern immer nur und auschliesslich auf der Blockchain. Die Wallet enthält lediglich die Schüssel um auf dort auf diese Assets zuzugreifen zu können. 

In einer Wallet können mehrere Schlüssel generiert und gespeichert werden. Aus Sicherheitsgründen entscheiden sich Krypto-Besitzer:innen allerdings eher für mehrere Wallets.    

### Wiederherstellung
Gehen Wallets, und damit die in ihnen gespeicherten Schlüssel und damit die Zugriffe auf die Assets verloren, können sie mittels, von der Wallet initial angezeigten und vom Owner sorgfältig zu verwahrenden [Seed Phrasen](../S/SeedPhrase.md)wieder hergestellt werden. 



## Need
Derzeit **bieten Schweizer Banken keine direkten Aufbewahrungslösungen für Kryptowährungen** an, daher wird empfohlen, eine Hardware-Wallet oder eine vertrauenswürdige digitale Wallet zu verwenden.

## Wallet-Typen

### Hierarchical Deterministic (HD) Wallets
Wallet software may use a BIP 32 seed to generate many private keys and corresponding public keys from a single secret value. This is called a hierarchical deterministic wallet, or HD wallet for short. The seed value, or master extended key, consists of a 256-bit private key and a 256-bit chain code, for 512 bits in total. The seed value should not be confused with the private keys used directly to sign Bitcoin transactions.

**Users are strongly advised to use HD wallets, for safety reasons**: An HD wallet only needs to be backed up once typically using a seed phrase; thereafter in the future, that single backup can always deterministically regenerate the same private keys. Therefore, it can safely recover all addresses, and all funds sent to those addresses. 

> Non-HD wallets generate a new randomly-selected private key for each new address; therefore, if the wallet file is lost or damaged, the user will irretrievably lose all funds received to addresses generated after the most recent backup.

## Hot Wallets

Bei der Hot Wallet erfolgt die Speicherung der Zugangsdaten online, das heisst, die Wallet ist permanent mit dem Internet verbunden. Es gibt unterschiedliche Arten von Hot Wallets, die eine einfache und bequeme Handhabung gemeinsam haben. Durch die digitale Speicherung und den passwortgeschützten Zugriff sind Hot Wallets allerdings ein beliebtes Ziel für Cyberkriminelle. Besitzer müssen sich den damit verbundenen Risiken bewusst sein und im Umgang mit ihren Schlüsseln stets vorsichtig sein.

## Cold Wallets
Eine Hardwarewallet - auch Cold-Wallet genannt - ist immer ein physisches Speichermedium für die Offline-Memorisierung des Schlüsselpaars. 

Beispiele sind USB-Stick, Flash- und «Solid State»-Laufwerk oder sogaenannte [Paper Wallet](../P/PaperWallet.md) 

### Nachteile
Insbesondere [Paper Wallets](../P/PaperWallet.md) sind für tägliche Transaktionen wenig geeignet weil, jedes Mal physisch auf das Papier zugegeriffen werden muss und damit schnell einmal kopiert oder beschädigt wird oder gleich ganz verloren gehen kann (die übereifrige Putze oder der Hund).  

### Vorteile
Nebst dem, dass eine PaperWallet von jedermann einfach zu verwenden ist und man dafür nur Papier und einen Drucker braucht und man damit von Drittherstellern unabhängig bleibt, schütehn Cold Wallets wegen ihrer Offgrid-Natur Schlüssel vor Hackern und Malware und sind somit die **beste Option für die LANGFRISTIGE Verwahrung**.

### Risiken
Ausfall durch Materialfehler oder veraltete Software. Auch könnte das Medium gestohlen, verwechselt und/oder kopiert werden, könnte gleich ganz verloren gehen (die übereifrige Putze oder der Hund) oder fällt Feuer, Wasser oder einem Magneten zum Opfer.

### Backup
Deshalb ist es **ratsam Backups von Cold Wallets auf unterschiedlichen Medien an verschiedenen Orten aufzubewahren und deren Lesbarkeit regelmässig zu überprüfen**. 
## Multi-Signatur-Wallets
Moderne Multi-Signatur-Wallets benötigen für die Wiederherstellung und das Signieren von Transaktionen die Genehmigungen mehrer Personen und bieten deshalb - insbesondere für Firmen - zusätzliche Sicherheit nach dem vier-Augen-Prinzip. 

## Paper Wallets
Paper Wallets sind keine eigentlichen Wallets mit denen man Transaktionen tätigen kann, sondern beinhalten lediglich die 12/18/24 Wörter der [Seed Phrase](../S/SeedPhrase.md) für die Wiederherstellung einer Wallet mit der man dann wieder auf die entsprechenden Assets zugreifen kann. 

In diesem Sinne hat man auch über Paper Wallets (nach dem Wiederherstellen einer Wallet) den vollen Zugriff auf Assets - aber einfach nicht ready-made. 

Paper Wallet sind zwar durch ihre 100% Offline-Natur vor Hackern geschützt, gehen aber in der Praxis schneller und öfters verloren als Wallets die man, optisch immer Präsent, z.B. auf dem Handy oder PC mitführt. 


---

## Benötige ich denn überhaupt eine Wallet?
Um Cryptos zu kaufen und zu halten braucht man, technisch gesehen, keine eigene Wallet sondern kann "sie" bei einer CryptoBörse wie z.B. [Swissborg](../../SERVICES/S/Swissborg/Swissborg.md) oder [Binance](../../SERVICES/B/Binance/Binance.md) kaufen. 

Damit erhält man aber keine EIGENEN Crypto-Tokens sondern lediglich eine Bescheinigung, dass Du den Gegenwert deiner Cryptos jederzeit in deiner FIAT-Währung ausbezahlt bekommst. 

Dabei muss dein Crypto-Provider nicht mal eigene Cryptos besitzen. 

Entsprechend erhältst du auch keine Seedphrase oder kannst auch nicht einfach "deine Cryptos" auf eine andere Wallet verschieben oder mit diesen Cryptos bezahlen. Demgegenüber ist die Verwaltung einfacher da du dir einzig und allein - analog zu einer klassischen Bank - lediglich die Zugriffsdaten für den Provider zu merken brauchst, ohne dass Du dich um Seedphrasen, Wallets, Aufbewahrung etc. kümmern musst. 

Leider wurden solche OnlineBörsen, wie z.B. der Fall FTX zeigt, schon mehrmals gehackt oder deren Bestände wurden veruntreut oder gingen sonstwie verloren.

Einige Cryptobörsen wie z.B.  [Swissborg](../../SERVICES/S/Swissborg.md) verfügen immerhin über eine Einlagensicherung.