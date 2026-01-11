# getNewAddress 
(BitcoinCore RPC Call)

Das ***getNewAddress*-Kommando** erstellt ein ein **neues Privat/Public-Schlüsselpaar** für die aktuell aktive Wallet. 

Als Resultat wird aber nur der Public Key resp. die Empfängeradresse ausgegeben wie z.B. "***bcrt1qaa557fl8gnxq62vnncttr0s6jxyunahcmgk09c***" (an welche dir Leute, sofern Du auf der Life Blockchain bist, Geld senden können) 

Falls keine Wallet aktiv ist, wird eine Fehlermeldung angezeigt. 

## Syntax
> **getnewaddress ( "label" "address_type" )**

## Output 
ein neu generierter Public Key resp. die Empfängeradresse:

> ***bcrt1qaa557fl8gnxq62vnncttr0s6jxyunahcmgk09c***"

## Input Parameter

### #1 label (string, optional, default=””)
If ‘label’ is specified, it is added to the address book so payments received with the address will be associated with ‘label’.

It **can also be set to an empty string** *“”* to represent the default label. 

When the label does not exist, it will be created.

### #2 address_type (string, optional, default=set by -addresstype)
The address type to use. 

Options are “*legacy*”, “*p2sh-segwit*”, and “*bech32*”

## Beispiel

> **bcrt1qaa557fl8gnxq62vnncttr0s6jxyunahcmgk09c**

Beachte dass diese Adresse mit den Buchstaben *bcr* beginnt.

