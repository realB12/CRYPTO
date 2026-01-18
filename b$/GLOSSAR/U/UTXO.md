# Unspent Transaction Output (UTXO)

Ein UTXO ist wie ein Geldbeutel, der bei einer Geld-Ueberweisung durch drei neue Beutel, resp. UTXOs, ersetzt wird: Jeweils einen neuen Beutel für

1. den **Geldempfänger** mit dem an ihn überwiesenen **Zahl-Betrag**
2. den **Owner/Absender** mit dem **Restbetrag** 
3. den **Miner** mit der **Transactionfee** für den Minen dieser Transaktion. 

Dabei ist lediglich die SUMME, resp. der WERT (in [Satoschis](../S/sat.md)) des Beutels relevant (Das Bild der darin enthaltenen "Münzen" dient nur der Veranschaulichung, wie der Input-Wert der Transaktion auf die verschiedenen Output-Beutel verteilt werden kann). 

> Der Name "Unspent Transaction Output" kommt daher, weil jeder UTXO als Output einer normalen [Geldüberweisungs Transaktion](../T/Transaction.md) oder einer [CoinBase Transaction](../C/CoinBase-Transaction.md) erstellt, aber noch nicht als Input einer FolgeTransaktion verwendet wurde. 

**Jeder UTXO kann nur genau einmal (als Transaktionsinput) verwendet werden,** resp. sobald ein UTXO auf der Blockchain als Input einer Transaktion vermerkt wird, gilt er als "ausgegeben" (bleibt aber "as is" in der Blockchain auf immer und ewig erhalten um so jeden neu auf dieser Basis erstellten Folge-Output zu seiner Quelle zurückverfolgen zu können). 

### Beispiel
If Alice owns a UTXO worth 1 BTC and wishes to pay Bob 0.4 BTC, she must spend her entire 1 BTC for this transaction's input. 

In order to send Bob exactly 0.4 BTC, Alice creates two outputs: the first to Bob, in the amount of 0.4 BTC, and the second back to herself, in the amount 0.59 BTC, assuming that she paid a 0.01 BTC transaction fee. This transaction will consume one UTXO (input) and create 2 new ones (output). 

Note that the fee paid is not itself an output. It is implied by the sum of the inputs (1 BTC) minus the sum of the outputs (0.4 + 0.59 = 0.99 BTC). The miner of this transaction would calculate this fee and claim it for themself in the coinbase transaction.

## UTXOs in Bitcoin Wallets
Eine Wallet speichert keine Bitcons, sondern managed die mit einer bestimmten [Addresse/PublicKey](../A/Address.md) assozierten UTXOs: 

1. **Konto**: Der in einer Wallet gespeicherte Wert (resp. der für eine Transaktion zur Verfügung stehende Betrag) ist die Summe aller darin enthaltenen UTXOs (resp. die Summe aller mit der Wallet-Addresse assoziierten UTXOs). 

2. **Transaction**: When you initiate a transaction, your wallet software selects appropriate UTXOs to use as inputs where their sum is equal or higher the amount of the "money" sent + transaction-fees.

3. **Retourgeld**: If the selected UTXOs exceed the amount you want to send, your wallet creates a change output back to one of your addresses.

4. **Konsolidierung**: Ab und zu werden die UTXOs mit kleinen Beträgen zu einem grösseren UTXO zusammengefasst um so Transaktionsgebühren zu sparen. 

5. **Privacy**: Fortgeschrittene wallets wit z.B. "CoinJoin" können UTXOs von mehreren Usern zusammenlegen, um so die Anonymität zu wahren, resp. Absender und Empfänger von Transaktionen zu verschleiern. 

### UTXO SET
Der **UTXO set** ist die zum aktuellen Zeitpunkt existierende Menge aller (aktiven = unspent) UTXOs. Die Summe der Werte (in [Saktoshis](../S/sat.md) nicht Dollars!) aller UTXOs entspricht damit der Anzahl der zu diesem Zeitpunkt existierenden (minted) Bitcoins. 

Jeder Bitcoin-Node enthält und kennt damit immer den ganzen UTXO set. Diese Sets werden laufend upgedatet sobald der Blockchain ein neuer Block mit Transaktionen hinzugefügt wird. 

## Wie wird ein UTXO erstellt?
New UTXOs are created when existing ones are consumed by transactions. Each bitcoin transaction consists of inputs and outputs. Inputs in a transaction use up old UTXOs, while outputs generate new ones. So, if old UTXOs are destroyed to create new UTXOs, how are UTXOs created in the first place? Answer: coinbase transactions. This cycle starts with a coinbase transaction, which miners use to introduce new Bitcoin into the system, creating initial UTXOs without prior inputs.

A coinbase transaction is a special type of transaction that creates new bitcoin as a reward for the miner of a block. Since this transaction is creating new bitcoin, the coinbase transaction has no inputs and one or more outputs. Like all normal outputs, the output of a coinbase transaction is a new UTXO.

Each UTXO has the following characteristics:

A fixed value
Tied to a bitcoin address
A transaction ID that created the UTXO
