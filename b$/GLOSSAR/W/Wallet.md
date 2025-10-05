# Bitcoin Wallets

* [UTXOs in Bitcoin Wallets](#utxos-in-bitcoin-wallets)
* [Choosing a Bitcoin Wallet](#choosing-a-bitcoin-wallet)

* [Seed Phrases](../S/Seed.md)

* [SpeedWallet](../../../SERVICES/S/SpeedWallet/_SpeedWallet.md): my personally preferred Wallet. 

* [Seed Verwaltung](../../../../PRIV/_KEY/Admin/PW/SeedVerwaltung.md)  
* [Metamask](../../../../PRIV/_KEY/Assets/Services/M/Metamask.md) // [Relai](../../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md)
* generische [Paper Wallets](../P/PaperWallet.md)

* [Paper Wallet](../P/PaperWallet.md)
* 
## Intro
Aus einer **GESAMTHEITLICHEN Sicht** bezeichnet eine "Wallet" eine Art **Passwort-Manager-Software** mit der man die **BitCoin-Blockchain lesen und Transaktionen erstellen kann**, die über den sogenannten [Mempool](../M/Mempool.md) im Zuge des Mining-Prozesses für immer auf der Blockchain verbucht werden. Wallet-Technologie ist sozusagen das **unverzichtbare FrontEnd des ganzen BitCoin-Systems**. 

Weil praktisch jede User-Interaktionen über eine Wallet läuft (Authentication) muss auch praktisch jede Bitcoin-App im Sinne eines Single-Point of Entry- über eine Wallet laufen. Entsprechend gross ist meine persönliche Motivation dieses Kerntechnologie und vor allem deren Sicherheitsaspekte von Grund auf zu verstehen (was mich im Sept 2025 veranlasste mir eine [eigene Wallet zu programmieren](../../DEV/WalDev/_Wallet%20selber%20programmieren.md). 

Wallets gibt es in allem möglichen Formen als WebExtension, Mobile- und Desktop-Apps. 

Die bekanntesten Wallets sind vermutlich die Metamask Wallet und für die Schweizer die [Relai App](../../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md)

From a user's perspective a wallet allows you to see the amount of bitcoins you have on the BlockChain and to send and receive Bitcoins, resp. Satoshis or Sats from others.  

From a technical perspective, a wallet is an **application** that does not contain coins, but pairs of private/public keys and addresses to access them on the bitcoin blockchain and to create and sign transactions.

Technically "wallet" refers to the files or simple databases storing such information.

There are many brands and types of bitcoin wallets, just like there are many brands of web browsers that vary in quality, performance, security, privacy, and reliability. 

The reference implementation is the so called ["Satoshi Client" or "Bitcoin Core,"](../B/BitCoin%20Core.md), derived from Satoshi Nakamoto's original implementation.

The most simply Wallet type today is a MobileApp (like for instance the Speed Wallet we have setup at [Day One of the Journey](../../../INFO/Training/BitCoin%20Journey/Day%201/_Notes%20for%20Day%201%20and%20following%20of%20the%20365%20BitCoin%20Journey.md)) that can be setup in minutes. 

If a user loses their wallet (resp. the device with the wallet application), they can use a mnemonic phrase of 24 words, known as a [seed phrase](../S/Seed.md) - or simply "seed", to restore the wallet whenever and on whatever device they want. 

## Bitcoin Address with QR Code
The most important part of a wallet is its [bitcoin address](../A/Address.md) such as: `1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK`. 

Next to it we normally find a **QR code** that can be scanned by a smartphone camera. 

**Tip**: Tapping the QR code on the screen might magnify it for easier scanning.

> <span style="color:red; font-weight:bold">ACHTUNG</span>: 
Keeping private keys and seed phrases secure is essential!

### Address Generation
Wallet application randomly generated a private key (described in more detail in [private_keys]()) together with its corresponding bitcoin address (which is the public key). 

At this point, a bitcoin address is not known to the bitcoin network or "registered" with any part of the bitcoin system. 

A bitcoin address at this stage is simply a number, that corresponds to a digital key, that one can use to control access to funds. 

It was generated independently by the wallet without reference or registration with any service and not intefearing with the blockchain. 

In fact, in most wallets, there is no association between the bitcoin address and any externally identifiable information including the user’s identity. 

Until the moment this address is referenced as the recipient of value in a transaction posted on the bitcoin ledger, the bitcoin address is simply part of the vast number of possible addresses that are valid in a bitcoin address space. 

Only once it has been associated with a transaction it become part of the known addresses in the network. Before it is just a locally generated but otherwise totally unknown number to the world. 

-> for more details see -> [Address](../A/Address.md)

## UTXOs in Bitcoin Wallets
Eine Wallet speichert keine Bitcoins, sondern managed die mit einer bestimmten Addresse assozierten UTXOs: 

1. **Konto**: Der in einer Wallet gespeicherte Wert (resp. der für eine Transaktion zur Verfügung stehende Betrag) ist die Summe aller darin enthaltenen UTXOs (resp. die Summe aller mit der Wallet-Addresse assoziierten UTXOs). 

2. **Transaction**: When you initiate a transaction, your wallet software selects appropriate UTXOs to use as inputs where their sum is equal or higher the amount of the "money" sent + transaction-fees.

3. **Retourgeld**: If the selected UTXOs exceed the amount you want to send, your wallet creates a change output back to one of your addresses.

4. **Konsolidierung**: Ab und zu werden die UTXOs mit kleinen Beträgen zu einem grösseren UTXO zusammengefasst um so Transaktionsgebühren zu sparen. 

5. **Privacy**: Fortgeschrittene wallets wit z.B. "CoinJoin" können UTXOs von mehreren Usern zusammenlegen, um so die Anonymität zu wahren, resp. Absender und Empfänger von Transaktionen zu verschleiern. 

## Wallets gestalten Transaktionen "behind the scene"
All the logic for selecting appropriate inputs and outputs to build a transaction is normally hidden by the wallet. Users  only specify a destination and an amount, and the rest happens in the wallet application without seeing the details. Importantly, a wallet application can construct transactions even if it is completely offline. Like writing a check at home and later sending it to the bank in an envelope, the transaction does not need to be constructed and signed while connected to the bitcoin network.

## Choosing a Bitcoin Wallet
Bitcoin wallets are one of the **most actively developed applications** in the bitcoin ecosystem and where a new wallet is probably being developed right now, **several wallets from last year are no longer actively maintained**. 

Many wallets focus on specific platforms or specific uses and some are more suitable for beginners while others are filled with features for advanced users. 

However, **moving keys or seeds between bitcoin wallets is relatively easy**. So it is worth trying out several wallets until you find your personal best.

We can categorize bitcoin wallets according to their type, platform and function:

### 1. Non-Determistic versus Seed Wallets

<span style="color:red; font-weight:bold">ACHTUNG</span>: 
**The use of nondeterministic wallets is discouraged for anything other than simple tests**. They are simply too cumbersome to back up and use. Instead, use an industry-standard–based HD wallet with a mnemonic seed for backup.

#### Nondetermistic Wallets (outdated)
In a **nondeterministic wallet each key is independently generated** from a random number. The keys are not related to each other. This type of wallet is also known as a **JBOK** wallet from the phrase `"Just a Bunch Of Keys."`

#### Determistic or Seeded Wallets
In a deterministic wallet - also called seeded wallet -  **all the keys are derived from a single master key**, known as the [seed](../S/Seed.md), through the use of a one-way hash function. 

All the keys in this type of wallet are related to each other and can be generated again if one has the original [seed](../S/Seed.md).

There are a number of different key derivation methods used in deterministic wallets. The most commonly used derivation method uses a tree-like structure and is known as a `hierarchical deterministic` or `HD wallet`.

The seed is a randomly generated number encoded as a set of 24 English words, also known as mnemonic code words. 

This seed then is combined with other data, such as an index number or "chain code" (see HD Wallets (BIP-32/BIP-44)) to derive the private keys from which the public keys and addresses will be derived again.

In a deterministic wallet, the seed is sufficient to recover all the derived keys, and therefore a single backup at creation time is sufficient. 

The seed is also sufficient for a wallet export or import, allowing for easy migration of all the user’s keys between different wallet implementations. 

#### HD Wallets (BIP-32/BIP-44)
The most advanced form of deterministic wallets is the HD wallet defined by the BIP-32 standard. 

HD wallets contain keys derived in a tree structure, such that a parent key can derive a sequence of children keys, each of which can derive a sequence of grandchildren keys, and so on, to an infinite depth. This tree structure is illustrated in Type-2 HD wallet: a tree of keys generated from a single seed.

![HD Wallets](../zPIC/HD%20Wallets.png)

The tree structure can be used to express additional organizational meaning, such as when a specific branch of subkeys is used to receive incoming payments and a different branch is used to receive change from outgoing payments. 

Branches of keys can also be used in corporate settings, allocating different branches to departments, subsidiaries, specific functions, or accounting categories.

The second advantage of HD wallets is that users can create a sequence of public keys without having access to the corresponding private keys. 

This allows HD wallets to be used on an insecure server or in a receive-only capacity, issuing a different public key for each transaction. The public keys do not need to be preloaded or derived in advance, yet the server doesn’t have the private keys that can spend the funds.


### 2. Platform Types
Bitcoin wallets can be categorized according to the **platform** the application is run upon: **Desktop, Mobile, Web, Hardware, Paper, ColdStorage**:

#### Desktop
A desktop wallet was the first type of bitcoin wallet created as a reference implementation and many users run desktop wallets for the features, autonomy, and control they offer. Running on general-use operating systems such as Windows and Mac OS has certain security disadvantages however, as these **platforms are often insecure and poorly configured**.

#### Mobile
A mobile wallet is the **most common type of bitcoin wallet**. Running on smart-phone operating systems such as Apple iOS and Android, these wallets are often a **great choice for new users**. Many are designed for simplicity and ease-of-use, but there are also fully featured mobile wallets for power users.

#### Web
Web wallets are **accessed through a web browser** and store the user’s **wallet on a server owned by a third party**. This is similar to webmail in that it relies entirely on a third-party server. Some of these services operate using client-side code running in the user’s browser, which keeps control of the bitcoin keys in the hands of the user. Most, however, present a compromise by taking control of the bitcoin keys from users in exchange for ease-of-use. It is **inadvisable to store large amounts of bitcoin on third-party systems**.

#### Hardware 
Hardware wallets are devices that operate a secure self-contained bitcoin wallet on special-purpose hardware. They are **operated via USB with a desktop web browser or via near-field-communication (NFC) on a mobile device**. By handling all bitcoin-related operations on the specialized hardware, these wallets are **considered very secure and suitable for storing large amounts of bitcoin**.

#### Paper wallet / Cold Storage
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
