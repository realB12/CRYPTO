# Merkle Root
"Fingerprint for the transactions in a block"

* [Details](https://learnmeabitcoin.com/technical/block/merkle-root/)

![Merkle Root](../zPIC/Merkle%20Root.png)

A merkle root is created by hashing together pairs of TXIDs to get a short and unique fingerprint for all the transactions in a block.

This merkle root is placed in a block header to prevent the contents of the block from being tampered with later on. So if someone tries to add or remove a transaction from the block, the merkle root for the transactions inside the block will no longer match the merkle root inside the block header.

In other words, the merkle root is what connects the block header to the transactions in the block.