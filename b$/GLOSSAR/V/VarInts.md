# Varints (Variable Integers Format)

Varints sind Integer von 0 bis 2^64 – 1 und werden je nach Grösse der Zahl nach den folgenden Regeln in 1,2,4 oder 8 Bytes gespeichert. 

* **0 bis 253** wird "normal" in EINEM Byte gespeichert (100 → 0x64).

* **254 bis 65'535 (2^16–1)** starten im ersten byte mit 253 resp. (*fd*) und codieren die Zahl dann in **2 bytes** im Little-Endian Format bei dem die kleineren Ziffern links, resp. die Nullen rechts stehen (255 → 0xfdff00, 555 → 0xfd2b02).

* ***2^16* bis *2^32*** – 1 starten mit 254 resp. (*fe*) im ersten Byte und sind dann in gesamthaft **4 bytes** in little-endian Notation codidiert (70015 → 0xfe7f110100).

* ***2^32* bis *2^64-1*** starten mit 255 byte (*ff*) im ersten Byte und sind dann in gesamthaft **8 bytes** in little-endian Notation codidiert  (e.g., 18005558675309 → 0xff6dc7ed3e60100000).