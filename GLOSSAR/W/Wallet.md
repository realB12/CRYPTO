# Wallet
Uebersicht über Sinn, Zweck und den Gebrauch von (Bitcoin)Wallets

-> [BTC Wallet](../../b$/GLOSSAR/W/Wallet.md)
-> [Paper Wallet](../P/PaperWallet.md)

Technisch gesehen ist eine "Wallet" mal primär nichts anderes als die Speicherung eins [Public](../P/PublicKey.md) und eines dazu passenden [Private Keys](../P/PrivateKey.md). 


Zur Verwaltung von Kryptowährungen und anderen Token braucht es eine Wallet. Bei der Wallet handelt es sich um einen Speicherort für Adressen, Public und/oder Private Keys. Das heisst, die Kryptos liegen nicht in der Wallet, sondern die Wallet beinhaltet die Zugangsdaten für den Zugriff auf die Kryptos, welche wiederum auf der Blockchain liegen. In einer Wallet können mehrere Zugangsdaten gespeichert werden. Aus Sicherheitsgründen entscheiden sich Krypto-Besitzer:innen allerdings eher für mehrere Wallets. Es gibt verschiedene Typen von Wallets, die gängigsten zwei sind:   

### Wiederherstellung
Gehen Wallets verloren können sie mittels Seedphrases wieder hergestellt werden. 

## Need
Derzeit **bieten Schweizer Banken keine direkten Aufbewahrungslösungen für Kryptowährungen** an, daher wird empfohlen, eine Hardware-Wallet oder eine vertrauenswürdige digitale Wallet zu verwenden.

## Wallet-Typen




## Hierarchical Deterministic (HD) Wallets
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

### Multi-Signatur-Wallets
Moderne Multi-Signatur-Wallets benötigen die Genehmigungen mehrer an Transaktionen beteiligten Personen und bieten deshalb zusätzliche Sicherheit. 
---

## Benötige ich denn überhaupt eine Wallet?
Technisch gesehen, nein. Man kann seine Kryptos auch auf einer Kryptobörse liegen lassen. Diese wurden leider schon mehrmals gehackt oder deren Bestände wurden veruntreut oder gingen sonstwie verloren. Einige Cryptobörsen wie z.B.  [Swissborg](../../SERVICES/S/Swissborg.md) verfügen über eine Einlagensicherung. 

There are also the risks of exchange hacks. We always recommend using a self-custodial wallet, you can learn more about the safest ways to store crypto in our Crypto Safety 101 Guide.