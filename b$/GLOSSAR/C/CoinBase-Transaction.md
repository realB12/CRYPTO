# Coinbase Transaktion
"Der Lohn des Miners"

Die sogenannte Coinbase-Transaktion ist die **erste Transaktion eines [Blocks](../B/Block.md)**. 

Sie wird dort vom Miner (im "candiate Blpock") platziert, um so bei erfolgreichem Minen des Blocks den sogenannten die Mining- und Transaktionsfees zu erhalten.

Dieser Transaktionstyp hat demzufolge lediglich einen Output aber keinen keinen Input (resp. technisch gesehen einen leeren Input).


Solange die 21 Millionen BTC noch nicht erreicht sind, erhöht sich bei jeder Coinbase-Transaktion die GesamtMenge der verfügbaren BTCs.

## BlockReward 
Der sogenannte [Block Reward](../B/BlockReward.md) ist die Menge **Bitcoins die ein Miner für das Minen seines Blocks erhält** und damit die Summe aus [Block Subsidy](../B/BlockSubsidy.md) (neu erstellter Bitcoins gem. HalvingRules) und der Summe aller [Transaction Fees](../T/TransactionFee.md) der im Block eingetragenen Transaktionen. 

Mit fortschreitendem Halving werden sich Miner mit Transactionfees begnügen müssen.    

### Cooldown Phase
Der Output einer Coinbase Transaction, und damit der BlockReward, sind für 100 Blocks gesperrt, resp. müssen 100 neue Blocks erstellt worden sein, bis BlockRewards ausgegeben werden dürfen. 