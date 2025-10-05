# SelfCustody: Bitcoins in Selbstverwahrung

> **Not your keys, not your coins!**

---

* [Risiken von Cryptobörsen](../TRAIN/1_INTRO/Risiken%20von%20Cryptobörsen.md)  

* Im [Crypto Plan Dokument](../../../_KEY/CryptoPlan.md) zeige ich exemplarisch den typischen "Werdegang eines Neueinsteigers" der selten direkt mit Self-Custody einsteigt. 

* [BTC Setup](../BTC_Setup.md) das generische Einstiegsdokument zum Setup eines CryptoFrameworks.  

* [Credentials Teilen](../../../../PRIV/_KEY/Admin/PW/CredentialsTeilen.md)

---

> **SelfCustody heisst, die Schlüssel zu den Bitcoins selbst- und alleinverantwortlich sicher aufzubewahren, um so Risiken durch Dritte zu minimieren, und sich und seine Assets durch Wahrung der Privatspähre auch zukünftig vor Zensur und Bevormondung zu schützen. Dies setzt aber den absolut sicheren und routinierten Umgang mit Passwörtern, eMail-Konten, Passphrasen und Wallets voraus (BRVOR man seine Coins dorthin transferiert!)**

## Zusammenfassung

### 1. Stufe: Vokabular, Zeit, Plan und Logindatenverwaltung
1. Sich einen Ueberblick zu Bitcoin verschaffen und die wichtigsten Fachbegriffe kennen 

2. Die eigenen Zeitverhältnisse klären und einen **[Crypto Plan](../../../_KEY/CryptoPlan.md) erstellen**: Was will ich bis wann, wo, und weshalb: Zuerst mit [Cryptobörsen spielen][Risiken von Cryptobörsen](../TRAIN/1_INTRO/Risiken%20von%20Cryptobörsen.md) oder direkt mit [_BTC SelfCustody](_BTC%20SelfCustody.md) einsteigen? Beides Parallel. Nur BTC oder auch Altcoins? 

3. Einen erprobten **[Prozess für den sicheren Umgang mit Logindaten](../../../../PRIV/_KEY/Admin/PW/_PasswortManagement.md)** (jeweils unterschiedliche Passphrasen & ANONYMEN eMailAdressen für unterschiedliche Börsen, Banken, Hoster, etc.!) implementieren, und mit einer **Vertrauensperson** teilen [Credentials Teilen](../../../../PRIV/_KEY/Admin/PW/CredentialsTeilen.md). 

### 2. Stufe: Custodial Crypto
1. Ev. zuerst mal **(safe! und überlegt) an einer [Cryptobörse](../TRAIN/1_INTRO/Risiken%20von%20Cryptobörsen.md) ein Gefühl fürs Ganze kriegen**: will ich **zocken oder nur sparen**? Und will das mein **soziales Umfeld** auch? Dabei die eigene **CredentialVerwaltung** (Passwörter & eMailKonten) testen, mit der Hausbank das **ON- und OffRamping üben**, sich um die **Steuern** kümmern und sich ganz generell mit **Zugangs-Infrastruktur** (Internet, PC, Handy, iPhone, Drucker, Backupmedien für a) zu Hause, b) Arbeitsplatz c) Unterwegs im In und Ausland), Datenschutz und Datensicherung auseinandersetzen.   

2. Bei **[Relai](../../SERVICEs/MIX/R/Relai/_Relai.md)** mit einem BTC-Sparplan mit SelfCustody einsteigen. Im Erstellen diverser Wallets und der Verwaltung der dazu gehörigen [Seedphrasen](../../GLOSSAR/S/Seed.md) auf Hot- und Cold-Wallets Profi werden.

### 3. Stufe: 100% SelfCustody
3. 100 SelfCustody: Auf einer sicheren Linux-Maschine einen eigenen Knoten betreiben mit Tools und Prozessen für eine 100% anonyme, unabhängige Selbstverwaltung der eigenen Cryptos 

### 4. Expertenstufe
Sich als Experte zertifizieren lassen und andere beraten und helfen. 


---

## Intro
Für den Anfang und für kleine Beträge, um sich einfach mal mit dem Thema Bitcoin vertraut zu machen, braucht es kaum Cryptokenntnisse und keine spezielle Infrastruktur und Prozesse um sind an Crypto-Börsen, wie z.B. der bekannten `Binance` oder bei meinem Favoriten `SwissBorg` die ersten "Bitcoins" zu kaufen (eigentlich erhälte man nur Zertifikate im Gegenwert des aktuellen BitcoinKurses). Diese bergen aber erhebliche Risiken die ich im separaten Dokument  [Risiken von Cryptobörsen](../TRAIN/1_INTRO/Risiken%20von%20Cryptobörsen.md) zusammengefasst habe. 

Langfristig und ab grösseren Beträgen sollte aber immer eine Selbstverwahrung angestrebt werden (die man natürlich auch wieder an Dritte delegieren kann, ohne dabei die eigenen Schlüssel wieder ganz aus der Hand zu geben).

Anderst als Cryptobörsen benötigt Self-Custody, also die Offline-Aufbewahrung der eigenen Coins (resp. der Schlüssel für deren Zugriff) fundiertes und praxiserproptes **Fachwissen, welches in regelmässigen Trainings, genauso wie die Infrastruktur durch permanentes Updaten, laufend wieder bestätigt werden will. 

Dafür muss man, je nach Vorwissen, Quellen, Coaches und Talent schon regelmässig eine gewisse Zeit investieren können. Hat man die nicht, sollte man den Alleingang gleich ganz lassen und die diesbezügliche Arbeit von Anfang an in die qualifizierte einer Vertrauensperson oder eine Dienstleisters geben. 

### Vorteile von Self Custody

> <span style="color:red; font-weight:bold">No keys; no coins!</span>
 
Most wallets will **automatically create new public keys each time you want to receive bitcoin**. This alleviates the problem of public key or address reuse. If you use the same public key every time you receive bitcoin, it would become trivial for anyone to track your entire payment history. Treating keys as single use tokens greatly improves a user’s privacy.

1. Man hält im Gegensatz zu Exchanges die dazu nicht verpflichtet sind, tatsächlich auf der Blockain global und auf ewig einsehbare Bitcoins. 

2. Nur eigene Bitcoins sind sowohl für die Oeffentlichkeit als auch den Staat einigermassen anonym (solange sie auf der Blockchain bleiben und nicht ausgezahlt werden (müssen) mit Auswirkunge auf die Besteuerung von Einkommen und Vermögen. 

3. Einfach ein besseres Gefühl wirklich zu besitzen und zu kontrollieren was man (in echt) selber hat und nicht irgendwo bei einer Börse liegt. 

4. Ich persönlich gelange zur Ueberzeugung, dass der Nachweis real-existierender Bitcoins als Primium zum Bitcoin-Kurs hinzugeschlagen werden kann, resp. z.B. bei der Belehung der eigenen Bitcoins relevant sein wird und gewisse "Geschäfte" überhautp erst ermöglichen werden. 

Mehr zum Theme SelfCustody versus Cryptobörsen findet sich in den folgenden Dokumenten: 

* [Risiken von Cryptobörsen](../TRAIN/1_INTRO/Risiken%20von%20Cryptobörsen.md)  

* Im [Crypto Plan Dokument](../../../_KEY/CryptoPlan.md) zeige ich exemplarisch den typischen "Werdegang eines Neueinsteigers" der selten direkt mit Self-Custody einsteigt. 

* [BTC Setup](../BTC_Setup.md) das generische Einstiegsdokument zum Setup eines CryptoFrameworks. 

### Zwischenschritt Custodial Banks
Immer mehr Banken und CryptoBörsen verwahren die von dir über sie gekauften Bitcoins in einer eigenen Wallet, für die aber nur die Bank die Schlüssel besitzt (was in regelmässigen Audits auch überprüft wird). 

Das ist natürlich nicht gratis und im Endeffekt ist es auch hier wieder Vertrauenssache, ob die Bank das tun was sie soll und ob überhaupt oder Du dann doch wieder nur eine IOY (I Owe You) Quittung in der Hand hältst.  

In diesem Paper werde ich aber nicht näher auf diese Custodials eingehen. 

### Anlehnen
Als Newbie SelfCustoy gleich im Solo-Alleingang zu wagen, um nur mal schnell mit Freunden ein paar Satoschis zu tauschen, verbraucht nicht unangemessen viel Zeit und Nerven, sondern ist auch wegen der viele möglichen Anfängerfehler mangels besserem Wissen - bis hin zum Totalverlust - so ziemlich risikobehaftet, u.U. wegen der (Layer 1 Transaktionskosten) unnötig teuer und deshalb davon abzuraten. 

Mittlerweile (Stand 2025) gibt es einige Anbieter über die Du BitCoins beziehen und in einer eigenen, aber vom Anbieter-kontrollierten WalletApp verwalten kannst. Alles aus einer Hand sozusagen, wo Du auch entsprechende Schulung, Training, Communit und Supporst erhältst und damit beim Mitfliegen den Piloten über die Schultern schauen kannst um alles zu lernen was Du für den Soloflug brauchst 

Einer aavon ist [Relai](#relai): 

### Relai
Anbieter wie die im folgenden beschriebene [Relai](../../../../PRIV/_KEY/Assets/Services/R/Relai/_Relai.md) sind explizit keine klassische Online-Börse wie z.B. Binance und machen nichts anderes, als dass sie dir gegen Fiat-Geld Bitcoins auf deine von Relai in Form einer RelaiApp autokonfigurierte Wallet senden. 

Dabei handelt es sich um eine gewöhnliche Wallet wie Metamask etc. - mit dem Unterschied, dass sie von einer (Schweizer) Firma kommt, die man kennt und die regelmässig (nach Schweizer Recht) staatlich überprüft wird. Und weil die Firma die Wallet kennt mit der Du arbeitest, kennt und kontrolliert sie auch die diesbezüglichen Prozesse und kann dir somit auch schnell und präzise helfen, falls dann doch etwas "klemmt". 

Ich persönlich halte diesen Full-Service-Einstieg für Neueinsteiger als "the way to go" um so mit einem schnellen, aber trotzdem sicheren Einstieg in die Materie ein erstes Gefühl für die Abläufe zu bekommen und Vertrauen zu gewinnen (welches man sich beim wilden Experimentieren im "Do-it-yourself-Modus" dann doch oft selbst vergeigt). 

Der nachfolgende Umstieg auf die Anbieter und (OpenSource-) Tools Deiner Wahl für die Implementierung einer 100% unabhängige CryptoInfrastruktur auf anonymer OpenSource-Basis wird, sobald man die grundsätzlichen Abläufe und Terminologie einmal mit Mitfliegen kennengelernt hat, dann bedeutend einfacher und auch weniger risikoreich. 


---

## 1. Grundsätzliches
Grundsätzlich gilt beim Neustart mit SelfCustody: **Take it slow!**

Investiere höchstens so viel Prozent Deines Vermögens in Crypto wie Du vom Ganzen verstehst: Also, wenn du nur 5% vom GANZEN überblickst, dann auch nur 5% Deines Geldes! Alles andere ist blöd, wird dich enttäuschen und last-but-not-least dem Ruf von Crypto schaden!

Und weil du am Anfang keine Ahnung hast, welchen Prozentsatz vom Ganzen Du verstehst, kann es da nur um Spielgeld in der Höhe von 100$ gehen, die du bei einem Anfängerfehler auch mal locker und ohne Nervenzusammenbruch oder Burnout zu 100% abschreiben kannst.

Mit diesem Spielgeld durchläuft man den im Folgenden beschriebenen Prozess ein paar mal, bis alles sitzt und auch soweit verstanden ist, dass man genau weiss, wie zu reagieren wäre, wenn auch mal was schief läuft oder ein daran beteiligter Dritter (Walletanbieter, FIAT-Bank, etc. ) nicht mehr oder falsch mitspielt. 

Auch wenn die Themen Steuern, FIAT-Bank, Todesfall, etc. am Anfang (Spielgeld) weder wichtig noch notwendig sind, sollte man sie von Anfang an im Hinterkopf behalten:  

### Steuern
Last but not least sollte man sich von Anfang an auch Gedanken zum Thema Steuern machen, da man CryptoVermögen und -Gewinne je nach Land von Anfang an versteuern muss. Da ich diesbezüglich kein Fachmann bin (resp. ich das meinem Steuerberater überlasse) werde ich auch nicht weiter auf dieses Thema eingehen.  

### Fiat Bank
Die Praxis zeigt, dass sich Standardbanek wegen Geldwäschereigesetzen, KYC, und anderen Gründen oft sperren Geld an Crypto-börsen zu überweisen und noch mehr, wenn sie von diesen Gelder erhalten. 

Es macht deshalb Sinn, sich von anfang an über die Usanzen der eigenen Bank zu informieren, dort nachzufragen und/oder die AGBs vollständig durchzulesen und gegebenenfalls ein Konto bei einer cryptofreundlicheren Bank- wie z.B. Revolut - zu eröffnen. 

### Zeit
SelfCustody ist ein Committment und eine Verpflichtung die relgemässig - auch wenn du deine Sats nur ruhen lässt - deine Aufmerksamkeit erfordert, und Du mindestens eine Woche für den Einstieg und danach jede Woche mindestens eine Stunde bewust in den Prozess investieren solltest. 

Und DAS sollte dir auch etwas Spass machen. Falls Du weder Zeit noch Spass hast ist SelfCustody ev. auch ganz grundsätzlich nichts für dich.

### Familie
Ueberlege dir, wen du für den Fall, dass Dir was passier mit einbeziehst: Wer erhält Zugriff auf deine Konten und wie? Testament? Was steht drin?
Dazu gehört auch, dass Deine Familie über dein Tun informiert ist und sowohl deinen Aufwand an Zeit wie auch das zu investierende Kapital gut heisst. 

### Politisches Statment
BitCoiner zu sein wird in den Augen Vieler je länger je mehr auch zu einem politisches Statement für staatliche und institutionelle Unabhängigkeit. Auch wenn man hier nur die Geldanlage und Wertsteigerung im Fokus hat, sollte man sich schon auch bewusst sein, dass man damit auch Teil einer grunsätzlichen Bewegung, wenn nicht sogar eine Revolution ist welche ev. noch grosse Wellen schlagen wird welche die Gesellschaft spalten und auf beiden Seiten Fanatikern eine Bühne bereiten wird. Damit muss man leben und schlafen können. 

### Finanzielle Zielsetzung
Gerade am Anfang sollte man keine finanziellen Ziele erreichen wollen. Das verleitet lediglich zu höheren Einsätzen ohne die entsprechende Routine diese auch sicher und nachhaltig verwalten zu können. 

---

## 2. Passwortmanagement
Im Endeffekt läuft alles darauf hinaus, die beim Erstellen von Wallets erzeugten Passphrasen zu verwalten. 

Auf der esten Stufe werden Crypto-Passphrasen idealerweise wie alle anderen Passwörter für Wichtiges verwaltet, resp. macht es wenig Sinn für CryptoPasswörter einen andere, neuen Prozess zu fahren, als den, an den man sich seit Jahren gewöhnt hat (Es sei denn, man traue der bisherigen Passwort-Verwaltung (so man denn eine hat) nicht mehr, und nutze jetzt die Gelegenheit, das eigene Passwortmanagment grundlegend - auch unabhängig von Crypto - zu überdenken und neu aufzusetzen). 

Wichtig ist eifach, dass man sich bezüglich der bei jeglicher Registrierung benötigten Passwörter und e-Mail Adressen Gedanken gemacht hat und man sein grundsätzliches Passwortmanagement up-to-date hat, **BEVOR man sich bei der ersten Börse registriert, die erste Wallet einrichtet** (weil diese Registrierungs-Passwörter vor lauter Begeisterung und oft auch Ueberforderung mit der Crypto-Technik sonst so ziemlich sicher schnelle wieder vergessen gehen). 

Selbst wer dirket mit MultiSig-Harwarewallets einsteigen möchte, sei daran erinnert, dass auch diese Hardware zunehmend und zusätzlich mit ganz normalen Passwörtern geschützt werden, die man entsprechend verwalten muss - und zwar so, dass man das auch noch nach Jahren völliger Inaktivität noch weiss! 

Deshalb: **Passwort- und eMail-management muss man können.**

Fühlt man sich damit nicht sicher, wird das Aufsetzen von SelfCustody unnötig stressig und auch die Nutzung neuster Cold-Wallet-Technologie ist dann sinnlos.   

### Passwort- und eMail-Management
Ich persönlich habe meinen PasswortGenerierungs- und Verwaltungs-Prozess in einem separaten [PasswortManagement-Dokument](../../../../PRIV/_KEY/Admin/PW/_PasswortManagement.md) festgehalten und dazu passen ein [eMail Gesamt-Konzept](../../../../PRIV/08_COLAB/eMail/_eMail-Konzept.md) verfasst.

Dabei geht es nicht nur um die Geheimaltung der dienstleisterspezifischen anonymen Passwörter und e-MailAdressen per se, sondern auch um den Ueberblick über alle mit Passwort- und eMail assozierten   

* **Tools** (eMail-Clients, Passwort- und Zufallsgeneratoren, Verschlüsselungsdienste, manuelle Verfahren)
* **Dienstleister** (Internetprovider, eMail-Hoster, Softwareanbieter, Backupservices, Git-Repos, Websitehoster)
* **Abos** (Internet, Domainnamen, Mail, SpamfilterDienste, Antivirus,...) 
* **Zugangsgeräten** (PC, Web, iPad, Mobile) und 
* **Infrastruktur** (z.B. Router, Safe, Printer, Netzwerk). 

### Logindaten mit Vertrauenspersonen teilen. 
Es empfielt sich, eine Zusammenfassung aller Login-Daten für alle relevanten Dienstleister von Anfang an mit einer VertrauensPerson zu teilen (just in case) oder mindestens so (auf Papier ausgedruckt) aufzubewahren und zu kommunizieren, dass mindestens eine Vertrauensperson weiss, wo sie danach suchen muss. Das permanente Einbinden dieser Vertrauensperson muss integraler Bestandteil des Gesamtprozess bleiben. 

-> Details zum [Teilen von Credentials](../../../../PRIV/_KEY/Admin/PW/CredentialsTeilen.md)  

---



## Relai
Im folgenden beschreibe ich wie man mit der Schweizer Firma Relai pragmatisch, sicher und einfach zu den ersten selbst verwalteten Bitcoins kommt. 




, sondern man der Routine und Tools von Experten vertraut, um den ganzen Prozess pfannenfertig vorgegeben mal End2End zu durchlaufen, um auf dieser Basis im Sinne eines mittelfristigen Ziels mit der nötigen Routine sich für die eigenen Tools und Prozesse zu entscheiden. 









## Bitcoin-Wissen für die Selbstverwaltung
Die Verwahrung von Bitcoin und Co. setzt ein Grundverständnis der folgenden vier Begriffe voraus: Public Key, Private Key, Backup- oder Wiederherstellungsphrase und Blockchain-Adresse.
