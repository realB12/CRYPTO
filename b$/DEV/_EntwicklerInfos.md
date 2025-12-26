# BitCont Entwickler-Infos

* [GitHub Repo](https://github.com/bitcoin/bitcoin)
* [Bitcoin Wiki](https://en.bitcoin.it/wiki/Main_Page)
* [Satoshis Version v0.1 Code on Github Mirror](https://github.com/Maguines/Bitcoin-v0.1)
* [Bitcoin Whitepaper](https://bitcoin.org/bitcoin.pdf)

* [A Hacker’s Guide to Bitcoin: Exploring Bitcoin by Command Line](https://dev.to/kniraj/a-hackers-guide-to-bitcoin-exploring-bitcoin-by-command-line-part-1-536i)

* [The Bitcoin Source Code: A Guided Tour - Part 1, Block Time and Spacing](https://www.youtube.com/watch?v=duAcEElZpNk&list=PLGIz-blhWiP80wXffE1nDQz_BKMhUSBDF)

Erste Anlaufstelle und Quelle der Wahrheit für Entwickler ist immer das öffentlich zugängliche [BitCoin GitHub Repo](https://github.com/bitcoin/bitcoin)

The contribution workflow is described in [CONTRIBUTING.md](https://github.com/bitcoin/bitcoin/blob/master/CONTRIBUTING.md) and useful hints for developers can be found in [doc/developer-notes.md](https://github.com/bitcoin/bitcoin/blob/master/doc/developer-notes.md).

## Warum selber entwickeln
Most developers first encounter Bitcoin through polished mobile wallets or sleek web interfaces and so they miss the fundamental mechanics that make everything work.

As programmers, we understand that true mastery comes from getting our hands dirty with the underlying systems. When you run your own Bitcoin node and interact with it directly via the command line, you're not just using Bitcoin — you're speaking its native language.

This guide will take you from spinning up your first Bitcoin node to understanding UTXOs, crafting transactions, and managing multiple wallets. By the end, you'll have the foundation needed to build Bitcoin applications.

## BitCoin Core (Version 0.11)
Bitcoin Core is the GitHub hosted OpenSource sofware, that connects to the Bitcoin peer-to-peer network to download and fully validate blocks and transactions. It also includes a wallet and graphical user interface, which can be optionally built.

Further information about Bitcoin Core is available in the [GitHub Repo](https://github.com/bitcoin/bitcoin) in the `/doc`-folder.

BitCoin Core is written in "flat" C++ (without extensive use of classes, inheritance and other typical object oriented stuff), whereas the data is stored as binary-raw and - for faster accessibility - in LevelDB datasets.

### Setup
Bitcoin Core is the original Bitcoin client and it builds the backbone of the network. It downloads and, by default, stores the entire history of Bitcoin transactions, which requires several hundred gigabytes or more of disk space. Depending on the speed of your computer and network connection, the synchronization process can take anywhere from a few hours to several days or more.

To download Bitcoin Core, visit bitcoincore.org.
### Architektur

<pre>
  Validating transactions; Managing blockchain, mempool, peers  (Consensus and Policy code)
                   | 
      Scripting engine / Signatures (Consensus code)
                   | 
             Network layer  (P2P code) 
                   | 
             P2P Messages
             
 </pre>
 
### SourceCode Structure
The C++ Source code is in the `src/` directory of the repository.

Most of the code resides in the top-level directory, although there has been some effort to modularize the code base with subdirectories (wallet, consensus, primitives, etc.) Also, certain components (QT, LevelDB, etc) live in subdirectories.

Key files in the `src/` directory include: (`file.*` means the header file `[file.h]` and the source file `[file.cpp]`)


* **`net.*`**: Manages the network (peer connections, etc.).
The while(true) loop in ThreadMessageHandler controls the program's flow, signalling `main.cpp` when there is work to do.
Key dependencies: None.

* **`init.cpp`**: Initializes the node, calling functions in `main.cpp` as necessary.
Key dependencies: `main.h`

* **`main.*`**:	`main.h` declares some key global variables (`mapBlockIndex`, `chainActive`, `mempool`, etc), constants, and functions.
`main.cpp` is the program's longest source file (5,237 lines).
`main.cpp` has most of the key functions for managing the blockchain, such as connecting, disconnecting, validating and storing blocks; identifying a certain block as the tip of the longest chain; and so forth.
The "**entry point**" for most of the code is `ProcessMessages` (which listens for a signal from the message-handling thread.).

Some of the code is run during initialization, called directly from `init.cpp`.
Key dependencies: net.h

* **`chain.*`**: The header file (`chain.h`) is the more notable of the two, as it declares the type definitions for the metadata about the block (`CBlockIndex`) and the longest blockchain (`CChain`).
`chain.cpp` contains a few handy functions for managing the blockchain (e.g., locating blocks and finding a fork point between two chains.)

* **`coins.*`**: The header file declares a CCoin, which is, conceptually, "a bitcoin." The source file contains methods for manipulating coins (retrieving, spending, etc.)

* **`miner.*`**: Contains the mining code, including block creation and generating new bitcoins.


## Datastructure
1. The 100% complete amount of trasactions are stored in a raw, non readable format on disk. 

2. For performance reasons an Index, State and Rollback-Data are written in parallel into LevelDB datasets (which could be regenerated from the raw data). 
Technically we have basically four datasets, one in Raw and 3 in LevelDB format: 

* **`blocks/blk*.dat:`**: the actual Bitcoin blocks, in network format, dumped in raw on disk. They are **only needed for rescanning missing transactions** in a wallet, reorganizing to a different part of the chain, and serving the block data to other nodes that are synchronizing.

* **`blocks/index/*`**:  this is a **LevelDB database** that contains **metadata about all known blocks**, and where to find them on disk. Without this, finding a block would be very slow.

* **`chainstate/*`**:  this is a **LevelDB database** with a compact **representation of all currently unspent transaction outputs** and some metadata about the transactions they are from. The data here is necessary for validating new incoming blocks and transactions. It can theoretically be rebuilt from the block data (see the `-reindex` command line option), but this takes a rather long time. Without it, you could still theoretically do validation indeed, but it would mean a full scan through the blocks (636 GB as of January 2025 / for actual size see https://www.blockchain.com/charts/blocks-size) for every output being spent.

* **`blocks/rev*.dat`**:  these contain **"undo" data**. You can see blocks as 'patches' to the chain state (they consume some unspent outputs, and produce new ones), and see the undo data as reverse patches. They are necessary for rolling back the chainstate, which is necessary in case of reorganisations.

Note here that the **LevelDB's are redundant** in the sense that they **can be rebuilt from the block data** . But validation and other operations would become intolerably slow without them.

See here: [StackExchange post by Pieter Wuille (2013)](https://bitcoin.stackexchange.com/questions/11104/what-is-the-database-for?rq=1)

