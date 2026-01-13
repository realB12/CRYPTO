# sendToAddress (BTC an eine Empfängeradresse senden)

Sendet BTCs an eine Empfängeradresse

## Syntax

> sendtoaddress "address" amount ( "comment" "comment_to" subtractfeefromamount replaceable conf_target "estimate_mode" avoid_reuse fee_rate verbose )

## Kontext
Mit diesem Kommando erstellt man eine neue Transaktion, in welcher BTCs von einer Senderadressse an eine Empfängeradresse überwiesen werden. 

Diese Transaktion geht aber zuerst nur mal in den Mempool. Damit sie in die Blockchain geschrieben und dort bestätigt werden kann muss sie zuerst in einem neu zu erstellenden Block erfasst werden um dann als Bestandteil dieses Blocks auf der Blockchain verifiziert zu werden. Auf der Testchain heisst das, dass die Transaktion erst dann in der Wallet erscheint wenn nach dieser Transaktionserstellung mittels [generate To Address](../G/generateToAddress.md) ein neuer Block erstellt wird, der dann diese "pending" Transaktions aus dem MemPol in die den Block pacht und sie damit in die Blockchain schreibt. 




Tip: Requires wallet passphrase to be set with walletpassphrase call if wallet is encrypted.

## Argumente
* **#1 address**: (string, required)
Die BitCoin Empfängeradresse an welche die im nächsten Argument benannten BitCons gesendet werden sollen. ACHTUNG: Wird diese falsch eingegeben sind die gesendeten Bitcoins ev. für immer verloren!

* **#2 - amount**: (numeric, required)

The amount in BTC to send. eg 0.1

* **#3 - comment**: (string, optional)

A comment used to store what the transaction is for.
This is not part of the transaction, just kept in your wallet.

* **#4 - comment_to**: (string, optional)

A comment to store the name of the person or organization
to which you’re sending the transaction. This is not part of the transaction, just kept in your wallet.

* **#5 - subtractfeefromamount**: (boolean, optional, default=false)

The fee will be deducted from the amount being sent.
The recipient will receive less bitcoins than you enter in the amount field.

* **#6 - replaceable**: (boolean, optional, default=wallet default)

Allow this transaction to be replaced by a transaction with higher fees via BIP 125

* **#7 - conf_target**: (numeric, optional, default=wallet -txconfirmtarget)

Confirmation target in blocks

* **#8 - estimate_mode**: (string, optional, default=unset)

The fee estimate mode, must be one of (case insensitive):
“unset” “economical” “conservative”

* **#9 - avoid_reuse**: (boolean, optional, default=true)

(only available if avoid_reuse wallet flag is set) Avoid spending from dirty addresses; addresses are considered
dirty if they have previously been used in a transaction.

## Result 
**Mit "verbose" = false**, (resp. falls die "verbose" Option nicht explizit auf true gesetzt wurde) gibt der Call lediglich **die TransaktionsID** der damit erstellten Transaktion wieder, resp. den sie representierenden  hexadezimalen String.

**Mit "verbose" = true**, (falls das "verbose" EXPLIZIT gesetzt wurde) gibt der Call folgendes JSON Objekt zurück: 

```json
{                          
  "txid" : "hex",          (string) Die TransaktionsID wie oben erklärt
  "fee reason" : "str"     (string) The transaction fee reason.
}
```

Mit der TransaktionsID kann man sich die Details dieser Transaktion mittels [get Transaction](../G/getTransaction.md)-Kommando wie folgt ausdrucken:

```json
{                                         
  "amount" : n,                            (numeric) The amount in BTC
  "fee" : n,                               (numeric) The amount of the fee in BTC. This is negative and only available for the
                                           'send' category of transactions.
  "confirmations" : n,                     (numeric) The number of confirmations for the transaction. Negative confirmations means the
                                           transaction conflicted that many blocks ago.
  "generated" : true|false,                (boolean) Only present if transaction only input is a coinbase one.
  "trusted" : true|false,                  (boolean) Only present if we consider transaction to be trusted and so safe to spend from.
  "blockhash" : "hex",                     (string) The block hash containing the transaction.
  "blockheight" : n,                       (numeric) The block height containing the transaction.
  "blockindex" : n,                        (numeric) The index of the transaction in the block that includes it.
  "blocktime" : xxx,                       (numeric) The block time expressed in UNIX epoch time.
  "txid" : "hex",                          (string) The transaction id.
  "walletconflicts" : [                    (json array) Conflicting transaction ids.
    "hex",                                 (string) The transaction id.
    ...
  ],
  "time" : xxx,                            (numeric) The transaction time expressed in UNIX epoch time.
  "timereceived" : xxx,                    (numeric) The time received expressed in UNIX epoch time.
  "comment" : "str",                       (string) If a comment is associated with the transaction, only present if not empty.
  "bip125-replaceable" : "str",            (string) ("yes|no|unknown") Whether this transaction could be replaced due to BIP125 (replace-by-fee);
                                           may be unknown for unconfirmed transactions not in the mempool
  "details" : [                            (json array)
    {                                      (json object)
      "involvesWatchonly" : true|false,    (boolean) Only returns true if imported addresses were involved in transaction.
      "address" : "str",                   (string) The bitcoin address involved in the transaction.
      "category" : "str",                  (string) The transaction category.
                                           "send"                  Transactions sent.
                                           "receive"               Non-coinbase transactions received.
                                           "generate"              Coinbase transactions received with more than 100 confirmations.
                                           "immature"              Coinbase transactions received with 100 or fewer confirmations.
                                           "orphan"                Orphaned coinbase transactions received.
      "amount" : n,                        (numeric) The amount in BTC
      "label" : "str",                     (string) A comment for the address/transaction, if any
      "vout" : n,                          (numeric) the vout value
      "fee" : n,                           (numeric) The amount of the fee in BTC. This is negative and only available for the
                                           'send' category of transactions.
      "abandoned" : true|false             (boolean) 'true' if the transaction has been abandoned (inputs are respendable). Only available for the
                                           'send' category of transactions.
    },
    ...
  ],
  "hex" : "hex",                           (string) Raw data for transaction
  "decoded" : {                            (json object) Optional, the decoded transaction (only present when `verbose` is passed)
    ...                                    Equivalent to the RPC decoderawtransaction method, or the RPC getrawtransaction method when `verbose` is passed.
  }
}
```





## Beispiele 

Sende 0.1 BTC an die EmpfängerAdresse "bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl":

> sendtoaddress "bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl" 0.1


Send 0.1 BTC with a confirmation target of 6 blocks in economical fee estimate mode using positional arguments:

bitcoin-cli sendtoaddress "bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl" 0.1 "donation" "sean's outpost" false true 6 economical
Send 0.1 BTC with a fee rate of 1.1 sat/vB, subtract fee from amount, BIP125-replaceable, using positional arguments:

bitcoin-cli sendtoaddress "bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl" 0.1 "drinks" "room77" true true null "unset" null 1.1
Send 0.2 BTC with a confirmation target of 6 blocks in economical fee estimate mode using named arguments:

bitcoin-cli -named sendtoaddress address="bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl" amount=0.2 conf_target=6 estimate_mode="economical"
Send 0.5 BTC with a fee rate of 25 sat/vB using named arguments:

bitcoin-cli -named sendtoaddress address="bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl" amount=0.5 fee_rate=25
bitcoin-cli -named sendtoaddress address="bc1q09vm5lfy0j5reeulh4x5752q25uqqvz34hufdl" amount=0.5 fee_rate=25 subtractfeefromamount=false replaceable=true avoid_reuse=true comment="2 pizzas" comment_to="jeremy" verbose=true

