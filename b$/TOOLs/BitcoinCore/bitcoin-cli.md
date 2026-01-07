# bitcoin-cli

* [BitCoinCore installieren](BitCoinCore-installieren.md)

## Was ist die BlockChain CLI?

Bitcoin-cli ist das mit dem [BitCoinCore FullNode](_BitCoinCore-FullNode.md) mitinstallierte KommandozeilenTool zum Ausführen von die lokale Blockchain betreffenden Kommandos wie das Auslesen gewisser Daten, Erstellen neuer Schlüssel etc. 

## Starten
### 1. CMD-Fenster
Unter Winows 11 mit "***CMD***" ein schwarzes Control-Fenster öffnen und das Tool mit folgenden Kommando starten: 

> bitcoin-cli

Dieses Kommando listet die Syntax und eine Kurzbeschreibung sämtlicher Parameter/Optionen, resp. prüfst Du so, ob das Tool überhaupt installiert ist. Falls nicht gehe zurück zur [BitCoinCore Installationsanleitung](BitCoinCore-installieren.md)

### 2. den BitCoin Daemon starten
Mit 
> bitcoind
Startest du den Daemon den Du wieder mit Ctrl+C beenden kannst

Falls Du ihn versuchst nochmals zu starten erhältst du eine etwas irreführende Meldung dass des Tool keinen Zugriff auf ein Verzeichnis hätte (was zwar stimmt, aber nicht auf den expliziten Mehrfachstart des Deamons verweist). 

## BlockchainInfo
Mit 

> bitcoin-cli getblockchaininfo 

erhält man den Status des lokal laufenden Bitcoin Daemons. Falls dieser nicht gestartet wurde erhält man eine Meldung dass der Server nicht gefunden wurde: 

    "bitcoind server is running and that you are connecting to the correct RPC port."

ansonsten den folgenden Output

```plaintext
{
  "chain": "main",
  "blocks": 582101,
  "headers": 582101,
  "bestblockhash": "000000000000000000165bf4a8eaa460df4752002840009c29ec0adfd9376406",
  "difficulty": 7409399249090.253,
  "mediantime": 1561321207,
  "verificationprogress": 0.9999922936147396,
  "initialblockdownload": false,
  "chainwork": "000000000000000000000000000000000000000006d23718c9e22adc4275b706",
  "size_on_disk": 257091100656,
  "pruned": false,
  "softforks": [
    {
      "id": "bip34",
      "version": 2,
      "reject": {
        "status": true
      }
    },
    {
      "id": "bip66",
      "version": 3,
      "reject": {
        "status": true
      }
    },
    {
      "id": "bip65",
      "version": 4,
      "reject": {
        "status": true
      }
    }
  ],
  "bip9_softforks": {
    "csv": {
      "status": "active",
      "startTime": 1462060800,
      "timeout": 1493596800,
      "since": 419328
    },
    "segwit": {
      "status": "active",
      "startTime": 1479168000,
      "timeout": 1510704000,
      "since": 481824
    }
  },
  "warnings": ""
}
```

These are all the details we need to identify the best block and where to find it. We can also see the size of the blockchain and various soft forks implemented.

### getmininginfo

> **getmininginfo**

returns the following object:

```plaintext
{
  "blocks": 582102,
  "difficulty": 7409399249090.253,
  "networkhashps": 6.626238141514776e+019,
  "pooledtx": 3527,
  "chain": "main",
  "warnings": ""
}
```

The blocks and difficulty values are also in the getblockchaininfo command, but here we can find:

1. **network hashes per second**
2. the **number of transactions** in the tx pool

### getpeerinfo
this finds information about the peers your node is communicating blockchain data with. 

> getpeerinfo

returns an array of objects representing peer’s nodes to which your Bitcoin Core instance is currently connected. This number generally ranges from 10–50 if you have port 8333 open.

The information returned includes:

* IP address information
* time since last sent/received
* node connected time (uptime)
* version/subversion
* additional network info

You can also use ***getconnectioncount*** to return the amount of connected nodes.

## Block Commands
To retrieve data about a block, we first need a block index or hash to identify that block. We can retrieve both values about the current best block on the chain by using the commands:

> getblockcount
to return the current best block index:

582102
or

> getbestblockhash
to return the current best block hash:

000000000000000000227508581434096917b80e3a4c981116cc8ff532aa48ef
Each block on the bitcoin blockchain has an index and a hash we can use to find details about it. Blocks can be looked up directly with the a block hash, or indirectly with a block index. For example, say we know that we want to look up the block with height (index) 530120. First type the command:

> getblockhash 530120
which returns the hash:

00000000000000000025c3a8404acf1cabc9fe0a2901f59828128c3bb16f7616
next use the getblock command to retrieve the block data:

> getblock 00000000000000000025c3a8404acf1cabc9fe0a2901f59828128c3bb16f7616
The getblock command called with a specific hash will return:

number of confirmed blocks since that block
block size
block weight
merkle root
an array of all the tx ids in the block
time when the block was mined
the block nonce
the currently difficulty
number of transactions (nTx)
the next/previous block hashes

## Transaction Commands
Bitcoin doesn’t index transactions by default. To look up transactions other than those associated with your wallet, you must first turn on indexing in the config file. Go to Settings >> Options >> Open Configuration File to open up the bitcoin configuration file (bitcoin.conf).

Get Peter Durham’s stories in your inbox
Join Medium for free to get updates from this writer.

Enter your email
Subscribe
Add the line:

txindex=1
With this command added, save the file and restart Bitcoin Core. This process can take several hours, so it is useful to setup overnight, or while you are away. Once Bitcoin Core has indexed the blockchain, any transaction can be looked up individually using the getrawtransaction and decoderawtransactioncommands.

This may seem like a tedious extra step, but keep in mind this setting is also a requirement to running a lightning node.

Now that we have an indexed bitcoin node running, lets find some transactions to decode. We can see the ids of all the transactions in the mempool with the command

> getrawmempool
this command will return an array of (usually) thousands of pending transactions currently in the mempool.

We can look up a specific transaction by selecting one of these transaction ids.

> getrawtransaction 68ecbf8b6d78db0aa4969feb65c6d600bde02f33dbc84151139964fcf448af55
this will return the raw transaction:

010000000152fb73aff8ae297ab294f0e4ddce76c63cfcdb10488582d6e7c894053a4325ea000000006b483045022100bc7852636a24fd1da1e14d04abc2c8a467b45f5f7922be47ed8cbd5f571904af0220239cb094a40a4b5d812096b82354bc4470823aeaf8658dd9c71a43327f4a29cd012102a1703f0092c3de5106379bce7fbf8689263e31ea8ed41723c8533c28de62cf16ffffffff02197c0800000000001976a914bf1cccd8e4256b5258ce66849e05f4a59f1edb8d88ac0000000000000000536a4c500003ad250002c5239e661ae029df7a66f02955e7a322413e8fbeb6448072b87b7a7c1304ac111052848276bb2bbbf5ad6612436a5d0fe8370702bd541feb2ffa416fa6194a21eb30a2be3060387bf87100000000
This hexadecimal string, let’s call it hex, is the encoded transaction and can be decoded using:

> decoderawtransaction hex
This command returns an object with details about that transaction


{
  "txid": "68ecbf8b6d78db0aa4969feb65c6d600bde02f33dbc84151139964fcf448af55",
  "hash": "68ecbf8b6d78db0aa4969feb65c6d600bde02f33dbc84151139964fcf448af55",
  "version": 1,
  "size": 284,
  "vsize": 284,
  "weight": 1136,
  "locktime": 0,
  "vin": [
    {
      "txid": "ea25433a0594c8e7d682854810dbfc3cc676cedde4f094b27a29aef8af73fb52",
      "vout": 0,
      "scriptSig": {
        "asm": "3045022100bc7852636a24fd1da1e14d04abc2c8a467b45f5f7922be47ed8cbd5f571904af0220239cb094a40a4b5d812096b82354bc4470823aeaf8658dd9c71a43327f4a29cd[ALL] 02a1703f0092c3de5106379bce7fbf8689263e31ea8ed41723c8533c28de62cf16",
        "hex": "483045022100bc7852636a24fd1da1e14d04abc2c8a467b45f5f7922be47ed8cbd5f571904af0220239cb094a40a4b5d812096b82354bc4470823aeaf8658dd9c71a43327f4a29cd012102a1703f0092c3de5106379bce7fbf8689263e31ea8ed41723c8533c28de62cf16"
      },
      "sequence": 4294967295
    }
  ],
  "vout": [
    {
      "value": 0.00556057,
      "n": 0,
      "scriptPubKey": {
        "asm": "OP_DUP OP_HASH160 bf1cccd8e4256b5258ce66849e05f4a59f1edb8d OP_EQUALVERIFY OP_CHECKSIG",
        "hex": "76a914bf1cccd8e4256b5258ce66849e05f4a59f1edb8d88ac",
        "reqSigs": 1,
        "type": "pubkeyhash",
        "addresses": [
          "1JRWZiGXAm9n3b5FXopkW1wPifAtXwfjWC"
        ]
      }
    },
    {
      "value": 0.00000000,
      "n": 1,
      "scriptPubKey": {
        "asm": "OP_RETURN 0003ad250002c5239e661ae029df7a66f02955e7a322413e8fbeb6448072b87b7a7c1304ac111052848276bb2bbbf5ad6612436a5d0fe8370702bd541feb2ffa416fa6194a21eb30a2be3060387bf871",
        "hex": "6a4c500003ad250002c5239e661ae029df7a66f02955e7a322413e8fbeb6448072b87b7a7c1304ac111052848276bb2bbbf5ad6612436a5d0fe8370702bd541feb2ffa416fa6194a21eb30a2be3060387bf871",
        "type": "nulldata"
      }
    }
  ]
}
Here we have the

transaction size
transaction weight
input details
output details and value/s
There is plenty of information here, but notice that transaction above doesn’t have any values associated with its input. The block which the transaction was confirmed in isn’t available either in the transaction. These details are missing on purpose to keep the blockchain from repeating unnecessary data. We do have enough information however to look up the amounts received in every bitcoin transaction, and the ability to look up previous transaction outputs. Using these commands is enough to build a basic block explorer.

## Summary
Note that these commands can be accessed by a multitude of different programming languages to build APIs and applications which use and implement transaction logic. It is possible to run a business from your own node, and track each transaction programmatically through an application with a custom user interface.