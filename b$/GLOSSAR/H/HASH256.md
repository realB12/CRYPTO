# HASH256

* [SHA 256](../S/SHA-256.md)
* [Block Hash](../B/Block%20Hash.md)

Der **`HASH256`** Algorithmus - eine Abkürzung für "`Double SHA-256`", "`double-SHA256`" oder "`SHA-256d`" -  hashed einen maximal 264 Bit langen InputText mittels `SHA-256` Hash um den Output dann gleich nochmals mit dem `SHA-256` Algo zu hashen.

<span style="color:red; font-weight:bold">ACHTUNG</span>: 
More recent changes to Bitcoin have started to use a single round of [SHA 256](../S/SHA-256.md) instead of HASH256!

## Einsatzgebiet
Der sogenannte HASH256 Algorithmus wird im BTC-Kontext an verschiedenen Stellen verwendet: 

* Beim Minen zum Erstellen des [BlockHashes](../B/Block%20Hash.md) resp der eindeutigen [BlockID](../B/BlockID.md) an Hand der der Block in der Blockchain wieder gefunden wird. Durch die Variation der [Nonce](../N/Nonce.md) wird dieser Hash millionenfach pro Sekunde durchlaufen bis ein Hashwert gefunden wird der kleiner als ein bestimmter [TargetWert](../T/Target.md) ist. Diese BlockID wird auch verwendet um auf den letzten Block zu verweisen und damit die einzelnen Blöcke zu einer Blockchain zu verknüpfen. 

### Why do we hash twice? 
Satoshi was probably concerned about a length extension attack. However if Bitcoin would be designed from scratch again, there would be no benefit to using double-SHA256. In fact, recent upgrades to Bitcoin now favor using single-SHA256 where possible (e.g. script hashes in P2WSH).




