# Block
Jeder, ca. 1 MB grosse BitCoin-Block umfasst einen [Block Header](Block%20Header.md) und die vollständigen Daten von maximal 2000 [Transaktionen](../T/Transaction.md). 

Durschnittlich wird alle 10 Minuten ein neuer Block erstellt, womit im Schnitt "nur" alle 3 Sekunden eine [Transaktionen](../T/Transaction.md) in die Blockchain eingehängt werden kann.

![Block Structure](../zPIC/BlockStructure.png)

> Die BlockSize wurde bewusst auf 2000 Transaktionen limitiert, um die Transaktionen so besser dezentral zu verteilen, resp. um damit die Dezentralität sicher zustellen. 

## Block Header

-> [Block Header Details](Block%20Header.md)

Zuoberst im Block angesiedelt enthält der [Block Header Details](Block%20Header.md)   

1. **allgemeine Information zum Block** wie die Versionsnummer, die sogenannte [Nonce](../N/Nonce.md) oder die Zeit  

2. Die **BlockID des letzten Blocks** (daher der Name Blockchian).   

3. Verweise auf die im Block enthaltenen Transaktionen (Merkle Root)

## Block-Header-Struktur: 
---
<code>
<span style="color:violet">01000000</span> 
<span style="color:grey">6fe28c0ab6f1b372c1a6a246ae63f74f931e8365e15a089c68d6190000000000</span> 
<span style="color:green">982051fd1e4ba744bbbe680e1fee14677ba1a3c3540bf7b1cdb606e857233e0e</span>
<span style="color:indigo">61bc6649</span> 
<span style="color:pink">ffff001d</span>
<span style="color:amber">01e36299</span> 
<span style="color:fuchsia">01</span>
<span style="color:gray">01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff0704ffff001d0104ffffffff0100f2052a0100000043410496b538e853519c726a2c91e61ec11600ae1390813a627c66fb8be7947be63c52da7589379515d4e0a604f8141781e62294721166bf621e73a82cbf2342c858eeac00000000</span>
</code>

---

This block only contains just one single transaction, but the basic structure is the same for every block.

![block Structure 2](../zPIC/blockStructure2.png)

* <span style="color:violet; font-weight:bold">Version</span>: Die **Versionsnummer** des Blocks. Ist mehr oder weniger eine Konstante ohne grossen Einfluss auf die Funktionalität, die z.T. auch für Experimentre missbraucht wurde `(4 bytes, little-endian)`

* <span style="color:grey; font-weight:bold">Vorangehende Block ID</span>: Die 32 Byte als 64 Hexzahlen dargestellte [BlockID](Block%20Hash.md) des vorangehenden Blocks der Blockchain `(32 bytes)`

* <span style="color:green; font-weight:bold">Merkle Root</span>: Fingerabdruck aller jeweils paarweise als [Merkle Tree](../../M/Merkle%20Root.md) gehaschter Transaktionen `(32 bytes)`

* <span style="color:indigo; font-weight:bold">[Block Time](Block%20Time.md)</span>: Ungefähre Erstellungszeit des Blocks im Unix Timestamp Format (Anzahl Sekunden seit dem 1. Januar 1970) `(4 bytes)`

* <span style="color:pink; font-weight:bold">Bits</span>:  a compact representation of the [Target](../../T/Target.md) at the time the block was mined. Beispiel: `ffff001d` (i.e. `1d00ffff` in little-endian)  `(4 bytes)`

* <span style="color:amber; font-weight:bold">Nonce</span>: Die [Nonce-Zahl](../../N/Nonce.md), die bewirkt dass der [Block Hash](Block%20Hash.md) kleiner als das [Target](../../T/Target.md) wird.  `(4 bytes)`


* <span style="color:fuchsia; font-weight:bold">Anzahl Transaktionen</span>: number of upcoming transactions in the block. It's a compact size field, so it's usually either 1 or 3 bytes in size (depending on how many transactions are in the block). (`compact size`)

<span style="color:gray; font-weight:bold">01000000010000000000000000000000000000000000000000000000000000000000000000ffffffff0704ffff001d0104ffffffff0100f2052a0100000043410496b538e853519c726a2c91e61ec11600ae1390813a627c66fb8be7947be63c52da7589379515d4e0a604f8141781e62294721166bf621e73a82cbf2342c858eeac00000000</span>


## Mining

Miners repeatedly hash this block header to try and get a result below the current target. If you can get a block hash below the target, the block can be added on to the blockchain. 

## Prioritäten. 
This is why miners will **add transactions with the highest fees first**, whereas blocks with low fees will be added only, when there is some space left to fill a block over the next 10 minutes or so. 




