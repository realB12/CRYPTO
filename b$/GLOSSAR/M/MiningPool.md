# MiningPool

A mining pool is a group of miners who combine their computational resources to increase their chances of solving blocks and earning rewards. This collaborative effort makes mining more efficient and profitable, especially for home miners using models like BitAxes.

---

Die [Hashrate](../H/Hashrate.md) des gesamten Bitcoin-Netzwerks ist gigantisch. Deswegen minen die wenigsten für sich alleine. Stattdessen schließen sich Miner häufig zu sogenannten Mining Pools zusammen.

Der Vorteil des gemeinschaftlichen Minings besteht darin, dass man zusammen über eine höhere Hashrate verfügt als alleine. Die Wahrscheinlichkeit, den nächsten Block in Bitcoin zu finden, lässt sich mit der dieser Formel errechnen:

Eigene Hashrate / gesamte Hashrate des Netzwerks = Wahrscheinlichkeit den nächsten Block zu finden

Angenommen, wir besitzen einen ASIC mit einer Hashrate von 1 TH/s und die Hashrate des Netzwerks insgesamt beträgt 1 Exa-Hash pro Sekunde. Dann lautet die Rechnung: 1 TH/s / 1000000 TH/s = 0,0000001

Die Chance, auf eigene Faust einen Block zu finden ist also sehr gering.

Sie beträgt 0,00001 Prozent. Statistisch gesprochen bedeutet dies, dass bei einer Million Blöcken einer von mir gefunden wird. Nicht sehr gute Aussichten wenn man berücksichtigt dass nur alle 10 Minuten ein neuer Block erstellt wird und man alle 4 Jahre nur noch die Hälfte Bitcoin dafür bekommt.

Lässt man den eigenen ASIC für einen Miningpool laufen steigt die Wahrscheinlichkeit dass der Pool einen der nächsten 1000 Blöcken finden wird. 

Allerdings wird die Belohnung des Blocks unter allen Minern entsprechend ihrer beigesteuerten Hashrate aufgeteilt. 

**Damit ist das Pool-Mining nicht per se profitabler, sondern nur verlässlicher, da man öfters einen Block findet**. Die Auszahlungen finden regelmäßiger statt, fallen allerdings auch kleiner aus.

## Muss ich dem Pool vertrauen dass er mit auch wirklich die Belohnung sendet

Wenn ihr Solo-Mining auf dem dem Public-Pool Projekt betreibt, bekommt ihr vom Pool alle 60 Sekunden ein komplett individuelles Block Template, welches in der Coinbase-Transaktion eure BTC-Adresse als Output für den Block-Reward enthält.

Ihr seid daher nicht auf das Vertrauen angewiesen, dass ein möglicher Block-Reward euch weitergesendet wird, weil der Reward mit der Coinbase-Transaktion bereits auf eure BTC-Adresse generiert wird.

Auch kann eure BTC-Adresse nicht durch eine andere Adresse ersetzt werden, weil sich sonst der Hash vom Block komplett verändern würde, und bei der geringsten Veränderung sofort ungütlig wäre.

## Wieso werde ich von manchen Pools geblockt obwohl ich einen Asic Miner habe
Das hat eben nichts mit ASIC oder nicht ASIC zu tun, sondern mit der sehr sehr geringen Hashrate. Ein Miner mit 1 MH/s benötigt gleich viel Ressourcen von einem Stratum-Proxy-Server wie ein Miner mit 200 TH/s. Das ist der Grund wieso CPU-Miner bereits vor Jahren von den meisten Pools geblockt wurden … Und Nicehash sowie der KanoPool möchten offensichtlich auch keine Miner mit weniger als 1 (?) TH/s …

## Solo-Pools in der Übersicht
Momentan empfehle ich für die BitAxe wegen der verleichsweise kleinen Hashrate nur [CKpool](#ckpool) und [Public Pool](#public-pool). 

[KanoPool](#kanopool) und [NiceHash](#hashrate-marktplatz-nicehash)sperrt regelmässiger Miner die nicht mindestens 2TH liefern. 
### Schweizer Default Pool
Unser Ziel ist es, auch mal in der Schweiz einen Block zu finden. 

* **Stratum Host**: blitzpool.yourdevice.ch
* Port: 3333
* Alternativer Port: 4444

Wir betreiben einen stark modifizierten Public-Pool Fork, der sich auch fürs Mining mit Freunden eignet. Somit habt ihr, wenn ihr zusammen auf einer Adresse schürft, eure Worker komplett im Überblick.

**Pool UI**: https://blitzpool.yourdevice.ch

### CKpool

* **URL**: **https://solo.ckpool.org/**

CKpool ist ein **reiner Solo-Pool** (277 Blöcke), der Code von **ckpool** ist frei verfügbar. 

Con Kolivas selbst geniesst grosses Vertrauen. Er war massgeblich an der Entwicklung von **cgminer** beteiligt. 

Die Oberfläche ist rudimentär und ohne Schnick-Schnack, dafür performant, stabil und die Konfiguration sehr einfach. Der Pool hat eine extrem hohe Uptime, der Block-Reward bzw. die Coinbase-Transaktion geht direkt an die eigene BTC-Adresse, ohne Umweg.

#### Pool Fees
2% des Block-Rewards (exkl. Transaction Fees) gehen an ckpool an die BTC-Adresse bc1q28kkr5hk4gnqe3evma6runjrd2pvqyp8fpwfzu um den Pool zu betreiben und zur weiteren Pflege des ckpool-Codes beizutragen.

#### Settings

**Pool URLs:** 
* stratum+tcp://eusolo.ckpool.org:3333  (primary weil schneller Pool in der EU) 
* stratum+tcp://solo.ckpool.org:3333 (backup pool (langsamer)

**Username** 
The Username is THE public BTC-Reward-Adresse starting wioth bc1q... followed by a dot followed with our individual workername in the format:

> **bc1qDoNotShareYourBTCAdressWithAnyBodyElse.workername**

**Password**
x

#### High-Difficulty Pool 
(für stärkere Miner) ab Work-Diff < 1'000'000 = 1'000K = 1M

**High-Difficulty Pool  URLs**:
* stratum+tcp://eusolo.ckpool.org:4334 (primary)
* stratum+tcp://solo.ckpool.org:4334 (backup)

#### Pool Difficulty
CKpool ist so konfiguriert, dass bei der ersten Verbindung einem Worker standardmässig die Work Diff = 10'000 zugewiesen wird.

Die Work-Diff wird so angepasst, dass im Durchschnitt 20 Shares pro Minute – also alle 3 Sekunden 1 Share – überliefert wird.

Kommen mehr als 20 Shares pro Minute wird die Work Diff vom entsprechenden Worker erhöht, kommen weniger wird die Work Diff gesenkt. Dabei ist das untere Limit, also die Minimum Work-Diff = 1.

#### Generelles
Seit dem Update vom Juni 2023 verteilt ckpool **alle 30 Sekunden** (vorher alle 60 Sekunden) ein neues Block Template mit den aktuellsten Transaktion an die Miner.

Seit November 2024 betreibt Con Kolivas **eusolo.ckpool.org** auf einem eigenständigen Server in der EU. Der Pool hat eine deutlich geringere Latenz als **solo.ckpool.org** — die beiden Pools laufen unabhängig voneinander und können daher auch als Backup-Pools eingerichtet werden.

---

### Public Pool
Public Pool ist tolles Open-Source-Projekt mit attraktiven Statistiken.

Insbesondere für Miner mit Work-Diff < 1 bzw. Hashrate im Kilo- oder Megahash-Bereich geeignet, wie zB NerdMiner oder andere CPU-Miner.

Public Pool is relativ jung und es gibt immer wieder Downtimes wegen Updates/Wartungsarbeiten. Zudem wurde mit diesem Solo-Pool **noch nie ein Block gefunden**.

#### URLs
* https://web.public-pool.io/ --> offizieller Public-Pool
* https://blitzpool.yourdevice.ch/ --> Schweizer Public-Pool von yourdevice.ch betrieben.

#### Pool Fees
No Fees. 
100% des Block-Rewards gehen an den Miner – seit Ende November 2023 auch für Miner mit mehr als 50 TH/s.

#### Settings

**Pool URLs**: 
* stratum+tcp://public-pool.io:21496
* stratum+tcp://blitzpool.yourdevice.ch:3333

**Username**: 

bc1qDoNotShareYourBTCAdressWithAnyBodyElse.workername

**Password**:
x

#### Pool Difficulty
Public Pool ist so konfiguriert, dass bei der ersten Verbindung einem Worker standardmässig die Work Diff = 512 zugewiesen wird.
Die Work-Diff wird so angepasst, dass im Durchschnitt 6 Shares pro Minute – also alle 10 Sekunden 1 Share – überliefert wird.
Kommen mehr als 6 Shares pro Minute wird die Work Diff vom entsprechenden Worker erhöht, kommen weniger wird die Work Diff gesenkt. Dabei ist das untere Limit, also die Minimum Work-Diff = 0.00001

---
### KanoPool
https://kano.is/

KanoPool ist sowohl Solo-Pool (0 Blöcke) als auch PPLNS-Pool (2434 Blöcke). Kano war ebenfalls an der Entwicklung von cgminer beteiligt. Deshalb blockiert KanoPool offenbar Miner, welche gegen die GPL-Lizenzbedingungen von cgminer verstossen, zB VNISH und Awesome. Ausserdem blockiert KanoPool IP-Adressen welche Hashrate von CPU-Miner oder GPU-Miner an den Pool schicken.

**Die Konfiguration ist aufwendiger** und für High-Difficulty-Worker ist diese **teilweise echt mühsam** und erfolgt nicht wie bei ckpool einfach über einen separaten Port.

**Dafür bessere API-Schnittstelle, schönere Statistiken als ckpool**, eine **bessere Verteilung der Proxy-Server und geringere Gebühren (=Pool Fee) im Falle eines Block-Rewards (0.5%)**.

**Jedoch hat man mit gesperrten IP-Adresse und extrem vielen rejected Shares zu gekämpft**. **Ausserdem wird der Block-Reward nicht direkt auf die eigene BTC-Adresse generiert, die Coinbase-Transaktion geht zuerst an die BTC-Adresse von Kano – eine Frage des Vertrauens**.

#### Pool Fees
0.5% des Block-Rewards gehen an kano.

#### Settings

**Pool URL**:stratum+tcp://de.kano.is:3333

**Username**: bc1qDoNotShareYourBTCAdressWithAnyBodyElse.workername

**Password**: x

KanoPool ist nach der Registration standardmässig als PPLNS-Pool eingerichtet und muss aktiv auf Solo-Pool umgestellt werden. Dafür sind folgenden Voraussetzungen bzw. Schritte notwendig:

👉 The account must have been created in the last 2 hours
👉 You must not have pointed ANY miners at the account
👉 You must have verified the account email under Account >Verify
👉 You must have set a payout address under Account >Settings

☝️ You will not be able to change the account from Solo back to PPLNS

#### Pool Difficulty

KanoPool ist so konfiguriert, dass bei der ersten Verbindung einem Worker standardmässig die Work Diff = 8'190 zugewiesen wird.
Die Work-Diff wird so angepasst, dass im Durchschnitt 18 Shares pro Minute – also alle 3.3 Sekunden 1 Share – überliefert wird.
Kommen mehr als 18 Shares pro Minute wird die Work Diff vom entsprechenden Worker erhöht, kommen weniger wird die Work Diff gesenkt. Dabei ist das untere Limit, also die Minimum Work-Diff = 442.

#### High-Difficulty für stärkere Maschinen:

👉 Aktiviert in eurem Account unter Account > Solo die Option Allow high Difficulty.
👉 Erfasse auf Nicehash/MRR in eurer Pool-Konfiguration euren Worker mit entsprechenden Einstellungen, zB:
userXY.worker_highdiff
👉 Führt einen Test mit dem Poolverifikator durch, dadurch wird der Worker auf KanoPool im Account userXY unter Workers ersichtlich.
👉 Danach ändert ihr unter Workers > Mangagement beim gewünschten worker_highdiff, die Minimum Diff von 0 auf den erforderlichen Wert.
👉 Achtung: Der Poolverifikator wird zwar weiterhin einen Fehler melden: Poolschwierigkeitsgrad zu gering (vorausgesetzt=8190, minimum=500000), aber wenn die Minimum Diff entsprechend gesetzt wurde, wird der Auftrag trotzdem starten!

---
### OCEAN Pool
Luke Dashj (Bitcoin Core developer) reaktiviert den Pool Eligius (2011-2017) unter dem Namen OCEAN.
Das Ziel ist, einen dezentralisierten, transparenten, zensurfreien, non-custodial Mining-Pool zu etablieren.
Weiter soll die Nutzung und Weiterentwicklung vonPoolschwierigkeitsgrad zu gering Stratum V2 vorangetrieben werden, ebenso ist die Intergration von Lightning-Auszahlungen (2024) geplant.
Das Belohnungssystem von OCEAN namens TIDES (Transparent Index of Distinct Extended Shares) gibt den Minern die Möglichkeit, noch vor dem Finden eines Blocks den genauen Betrag ihrer Bezahlung zu verifizieren. Die Miner werden direkt vom Bitcoin-Netzwerk in der Coinbase-Transaktion bezahlt.

https://ocean.xyz

## Hashrate-Marktplatz (NiceHash)
Nicehash ist kein Mining-Pool, sondern ein Hashpower-Marktplatz, ihr bietest also eure Hashrate auf dem Marktplatz an und werdet von Nicehash nach überlieferten Shares bezahlt (PPS = Pay per Share).
Mit und ohne KYC möglich.

Homepage: **https://www.nicehash.com/**

### Auszahlungen

PPS (Pay Per Share)
Nicehash-Wallet: 0.00001 BTC (alle 4 Stunden), Payout fee 2%
BTC-Adresse: 0.001 BTC (wöchentlich), Payout fee 2% + 0.00001 BTC
BTC-Adresse: 0.100 BTC (täglich), Payout fee 2% + 0.00001 BTC
🔗 https://www.nicehash.com/support/mining-help/earnings-and-payments/can-i-get-paid-to-an-external-wallet-address

### Settings (ohne KYC)

Pool URL
stratum+tcp://sha256asicboost.auto.nicehash.com:9200

Pool URL Alternative
stratum+ssl://sha256asicboost.auto.nicehash.com:443

Username
bc1qDoNotShareYourBTCAdressWithAnyBodyElse.workername

Password
x

<span style="color:red; font-weight:bold">ACHTUNG</span>: Wenn ihr zB. bei Nicehash kein KYC macht und somit auf eure eigene BTC-Adresse ausbezahlen wollt, müsst ihr mit einer Bitaxe mind. 44 Monate schürfen (ohne Berücksichtigung der steigenden Difficulty) bis ihr die Schwelle von 0.001 BTC erreicht🥸

---
## Infos
* **Tips aus Bülach**: https://yourdevice.ch/bitcoin/

## List of pools
* [BlitzPool](https://blitzpool.yourdevice.ch/#/)

* eusolo.ckpool.org

* stratum.kano.is