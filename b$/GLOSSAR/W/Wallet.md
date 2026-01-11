# Bitcoin Wallets

* [UTXOs in Bitcoin Wallets](#utxos-in-bitcoin-wallets)
* [Choosing a Bitcoin Wallet](#choosing-a-bitcoin-wallet)

* [Seed Phrases](../S/Seed.md)

* [SpeedWallet](../../../SERVICES/S/SpeedWallet/_SpeedWallet.md): my personally preferred Wallet. 

* [Seed Verwaltung](../../../../PRIV/_KEY/Admin/PW/SeedVerwaltung.md)    

* [Metamask](../../../../PRIV/_KEY/Assets/Services/M/Metamask.md) // [Relai](../../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md)
  
* generische [Paper Wallets](../P/PaperWallet.md)

* [Paper Wallet](../P/PaperWallet.md)

* [Private Key](../P/Private%20Key.md) // [Public Key](../P/Public%20Key.md)  

## Intro
Aus **EndUser Sicht** bezeichnet eine "Wallet" i.d.R eine zugangsgesicherte lokal installierte oder remote betriebene **Software** oder **App** mit der man die **BitCoin-Blockchain lesen und Transaktionen signieren kann**, die über den sogenannten [Mempool](../M/Mempool.md) mittels Mining-Prozesse für immer auf der Blockchain verbucht werden. Wallet-Technologie ist sozusagen das **unverzichtbare FrontEnd des ganzen BitCoin-Systems** um z.B. Bitcoins zu erhalten, zu kaufen oder mit Satoshis (SATS) zu bezahlen.  

Technisch gesehen, ist eine "Wallet" primär mal nichts anderes als eine (i.d.R. mittels Wallet-App verwaltete) Datei oder eine Datenbank für [Private Keys](../P/Private%20Key.md) und die daraus generierten [Public Keys](../P/Public%20Key.md), welche über eine ebenfalls mit dieser Wallet generierte [SeedPhrase](../S/Seed.md) wieder hergestellt werden könnten. 

Im täglichen Umgang mit Wallet-Apps sieht man diese Schlüssel aber kaum, das sie implizit von der WalletApp verwaltet und benutzt werden - was wiederum heisst - dass JEDER der auf deine WalletApp zugreifen kann, auch ohne dass er die Seedphrase oder den Private Key kennt, sich deine Coins auf sein Konto überweisen kann!

Aus diesem Grunde sind WalletApps meist zusätzlich durch ein Passwort oder biometrische Zugangsprüfung wie z.B. Gesichtserkennung geschützt. Wer es sicherer braucht und nur selten auf seine ANLAGE-Coins zugreifen muss, sollte dies auf eine sogenannte Cold-Wallet transferieren: offline-only Hardwarelösung die lediglich die Keys aufbewahren aber ansonsten keine Coins kaufen oder transferieren können.

Weil praktisch jede User-Interaktionen über eine Wallet läuft (Authentication) muss auch praktisch jede Bitcoin-App im Sinne eines Single-Point of Entry- über eine Wallet laufen.

Entsprechend gross ist meine persönliche Motivation dieses Kerntechnologie und vor allem deren Sicherheitsaspekte von Grund auf zu verstehen (was mich im Sept 2025 veranlasste mir eine [eigene Wallet-App zu programmieren](../../DEV/WalDev/_Wallet%20selber%20programmieren.md). 

### Wallettypen
Wallet-Apps - sogenannte Hot Wallets - gibt es in allem möglichen Formen als WebExtension, Mobile- und Desktop-Apps von hunderten von verschiedenen Herstellern. Die bekanntesten Wallets sind vermutlich die Metamask Wallet und für die Schweizer die [Relai App](../../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md). 

### Wallets als Filter
Wenn Wallets direkt mit einem eigenen, lokal installierten Knoten (Bitcoin Core) verbunden werden, diesen sie zusätzlich als Filter um aus der Menge aller anbrausenden Transaktionen nur die auf die Wallet passenden herauszufiltern. 

### ReferenzWallet
Die erste und damit auch Referenzwallet geltende, [ "Satoshi Client" oder "Bitcoin Core"](../B/BitCoin%20Core.md) benannte, direkt von Satoshi Nakamoto's OriginalApp abgeleitete OpenSource-App, wird in der Praxis nur noch selten verwendet.  

### Wiederherstellung einer Wallet mittels Seed
Bei Verlust der WalletApp (z.B. durch das Verlieren des Handys) kann man die selbe oder eine andere kompatible WalletSoftware runterladen, und den impliziten Private Key in der WalletApp durch die Eingabe der Seedphrase wieder herstellen, woraus dann die WalletApp wieder den Public Key generiert, um daraus dann wieder die öffenltiche BTC-Adresse zu erstellen: ![Wiederherstellung der Schlüssel mittels Seed](../zPIC/Wiederherstellung%20der%20Schlüssel%20mittels%20Seed.png)

## Bitcoin Addresse mit QR Code
The most important part of a wallet is its [bitcoin address](../A/Address.md) such as: `1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK`. 

Next to it we normally find a **QR code** that can be scanned by a smartphone camera. 

**Tip**: Tapping the QR code on the screen might magnify it for easier scanning.

> <span style="color:red; font-weight:bold">ACHTUNG</span>: 
Keeping private keys and seed phrases secure is essential!

### Generieren von neuen Keys und Addressen

WalletApp generieren i.d.R. bei der Installation 

1. einen zufälligen **[Private Key](../P/Private%20Key.md)**

2. daraus mittels EllipsenKurvenAlgorithmus einen **[Public Key](../P/Public%20Key.md)** und  damit die öffentlich bekannte **WALLET-Adresse**. 

3. Mittels Hashfunktion wird anschliessend die kürzere, öffentlich zu teilende **[BLOCKCHAIN-Addresse](../A/Address.md)** des damit assozierten BTC Kontos abgeleitet (ACHTUNG: Der Public Key ist NICHT gleich der BlockchainAdresse!) 

4. Last but not least generiert die Wallet eine **24-stellige [SeedPhrase](../S/Seed.md)** welche es geheim zu halten gilt da damit die Wallet (z.B. beim Verlust Deines Handys) wieder hergestellt werden kann und damit jeder, der das macht, auch Zugriff auf deine Schlüssel und damit deine Coins erhält! 

#### Wann wird eine BTC-Addresse sichtbar
Zu diesem Zeitpujnkt sind diese so neu generierten [Adressen](../A/Address.md) weder in der Blockchain, noch sonst irgendwo (z.B. bei einem Servic- oder Walletprovider) bekannt, und bleiben es auch, bis jemand BTC auf diese Adresse sendet (oder du die Adressen ausplauderst oder - falls du sie gespeichert hast - gehackt oder geklaut wurden). Bis dahin ist diese Bitcoin Adresse lediglich eine zufällige Nummer mit einem dazu gehörenden, nur Dir bekannten Privat Key, mit dem Du, sollten dann mal jemand BTCs auf diese Adresse überwiesen, Du auf diese zugreifen und über diese verfügen kannst. Auch stehen diese Adressen in keinster Weise mit deiner Person in Verbindung. 
 
> Until the moment this address is referenced as the recipient of value in a transaction posted on the bitcoin ledger, the bitcoin address is simply part of the vast number of possible addresses that are valid in a bitcoin address space. Only once it has been associated with a transaction it become part of the known addresses in the network. Before it is just a locally generated but otherwise totally unknown number to the world. 

Damit ist auch klar dass man jederzeit auch eine nur durch die Rechenpower beschränkte Anzahl Wallets erstellen könnte um einfach mal Millionen von BlockchainAdressen durchzuchecken ob man ev. zufällig auf eine bereits erstellte trifft. 

Die Blockchain selber führt nur eine Liste aller Transaktionen aber keine mit WalletAdressen resp. PublicKeys (die man natürlich auch nicht von den mittels Hashfunktion aus den PublicKeys asymetrisch one-way-generierten Blockchain-Adressen ableiten kann) und funktional ist es der Blockchain egal ob die bei einer Transaktion angegebene Adresse bereits existiert oder nicht (was wiederum heisst, dass wenn du deine Coins an eine falsche Adresse sendest (von der weder du noch dein Empfänger den Schlüssel hat) sind diese Coins für immer und ewig für jedermann futsch. Wichtig: Es wird Dich nichts und niemand daran hindern, deine Coins auf eine falsche Adresse zu senden. Das geht durch wie Butter, so wie jeder andere Transaktion auch! Falls die Adresse nicht existiert, wird einfach eine neue erstellt (auf die dann natürlich niemand Zugriff hat). 

-> for more details see -> [Address](../A/Address.md)

## UTXOs in Bitcoin Wallets
Auch eine Wallet-App speichert keine Bitcoins, sondern managed die mit einer bestimmten Crypto-Addresse assozierten [UTXOs](../U/UTXO.md): 

1. **Konto**: Der in einer Wallet gespeicherte Wert (resp. der für eine Transaktion zur Verfügung stehende Betrag) ist die Summe aller darin enthaltenen UTXOs (resp. die Summe aller mit der Wallet-Addresse assoziierten UTXOs). 

2. **Transaction**: When you initiate a transaction, your wallet software selects appropriate UTXOs to use as inputs where their sum is equal or higher the amount of the "money" sent + transaction-fees.

3. **Retourgeld**: If the selected UTXOs exceed the amount you want to send, your wallet creates a change output back to one of your addresses.

4. **Konsolidierung**: Ab und zu werden die UTXOs mit kleinen Beträgen zu einem grösseren UTXO zusammengefasst um so Transaktionsgebühren zu sparen. 

5. **Privacy**: Fortgeschrittene wallets wit z.B. "CoinJoin" können UTXOs von mehreren Usern zusammenlegen, um so die Anonymität zu wahren, resp. Absender und Empfänger von Transaktionen zu verschleiern. 

### Wallets gestalten Transaktionen "behind the scene"
All the logic for selecting appropriate inputs and outputs to build a transaction is normally hidden by the wallet. Users  only specify a destination and an amount, and the rest happens in the wallet application without seeing the details. Importantly, a wallet application can construct transactions even if it is completely offline. Like writing a check at home and later sending it to the bank in an envelope, the transaction does not need to be constructed and signed while connected to the bitcoin network.

---

## Klassifikation von Bitcoin Wallet
Bitcoin wallets are one of the **most actively developed applications** in the bitcoin ecosystem and where a new wallet is probably being developed right now, **several wallets from last year are no longer actively maintained**. 

Many wallets focus on specific platforms or specific uses and some are more suitable for beginners while others are filled with features for advanced users. 

However, **moving keys or seeds between bitcoin wallets is relatively easy**. So it is worth trying out several wallets until you find your personal best.



Nebst der klassischen Unterscheidung zwischne **HOT online Wallet(Apps)** und **COLD offline-only Speicherlösungen** können wir Wallets auch nach folgendne Kriterien unterscheiden: 

1. [**GenerierungsArt** Non-Determistic versus Seed Wallets](#1-non-determistic-versus-seed-wallets)
2. [**Platform**: Mobile, Desktop, Web, Hardware, Paper](#2-platform-typen)
3. [**Autonomie**: Full-/LightWeight Client oder ThirdParty API App](#3-autonomy-types)

### 1. Non-Determistic versus Seed Wallets

<span style="color:red; font-weight:bold">ACHTUNG</span>: 
**The use of nondeterministic wallets is discouraged for anything other than simple tests**. 

They are simply too cumbersome to back up and use. Instead, use an industry-standard–based [HD wallet]() with a mnemonic seed for backup.

#### Nondetermistic Wallets (outdated)
In a **nondeterministic wallet each key is independently generated** from a random number.

The keys are not related to each other. This type of wallet is also known as a **JBOK** wallet from the phrase `"Just a Bunch Of Keys."`

<span style="color:red; font-weight:bold">ACHTUNG</span>: Dieser Wallet Typ sollte aus Sicherheitsgründen nicht mehr verwendet werden!

#### Deterministic-Wallets
In a deterministic wallet - also called seeded wallet - **all the keys are derived from a single master key**, known as the [seed](../S/Seed.md), through the use of a one-way hash function. 

All the keys in this type of wallet are related to each other and can be generated again if one has the original [SeedPhrase](../S/Seed.md).

There are a number of different key derivation methods used in deterministic wallets. The most commonly used derivation method uses a tree-like structure and is known as a `hierarchical deterministic` or `**HD wallet**`.

The seed is a randomly Wallet-generated number encoded as a set of 24 English words, also known as mnemonic code words. 

This seed then is combined with other data, such as an index number or "chain code" (see HD Wallets (BIP-32/BIP-44)) to derive the private keys from which the public keys and finally the blockchain addresses will be derived.

In a deterministic wallet, the seed is sufficient to recover all the derived keys, and therefore a single backup of the Seedphrase at creation time is sufficient. 

The seed is also sufficient for a wallet export or import, allowing for easy migration of all the user’s keys between different HD-Wallet implementations. 

<span style="color:red; font-weight:bold">ACHTUNG</span>: SeedPhrasen funktionieren nur bei Wallets die auf der selben (HD-)-Technologie basieren. Dies Kompatibilität sollte vor dem Transfer mit den Herstellern geklärt werden, resp. sollte man nur Wallets verwenden, deren Marke und Business im Markt etabliert sind und denen zuzutrauen ist, dass deren Produkte und Support auch nach Jahren noch verfügbar sind. 

#### HD Wallets (BIP-32/BIP-44)
The most advanced form of deterministic wallets is the HD wallet defined by the BIP-32 standard. 

HD wallets contain keys derived in a tree structure, such that a parent key can derive a sequence of children keys, each of which can derive a sequence of grandchildren keys, and so on, to an infinite depth. This tree structure is illustrated in Type-2 HD wallet: a tree of keys generated from a single seed.

![HD Wallets](../zPIC/HD%20Wallets.png)

The tree structure can be used to express additional organizational meaning, such as when a specific branch of subkeys is used to receive incoming payments and a different branch is used to receive change from outgoing payments. 

Branches of keys can also be used in corporate settings, allocating different branches to departments, subsidiaries, specific functions, or accounting categories.

The second advantage of HD wallets is that users can create a sequence of public keys without having access to the corresponding private keys. 

This allows HD wallets to be used on an insecure server or in a receive-only capacity, issuing a different public key for each transaction. The public keys do not need to be preloaded or derived in advance, yet the server doesn’t have the private keys that can spend the funds.


### 2. Platform Typen
Bitcoin wallets can be categorized according to the **platform** the application is run upon: **Desktop, Mobile, Web, Hardware, Paper, ColdStorage**:

#### Desktop-Wallet
A desktop wallet was the first type of bitcoin wallet created as a reference implementation and many users run desktop wallets for the features, autonomy, and control they offer. Running on general-use operating systems such as Windows and Mac OS has certain security disadvantages however, as these **platforms are often insecure and poorly configured**.

#### Mobile-Wallet
A mobile wallet is the **most common type of bitcoin wallet**. Running on smart-phone operating systems such as Apple iOS and Android, these wallets are often a **great choice for new users**. Many are designed for simplicity and ease-of-use, but there are also fully featured mobile wallets for power users.

#### Web-Wallet
Web wallets are **accessed through a web browser** and store the user’s **wallet on a server owned by a third party**. This is similar to webmail in that it relies entirely on a third-party server. Some of these services operate using client-side code running in the user’s browser, which keeps control of the bitcoin keys in the hands of the user. Most, however, present a compromise by taking control of the bitcoin keys from users in exchange for ease-of-use. It is **inadvisable to store large amounts of bitcoin on third-party systems**.

#### Hardware-Wallets
Hardware Wallets speichern lediglich den PrivateKey auf einem Chip und kommen immer mit einer WalletApp über die die Hardware konfiguriert und die Schlüssel wieder von dieser Hardware gelesen werden können.     

Den PrivateKey gibt man bei der Installation einmalig entweder über eine Seedphrease manuell auf dem Gerät ein oder überträgt ihn mittels USB oder - wie bei den Tangem-Karten - mittels Near-Field-Communication (NFC). 

Zudem können HardwareWallets zusätzlich noch durch ein auf der Hardware einzugebendes Passwort geschützt werden.

Weil man übers Internet niemals direkt auf diese Hardware-Wallets zugreifen kann, sondern nur über die dazugehörige WalletApp welche nur physische USB oder NFC-Verbindungen zulässt - gelten diese Hardwarewallets als bez. InternetHacking als sehr sicher. Umgekehrt, weil die WalletApp nur im Verbund mit der Wallet Hardware funktioniert ist auch der Verlust des Handys unbedenklich. Wenn die Codes dann auch noch - wie z.B. bei den Tangem-Karten noch auf an verschiedenen Orten vergteilte "Teile" verteilt sind, sind die Schlüssel auch gegen physischen Einbruch oder Katastrophen gesichert.

#### Paper-Wallet 
The keys controlling bitcoin can also be printed for long-term storage. These are known as paper wallets even though other materials (wood, metal, etc.) can be used. Paper wallets offer a **low-tech but highly secure means of storing bitcoin long term**. Offline storage is also often referred to as **cold storage**.

### 3. Autonomy Types

Another way to **categorize bitcoin wallets is by their degree of autonomy** and how they interact with the bitcoin network:

#### Full-node client
A full client, or "full node," is a client that stores the entire history of bitcoin transactions (every transaction by every user, ever), manages users' wallets, and can initiate transactions directly on the bitcoin network. A full node handles all aspects of the protocol and can independently validate the entire blockchain and any transaction. A full-node client consumes substantial computer resources (e.g., more than **125 GB of disk, 2 GB of RAM**) but offers complete autonomy and independent transaction verification.

#### Lightweight client
A lightweight client, also known as a **simple-payment-verification (SPV) client**, connects to bitcoin full nodes (mentioned previously) for access to the bitcoin transaction information, but stores the user wallet locally and independently creates, validates, and transmits transactions. **Lightweight clients interact directly with the bitcoin network, without an intermediary**.

#### Third-party API client
A third-party API client is one that interacts with bitcoin through a third-party system of application programming interfaces (APIs), rather than by connecting to the bitcoin network directly. The wallet may be stored by the user or by third-party servers, but all transactions go through a third party.

Combining these categorizations, many bitcoin wallets fall into a few groups, with the three most common being desktop full client, mobile lightweight wallet, and web third-party wallet. The lines between different categories are often blurry, as many wallets run on multiple platforms and can interact with the network in different ways.


