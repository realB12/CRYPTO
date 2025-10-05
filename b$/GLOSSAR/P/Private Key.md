# Private Key (k) = Passwort zum Entschlüsseln für MICH

* [Public Key](Public%20Key.md)
* [Seed Phrase](../S/Seed.md)

---

**Ein Private Key - oft mit einem kleinen "k" dargestellt - ist eine zufällig generierte 256 Bit lange Binärzahl, über die JEDERMANN auf die "Coins" einer bestimmten BitCoin Adresse (Public Key) zugreifen kann, und deshalb unter ALLEN UMSTAENDEN und von Anfang an geschützt werden muss**

Der Private Key die die einzige Quelle für die Generierung

a) des [Public Keys](Public%20Key.md) den Du als eine Art KontoNumemr mit Leuten teilst, die dir darauf Geld überweisen. 

b) von **Signaturen** mit denen Du dich als Besitzer von auf der Blockchain verbuchten BitCoins ausweist. 

Private Schlüssel leben in der Regel **nur versteckt in der Wallet und sind damit i.d.R. weder sichtbar** noch werden sie benötigt um etwas manuell zu erledigen! 

> **Hinweis**: Private Keys können NICHT von Public Keys abgeleitet werden (was ja der eigentliche Trick bei der Sache ist). 

Deshalb müssen Private Schlüssel auch super safe auf speziellen Hardware  ("Cold Wallets") oder [Paper Wallet](PaperWallet.md)  gesichert werden. 

Spätestens dann wenn die Wallet-App, resp. das dazugehörige iPhone mal verloren geht, gehackt wird oder nicht mehr funktioniert wird der Private Key wieder benötigt um eine neue Wallet auf einem neuen Gerät so zu konfigurieren damit man mit ihr wieder auf das BitCoin-"Konto" zugreifen kann.

## Einen Privaten Schlüssel selber generieren  

### Würfeln
You can pick your private keys randomly using just a coin, pencil, and paper: toss a coin 256 times and you have the BINARY digits of a random private key you can use in a bitcoin wallet. 

Alternativ kannst Du auch mit einem 16-ner Würfel 64 mal eine Hexadezimale-Zahl würfeln und aufschreiben: 

`1E99423A4ED27608A15A2616A2B0E9E52CED330AC530EDCC32C8FFC6A526AEDD`

### SeedPhrases
Da das elektronische Kopieren dieses Schlüssels nicht sicher ist (Memoryleak, Spoofing, etc. ) und eine manuelle Uebertragung dieser 64 Zahlen höchst fehleranfällig ist, hat sich die Verwendung sogenannter [SeedPhrases](../S/Seed.md) - eine Folge von 12, 18 oder 24 Wörtern aus denen sich der Private Key Generieren lässt, insbesondere für das Erstellen von [Paper Wallets](PaperWallet.md) als zuverlässiger und praktikabler herausgestellt. 

[SeedPhrases](../S/Seed.md)SeedPhrases erstellt man nicht manuell, sondern werden i.d.R. beim Einrichten von Wallets generiert und bergen damit das Risiko, dass sie bereits bei der Genererierung - selbst im im Offline-Modus -  "gehackt" werden könnten. 

### Sich mit einer App einen Schlüssel generieren
The first and most important step in generating keys is to find a secure source of entropy, or randomness. Creating a bitcoin key is essentially the same as "Pick a number between 1 and 2256." The exact method you use to pick that number does not matter as long as it is not predictable or repeatable. Bitcoin software uses the underlying operating system’s random number generators to produce 256 bits of entropy (randomness). Usually, the OS random number generator is initialized by a human source of randomness, which is why you may be asked to wiggle your mouse around for a few seconds.

More precisely, the private key can be any number between 0 and n-1 inclusive, where n is a constant (n = 1.1578 * 10^<small>77</small>, slightly less than 2^<small>256</small>) defined as the order of the elliptic curve used in bitcoin (see Elliptic Curve Cryptography Explained). To create such a key, we randomly pick a 256-bit number and check that it is less than n. In programming terms, this is usually achieved by feeding a larger string of random bits, collected from a cryptographically secure source of randomness, into the SHA256 hash algorithm, which will conveniently produce a 256-bit number. If the result is less than n, we have a suitable private key. Otherwise, we simply try again with another random number.

<span style="color:red; font-weight:bold">Warning</span>: 
Do not write your own code to create a random number or use a "simple" random number generator offered by your programming language. 

Use a cryptographically secure pseudorandom number generator (CSPRNG) with a seed from a source of sufficient entropy. Study the documentation of the random number generator library you choose to make sure it is cryptographically secure. Correct implementation of the CSPRNG is critical to the security of the keys.

The following is a randomly generated private key (k) shown in hexadecimal format (256 bits shown as 64 hexadecimal digits, each 4 bits):

`1E99423A4ED27608A15A2616A2B0E9E52CED330AC530EDCC32C8FFC6A526AEDD`

**Tip**
The size of bitcoin’s private key space, (2^<small>256</small>) is an unfathomably large number. It is approximately 10^<small>77</small> in decimal. For comparison, the visible universe is estimated to contain 10^<small>80</small> atoms.

To generate a new key with the Bitcoin Core client (see [ch03_bitcoin_client]), use the `getnewaddress` command. For security reasons it displays the public key only, not the private key. To ask `bitcoind` to expose the private key, use the `dumpprivkey` command. The `dumpprivkey` command shows the private key in a Base58 checksum-encoded format called the `Wallet Import Format` (WIF), which we will examine in more detail in Private key formats. 

Here’s an example of generating and displaying a private key using these two commands:

    $ bitcoin-cli getnewaddress
    1J7mdg5rbQyUHENYdx39WVWK7fsLpEoXZy

    $ bitcoin-cli dumpprivkey 1J7mdg5rbQyUHENYdx39WVWK7fsLpEoXZy
    KxFC1jmwwCoACiCAWZ3eXa96mBM6tb3TYzGmf6YwgdGWZgawvrtJ

The `dumpprivkey` command opens the wallet and extracts the private key that was generated by the `getnewaddress` command. It is not possible for `bitcoind` to know the private key from the public key unless they are both stored in the wallet.

<span style="color:red; font-weight:bold">ACHTUNG</span>: 
The `dumpprivkey` command does not generate a private key from a public key, as this is impossible. The command simply reveals the private key that is already known to the wallet and which was generated by the `getnewaddress` command.

You can also use the Bitcoin Explorer command-line tool (see [appdx_bx]) to generate and display private keys with the commands `seed`, `ec-new`, and `ec-to-wif`:

    $ bx seed | bx ec-new | bx ec-to-wif
    5J3mBbAH58CpQ3Y5RNJpUKPE62SQ5tfcvU2JpbnkeyhfsYB1Jcn