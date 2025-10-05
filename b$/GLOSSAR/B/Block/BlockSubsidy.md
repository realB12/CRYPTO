# Block Subsidy (Mining Reward)

* [Halving BTC](../H/Halving-BTC.md)
* [Transaction Fee](../T/TransactionFee.md)

Die sogenannte "Block Subsidy" ist die Mengen an Bitcoins die der Miner für das Erstellen und Einfügen seines Blocks in die Blockchain (-> Minen) erhält, und die damit die Gesamtmenge der verfügbaren Bitoins erhöht. 

Die ursprünglich mit 50 BTC gestartete Subsidy wird ungefähr alle 4 Jahre (resp. nach dem Minen von 210,000 blocks) halbiert und ist nach dem Erreichen der maximal 21 Millionen BTCs prkatisch gleich Null. 

The block subsidy is how new bitcoin enters into circulation, but it also incentivizes miners to remain honest and submit valid blocks. 

The block subsidy is paid out in the [coinbase transaction][CoinBase Transaction](../C/CoinBase-Transaction.md) of each block. This special transaction is the first transaction in every block, and it has no inputs. The output of a coinbase transaction cannot be spent for 100 blocks, so miners can only spend their block subsidy after a 100 block cooldown.

Each block contains many transactions, each with fees attached to incentivize their confirmation. The sum of the block subsidy and cumulative transaction fees in a block yield the block reward. Because the block subsidy falls by half every four years, transaction fees will slowly begin to make up most and then all of the block reward.


### Cooldown Phase
Der Output einer Coinbase Transaction, und damit der BlockReward inklusive Subsidy, sind für 100 Blocks, resp. maximal für 20 Stunden (durchschnittle 10 Minuten BlockTime X 100 Blocks) gesperrt, resp. müssen 100 neue Blocks erstellt worden sein, bis BlockRewards wieder ausgegeben werden dürfen.