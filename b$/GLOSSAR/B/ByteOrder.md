# Natural versus Reverse Byte Order

* [hexadecimale Darstellung von HalfBytes](../H/hexadecimal.md)

* [Ausführliche Beschreibung mit Beispielen](https://learnmeabitcoin.com/technical/general/byte-order/#natural-byte-order)

Weil beim [Minen](../M/Mining.md) nur BlockIDs gültig sind, deren Hash am Ende mehrere Nullen aufweisen (siehe -> [Nonce](../N/Nonce.md) und [Target](../T/Target.md)), aber das weniger gut lesbar ist, als wenn diese am Anfang stehen, werden diese Hashes in den [Blocks](Block.md) mit den Nullen am Ende (im sogenannten "Normal Byte Order" Format) gespeichert, aber in BitCoin-Tools wie z.B. dem Explorer in umgekehrter Reihenfolge, resp. mit führenden Nullen verwemdet. 

Das ist zwar gewöhnungsbedürftig und scheinbar überflüssig, aber gehört nun mal zu den Eigenheiten (Quirk) der BitCoin Welt die nicht hinterfragt werden müssen.  

## Intro
Der [SHA 256](../S/SHA-256.md) Algorithmus erzeugt einen 256 Bit resp. 32 Byte lange String, welcher [hexadezimal](../H/hexadecimal.md) mit 64 Zeichen wie folgt dargestellt werden kann:  

`6fe28c0ab6f1b372c1a6a246ae63f74f931e8365e15a089c68d6190000000000`

Dieser "HexString" kann auch als Zahl interpretiert werden, welche natürlich unterschiedliche Werte hätte, je nachdem ob er von vorne oder von hinten her gelesen wird, resp. je nachdem ob die die "Einser", resp. die "Zahlen" mit der tiefsten Wertigkeit an erster oder an letzter Stelle stehen. 

Bei den ersten Computern standen die kleinsten Wert links (während sie nach unserem modernen Verständnis rechts stehen). Dieses Interpretationsformat wurde als "Little Endian" bezeichnet, und wurde vermutlich auch von Nakamoto so interpretiert, als er beschloss, dass die - aus unserer heutigen Sicht "letzten" Stellen rechts in der BlockID Nullen sein müssten, und damit nur Hashes das "Puzzle" lösen, deren Werte - in der Little Endian Notation von links her gelesen - "kleiner" sind als das [Target](../T/Target.md), bzw. auf der rechten Seite soviele Nullen haben müssen wie dieses. 

![Natural Byte Order](../zPIC/NaturalByteOrder.png)

<span style="color:red; font-weight:bold">TIP</span>: 
> Die ganze Verwirrung um Natural und Revers-Order fällt weg, wenn man einfach weiss, dass [Nonces](../N/Nonce.md) so lange mutiert werden, bis der [Block Hash](Block%20Hash.md) am Ende gleich viele Nullen hat, wie das [Target](../T/Target.md)! und dass sämtliche Hashes as is und damit in den Blocks mit den Nullen am Ende gespeichert werden, und dieselben Hashes lediglich in interaktiven BitCointTools - der besseren Lesbarkeit wegen - in umgekehrter Reihenfolge, und deshalb mit führenden Nullen angezeigt werden. 

> Dass die Tools dann "andere" Hashes anzeigen als man in den Daten findet gehört zu den Quirks der Bitcoin-Welt und muss nicht länger diskutiert werden. 


## Natural Byte Order
Bei der Natural Byte Order - auch "Little Endian" genannt - werden Bytes wie Buchstaben von links nach rechts gelesen. Dabei hat, wenn man den ByteString als Zahl interpretiert, das erste Byte links die TIEFSTE Wertigkeit, resp. entspricht die erste HexZahl links den "Einsern": 

<pre>
┌ lowest value byte  
│   
6fe28c0ab6f1b372c1a6a246ae63f74f931e8365e15a089c68d6190000000000 (BlockHash) 

0000000000000000000000000000000000000000000000000000ffff00000000 (Target)

</pre>


## Reverse Byte Order. 
Reverse Byte Order sind dieselben HexZahlen in umgekehrter Reihenfolge dargestellt, wobei nun aber die "Einser" rechts sind und man den ByteString dann auch wie eine normale Zahl lesen kann. 

Dieses Format wird wegen der bessereren Lesbarkeit von BlockIDs (die Nullen am Anfang) in Blockchain Explorers und anderen BlockchainTools verwendet. 