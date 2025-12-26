# Private Key: der geheime Zugangsschlüssel

* [Public Key](PublicKey.md)
* [Wallet](../W/Wallet.md)

Der Private Key ist das Gegenstück zum [Public Key](PublicKey.md). Zusammen bilden beide jeweils ein einzigartiges Schlüsselpaar. Der Private Key ermöglicht die Entschlüsselung von mit dem zugehörigen Public Key verschlüsselten Daten. 

Im Cryptokontext ist der Private Key eine geheim zuhaltende, kryptografische 256-bit Zeichenfolge, die zur Signierung und Autorisierung eigener Blockchain-Transaktionen und damit für den Zugriff auf eine bestimmtes BTC-Konto, resp. eine bestimmte BlockchainAdresse verwendet wird resp. ist ein Private Key - technisch gesehen - mit der entsprechenden Bitcoin Adresse mathematisch verknüpft (aber nie mit dieser identisch).  

> wenn man nur die Anzahl Bitcons auf dieser Adresse sehen will, kann man das auch ohne PrivateKey tun. 

PrivatKeys werden meistens in sogenannten Wallets gespeichert, können abrer auch nativ offline z.B. auf feuer- und wasserfestem Papier geschrieben und immer wieder von Hand neu eingegeben werden (was aber aus praktischen Gründen und wegen der Fehleranfälligkeit beid er Eingabe niemand macht). 

Wenn schon offline und von Hand, dann werden diese PrivatKeys, resp. die zu deren Verwaltung benötigte Wallet, über die einfacher zu merkendere [Seedphrase]() - eine Kombination von 12, 18 oder 24 Wörtern aus einem fixen 2042 Wörter umfassenden Vorrat - wieder hergestellt.  

## Beispiel
**Ein BTC PrivatKey eine 256-bit-Nummer** welche i.d.R. entweder in hexidezimaler Form als eine Folge von 64 Zeichen von 0-9 oder A-F dargestellt werden:  

> **E9873D79C6D87DC0FB6A5778633389F4453213303DA61F20BD67FC233AA33262**

### Range of valid ECDSA private keys
Nur Keys von 0x1 bis 0xFFFF FFFF FFFF FFFF FFFF FFFF FFFF FFFE BAAE DCE6 AF48 A03B BFD2 5E8C D036 4140 sind gültig Private Keys, resp. enthält nicht der ganze 256Bit-Zahlenraum gültige Schlüssel. Der Gültigkeitsbereich wird für BTC im sogenannten "secp256k1 ECDSA standard" geregelt. 

### Base58 Wallet Import format (WIF)
Beim Wallte-Import von ECDSA PrivatKeys wird oft ein kürzeres Foramt verwendet welches bei der Eingabe auch PrüfsummenChecks ermöglicht. Zudem zeigen die führenden Bits, wofür der Schlüssel verwendet werden soll. 

For private keys associated with uncompressed public keys, they are 51 characters and always start with the number 5 on mainnet (9 on testnet). 

Private keys associated with compressed public keys are 52 characters and start with a capital L or K on mainnet (c on testnet). 

This is the same private key in (mainnet) wallet import format:

> **5Kb8kLf9zgWQnogidDA76MzPL6TsZZY36hWXMssSzNydYXYB9KF**

When a WIF private key is imported, **it always corresponds to exactly one Bitcoin address**. Any utility which performs the conversion can display the matching Bitcoin address. The mathematical conversion is somewhat complex and best left to a computer, but it's notable that the WIF guarantees it will always correspond to the same address no matter which program is used to convert it.

### Mini private key format
Some applications use the mini private key format. **Not every private key or Bitcoin address has a corresponding mini private key** - they have to be generated a certain way in order to ensure a mini private key exists for an address. The mini private key is used for applications where space is critical, such as in QR codes and in physical bitcoins. The above example has a mini key, which is:

> **SzavMBLoXU6kDrqtUVmffv**

## PrivateKeys nicht wiederverwenden!
If a private key controlling unspent bitcoins is compromised or stolen, the value can only be protected if it is immediately spent to a different output which is secure. 

Because **bitcoins can only be spent once, when they are spent using a private key, the private key becomes worthless**. 

<span style="color:red; font-weight:bold">ACHTUNG</span>: It is often possible, but inadvisable and insecure, to use the address implemented by the private key again, in which case the same private key would be reused.

## Wallets
Jede BTC-Wallet enthält mindestens einen oder mehrer in der WalletDatei verschlüsselte PriavtKeys. 

Some wallets allow private keys to be imported without generating any transactions while other wallets or services require that the private key be swept.

When a private key is swept, a transaction is broadcast that sends the balance controlled by the private key to a new address in the wallet. Just as with any other transaction, there is risk of swept transactions to be double-spending.

In contrast, bitcoind provides a facility to import a private key without creating a sweep transaction. This is considered very dangerous, and not intended to be used even by power users or experts except in very specific cases. 

Importing keys could lead to the Bitcoins being stolen at any time, from a wallet which has imported an untrusted or otherwise insecure private key - this can include private keys generated offline and never seen by someone else.

## Alternativen
**Privat Keys in Selbstverwahrung sind ein Auslaufmodell** und werden durch bessere Hardwarelösungen wie z.B. [Tangem Karten](../../../PRIV/_KEY/Assets/Products/Hardware/T/Tangem/_Tangem.md) oder [Multiparty Computation Technology (MPC)](#multiparty-computation-technology-mpc) abgelöst. 

### Multiparty Computation Technology (MPC)
Das Verwalten des PrivateKeys birgt natürlich das Risiko des Single Points of Failure. Geht er verloren, vergessen oder wird er gestohlen, gibt es keinen Weg mehr zum Konto. 

Eine Alternative bietet die sogenannte ["MultiParty Computation Technologie" MPC](../M/MPC.md), wie sie z.B. von [Swissborg](../../SERVICES/S/Swissborg/Swissborg.md) verwendet wird. 

Sie schützt Konten und Transaktionen in dem ihr Zugang durch das Zusammenspiel verschiedener Transaktionspartner, bei denen keiner den GANZEN Privaten Schlüssel hat, resp. wird erst gar kein [Private Key](../P/PrivateKey.md) verwendet, der damit auch nicht gestohlen oder erraten werden kann. 

[Swissborg](../../SERVICES/S/Swissborg/Swissborg.md) verwendet z.B. Fireblocks: die gemäss eigenen Angaben sicherst Platform um digitale Assets mittels "multiparty computation technology" zu schützen. 


