# Block Reward

* [Block Subsidy](BlockSubsidy.md)
* [Transaction Fee](../T/TransactionFee.md)
* [CoinBase Transaction](../C/CoinBase-Transaction.md)
* [Halving BTC](../H/Halving-BTC.md)

Der sogenannte [Block Reward](../B/BlockReward.md) ist die Menge **Bitcoins die ein Miner für das Minen seines Blocks erhält** und damit die Summe aus [Block Subsidy](../B/BlockSubsidy.md) (Anzahl neu aus dem Nichts erstellte Bitcoins gem. [HalvingRules](../H/Halving-BTC.md)) und der Summe aller [Transaction Fees](../T/TransactionFee.md) der im Block eingetragenen Transaktionen. 

Mit fortschreitendem Halving werden sich Miner mit Transactionfees begnügen müssen.    

### Cooldown Phase
Der Output einer Coinbase Transaction, und damit der BlockReward, sind für 100 Blocks, resp. maximal für 20 Stunden (durchschnittle 10 Minuten BlockTime X 100 Blocks) gesperrt, resp. müssen 100 neue Blocks erstellt worden sein, bis BlockRewards wieder ausgegeben werden dürfen. 