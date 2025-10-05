# Private Key: der geheime Zugangsschlüssel

Der Private Key ist das Gegenstück zum [Public Key](PublicKey.md). Zusammen bilden beide jeweils ein einzigartiges Schlüsselpaar. Der Private Key ermöglicht die Entschlüsselung von mit dem zugehörigen Public Key verschlüsselten Daten. Im Bereich der Kryptos ist der Private Key eine geheim zuhaltende, kryptografische Zeichenfolge, die zur Signierung und Autorisierung eigener Blockchain-Transaktionen verwendet wird. Der private Schlüssel ist wie ein geheimer Zugangscode – vergleichbar mit einem E-Banking Passwort. Er verschafft Nutzern direkte Kontrolle über ihre Kryptos auf der Blockchain. Im Gegensatz zum Public Key ist es äusserst wichtig, dass der Private Key geheim gehalten wird, um die eigenen kryptobasierten Vermögenswerte vor unbefugtem Zugriff zu schützen. Auch sollte ein Private Key stets sicher aufbewahrt werden, da ein Verlust desselben dem Verlust der kryptobasierten Vermögenswerte gleichkommt.

## Alternative MPC
Das Verwalten des PrivateKeys birgt natürlich das Risiko des Single Points of Failure. Geht er verloren, vergessen oder wird er gestohlen, gibt es keinen Weg mehr zum Konto. 

Eine Alternative bietet die sogenannte ["MultiParty Computation Technologie" MPC](../M/MPC.md), wie sie z.B. von [Swissborg](../../SERVICES/S/Swissborg/Swissborg.md) verwendet wird. Sie schützt Konten und Transaktionen in dem ihr Zugang durch das Zusammenspiel verschiedener Transaktionspartner, bei denen keiner den GANZEN Privaten Schlüssel hat, resp. wird erst gar kein [Private Key](../P/PrivateKey.md) verwendet der damit auch nicht gestolen oder erraten werden kann. 

[Swissborg](../../SERVICES/S/Swissborg/Swissborg.md) verwendet z.B. Fireblocks: die gemäss eigenen Angaben sicherst Platform um digitale Assets mittels "multiparty computation technology" zu schützen. 


