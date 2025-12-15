# Seed- oder Wiederherstellungsphrasen für MiniWallets
> (**Uebersicht only** für das generisches Crypto Glossar)

-> [SeedPhrase **im Detail**](../../b$/GLOSSAR/S/Seed.md)  

-> [**SEED-Verwaltung**](../../../PRIV/_KEY/Admin/PW/SeedVerwaltung.md): Erstellen und Ablage von neuen Seedphrases

-> [**CRYPTO-Verwaltung**](../../../PRIV/_KEY/Assets/Crypto/_CryptoVerwaltung.md): Single Point of Entry Dokument für alles Crypto und damit auch Uebersicht über alle aktiven Wallets und Seedphrases im Einsatz.

* [BIP39 Wortliste](../B/BIP39%20Wortliste.md)
---

In DIESEM Dokument erkläre ich kurz 

> **was eine SeedPhrase ist und wofür sie grundsätzlich verwendet wird**. 

Für die konkrete Anwendung derselben im Rahmen meiner CryptoAssets wie z.B. der [Relai-Wallet](../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md) wird in einem separaten [Seed Verwaltungs-Dokument](../../../PRIV/_KEY/Admin/PW/SeedVerwaltung.md) beschrieben. 

## Was ist eine SeedPhrase?
Eine Seed-Phrase ist eine geordnete Liste von 12-, 18- oder 24 Wörter, die i.d.R. beim Erstellen einer neuen [(Mini-)Wallet](../W/Wallet.md) nach einem [BIP39](../B/BIP39%20Wortliste.md) genannten Verfahren einmalig aus dem in der Wallet gespeicherten PrivateKey generiert wird, um die Wallet bei Bedarf wieder herstellen zu können, oder (parallel dazu) eine weitere, externe (Backup)Wallet zu erstellen, mit der man ebenfalls auf diese Bitcoins zugreifen kann.

![Seedphrase Beispiel](../zPIC/Seedphrase%20Beispiel.png)

<span style="color:red; font-weight:bold">ACHTUNG</span>: **für die Sicherung meiner Vermögen verwende ich nur noch seedless [Life Wallets](../L/LifeWallet.md)** wie z.B. Tangem Karten, die keine Seedphrases mehr benötigen. 

## Wie wird eine Seed erstellt?
Eine Seed erstellt man i.d.R. nicht selber, sondern wird beim Erstellen einer neuen Wallet automatisch von der WalletSoftware generiert und angezeigt (aber nicht gespeichert!).

Diese Seedphrase ist dann SOFORT gem. [**SEED-Verwaltungs Konzept**](../../../PRIV/_KEY/Admin/PW/SeedVerwaltung.md) als Paperwallet zu sichern. 

Natürlich muss man der WalletSoftware trauen, dass sie das 100% zufällig macht und den PrivateKey nirgendswohin kopiert und intern auch nach höchsten Sicherheitsstandards verschlüsselt hält (resp. ein Hacker ohne das Zugangspasswort zu deiner App den PrivateKey nicht aus dem auf deinem Handy installierten Code oder Daten unverschlüsselt auslesen kann!

## Wozu werden Seeds benötigt?
Am häufigsten dienen **Seeds der Authorisierung von Transaktionen**. 

Weniger häufig aber umso wichtiger sind Seeds bei der **Wiederherstellung der Wallet** (z.B. bei einem Handyverlust oder beim Wechsel auf eine andere oder weitere Wallewt), resp. dem zusätzlichen Aufsetzen einer **BackupWallet** für eine alternative Zugriffsmöglichkeit auf die PrimärWallet resp. dasselbe BTC-Konto. 

Bei der Wiederherstellung einer Wallet generiert diese an Hand der Seedphrase wieder den Privat-Key mit der sie wieder auf das zugehörige (anonyme) BitCoin-"Konto" zugreifen kann, resp. erhält man mittels Eingabe dieser SeedPhrase auch mit jeder anderen, auf einem beliebigen Gerät in einem beliebigen Moment und beliebiger Wallet-Software so über diese wieder Zugriff auf seine Bitcoins, resp. den Inhalt an der  durch den Public Key repräsentierten Adresse der BTC Blockchain.  

Mittels Seed Phrases lassen sich die ansonsten unmerkbar kryptischen als 64HexString geschriebenen Private Keys einfacher sichern und eingeben, z.B. indem man sie auf Papier (-> Paperwallet) in einen Safe legt, in eine Metallplatte einstanzt oder indem man spezifische Hardwarelösungen - sogenannte Cold-Wallets wie z.B. [Tangem]-Karten(../../../PRIV/_KEY/Assets/Products/Hardware/T/Tangem/_Tangem.md) oder die [MeLE Cyber X1 Lösung](../../../PRIV/_KEY/Assets/Products/Hardware/M/MeLE/MeLE%20Cyber%20X1%20MiniPC.md) einsetzt. 

---

> <span style="color:red; font-weight:bold">ACHTUNG</span>: 
Die Seedphrase ist das 100% EINZIGE Mittel um bei Verlust oder Ausfall deiner Wallet jemals wieder auf deine BitCoins zugreifen zu können. **Seedphrases sind demzufolge wichtiger als Autoschlüssel oder Bankkontonummern**.

---

 Bei **nicht verwahrten Wallets**, wie der über die mobile App erstellten Wallet, wird der Seed ausschließlich auf dem Gerät des Kunden generiert und gespeichert und ist z.B für [Relai](../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md) oder Dritte ohne physichen Zugriff auf diese Offline-Ware nicht zugänglich.

---

## Mini- versus Life-Wallets  resp. Seed versus Non-Seed Custody
Grundsätzlich verwende ich Seedsphrases nur noch für [Mini Wallets](../M/MiniWallet.md) für die täglichen Zahlungen, CryptoTrading, Evaluations-, Schulung-, Test- oder "Just4Fun"-Wallets, wo mir Komfort, Preis und Verfügbarkeit von PaperWallets wichtiger sind, als State of the Art Non-Seed-Security, wie z.B. Tangem Karten, die aus Kostengründen meinen [LifeWallets](../L/LifeWallet.md) zur Verwaltung meines Vermögens vorbehalten bleibt. 

[LifeWallets](../L/LifeWallet.md) für den Zugriff auf substantielle Anlage-Konten ab CHF 1000.-- aufwärts basieren auf neuster VERTEILTER Cold/HarwareWallet Technologien die gänzlich OHNE Seedphrase auskommen und damit ohne physischen Zugriff auf mindestens zwei voneinander unabhängigen Karten zu 100% nicht mehr gehackt werden können.   
