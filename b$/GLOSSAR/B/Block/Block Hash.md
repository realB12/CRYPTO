# BlockHash = BlockID

* [SHA 256](../S/SHA-256.md) / [H A S H256](../H/HASH256.md)
* [Byte Order](ByteOrder.md)


![Block Hash](../zPIC/BlockHash.png)

Der BlockHash ist der **Hashwert der im Blockheader vorhandenen Daten**, und wird auch als eindeutige **ID** des Blocks in der Blockchain, resp. als BlockID verwendet.

Die Transaktionen sind insofern indirekt gehashed, als dass diese in einem sogenannten Merkle-Tree zusammengefasst werden und der dabei ermittelte Hashwert (Merkle-Root) im [Block Header](Block%20Header.md) (an der dritten Stelle) eingetragen wird.

Dieser Hashwert wird beim [Mining](../M/Mining.md) berechnet, und zwar so, dass durch die Variation einer als [Nonce](../N/Nonce.md) bezeichneten Variable des BlockHeaders, dieser Hashwert kleiner als ein bestimmter [Target](../T/Target.md)-Wert ist 

**Tip**: weil der Blockhash kleiner als der [Target](../T/Target.md)-Wert ist, stehen je nach verwendeter [Byte Order](ByteOrder.md) entweder am Anfange (im Blockchain Explorer angezeigte Reverse Order) oder am Ende des Outputs ("Normal Order" bei Betrachtung der Blockdaten) viele Nullen: 

`000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f`

Scheinbar ist der Hashwert eines jeden Blocks immer eindeutig, resp. gibt es keine zwei Blocks deren Hashwert identisch sein können. 
??? Warum ???


## HASH256 
Die Hashfunktion um den Blockheader zu hashen ist der sogenannte **`HASH256`** Algorithymus - eine Abkürzung für "`Double SHA-256`", "double-SHA256" oder "SHA-256d" -  wo der Blockheader mit der `SHA-256` Hash Funktion gehashed wird um dann das Resultat nochmals mit dem `SHA-256` Algo zu hashen.

<span style="color:red; font-weight:bold">ACHTUNG</span>: 
More recent changes to Bitcoin have started to use a single round of [SHA 256](../S/SHA-256.md) instead of HASH256:

### Wieso zweimal hashen? 
Satoshi was probably concerned about something called a length extension attack, and it has been recommended in some literature (e.g. Cryptography Engineering) to use double-SHA256 to protect against it.

Either way, hashing data twice is now just a quirk of Bitcoin.

If you designed Bitcoin from scratch today there would be no benefit to using double-SHA256. In fact, recent upgrades to Bitcoin now favor using single-SHA256 where possible (e.g. script hashes in P2WSH).
