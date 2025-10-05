# Baron Token Project Charter
---
locpath: C:\me\ACTIVE\VeriVotion\VeriVotion_Charter.md

author: rene.baron@baronsolutions.ch
created: 06.01.2025 17:57:48
version: draft v0.0.1
draft: true
private: false
disqid: DiscussID
tags: ["aktiv", "***", "bré"]
categories: ["BT", "Intern", "KEY"]
---

# Baron Token (BT): Project Charter
`rene.baron@govy.swiss | bré | Jan 06, 2025 | draft work in progress v0.0.1 | updated Jan 06, 2025`

---

> **"This document overlooks the principal goals, end-user purpose and functionality** of the herein to be engineered **Baron Token (BT)**"**

## Vision Statement
**The "BARON" (BAR) Token with its "Baronis" named Coins is a distributed open source [SocialFi platform](../GLOSSAR/S/SocialFi.md), that warrants participation for all human beings - poor or not - on the basis of ongoing cross-verified transactions among [KYC](../GLOSSAR/K/KYC.md) registered and therefore audited and well well trusted individuals**. 

---

<div style="background-color:#DFFF00; border-style:solid; border-color:#DFFF00; border-width:20px;">
<span style="font-weight:bold">Links</span>

* [Intro to **SocialFi**](../GLOSSAR/S/SocialFi.md)

* [Baroner](S01-Votioner/_S01-Votioner-CommandlineClient.md): Highly efficient end-user **CommandLine Interface for the BaronNetwork**. 

* [BaronCommand](): The command-line-interface for TestDriving the network

* [ClickUp Project Monitoring]()

* Project [Handbook](BT_PRJ_Handbook.md) For all **operational details**

* Project [Folder Index](01_KEY/_01_KEY.md): List of **Key Documents**

* Project [LOG](01_KEY/BT_LOG.md)

* [GitHub's README.md](README.md)

* [Solution Architecture (BluePrint)](04_MODEL/VV_SoftwareArchitecture.md)

**W=I=R=E Programme**

* The [W=I=R=E Programme Handbook](../../REPO/WIRE/01_KEY/WIRE_PRG-Handbook.md) -:|:- [LOG](../../REPO/WIRE/01_KEY/WIRE-LOG.md)  -:|:- [Key Docs](../../REPO/WIRE/01_KEY/KEY-Docs.md)

</div>

---

## Vision Statement
VeriVotion — Esperanto for “reasoning” — is a secure website **for civilised debates** — no shouting, rudeness or irrationality allowed! - that supports more relevant opinion-building as a foundation for smarter decisions and votings along social, political and organisatorial debates and large scale problem resolution activities. 

From a technical perspective,  the project's primary Phase I deliverable is a **generic Commenting- and Discussion-WebSite-Plugin** that supports smarter social debates on otherwise public accessible websites.

## Grundidee
1. Jedermann kann sich die frei im Web verfügbare **DAO-Blockchain-Management & Mining-App runterladen** in der die unten aufgeführten Regeln fix und unabänderbar eincodiert sind. 

2. Jedermann kann sich **mit 10$, seinem Ausweis und den UNIQUE (resp. nur einmal zu vergebenden, [What3Word](https://what3words.com/) encodierten Geodaten seines Briefkastens** (Rastergrösse gemäss [What3Word](https://what3words.com/) für das Mining **registrieren**.

3. Sobald 10, 100, 1000, ..., 10x Registrierte zusammenkommen, wird genau **ein Registrierter ausgelost**, der dann genau EINEN BARON minen darf. Technisch wird der Registrierte aus dem Auslosungspool genommen, so dass jeder Registrierte nur  einmal minen kann). 

4. Wer nicht selber minen kann oder will, kann das Minen, gegen eine von diesem frei wählbaren Gebühr, auch von einem professionellen Miner minen lassen. 

5. 1 Baron = 1 Million Barons. So wird jeder mindestes einmal im Leben zum Millionär :-)

6. Barons können nur an registrierte BaronUser überwiesen werden. 

7. Die Barons selber sind anonym und die Transaktion nur für die an der Transaktion Beteiligten sichtbar. 


## Welches Problem wird gelöst ? 
BAR wäre die erst Cryptowährung die garantiert dass wirklich JEDER Erdenbürger f¨r einen kleinen Unkostenbeitrag von 10$ partizipieren kann und sich so nicht diejenigen zuerst bedienen die über die entsprechenden Mittel und technisches Knowhow verfügen. 

## Nachteile
Keine Anonyme Registrierung und damit auch kein anonymes Mining. Hingegen ist und bleibt der damit generierte Token anonym, resp. ist bei Transaktionen mit diesem Token (oder Teilen davon (1 Baron = 1 Million Baronis) 



## Herefore derived Project Goals
The VeriVotion Software Project creates an advanced **discussion-plugin for smarter and more actionable discussions.

Check [the VeriVotion Log](01_KEY/VeriVotion_LOG.md) to see which goals have alreay been implemented and scheduled. The **most actual next steps** are listed blow or listed on [Clickup](https://app.clickup.com/2472934/v/dc/2bez6-647/2bez6-487).

## Next Steps
-> find most actual Next Steps on [Clickup](https://app.clickup.com/2472934/v/dc/2bez6-647/2bez6-487)

### Actual Steps End November 2022: 
1. setup a fully working, GCP-hosted Backend-Server that runs against my local frontend

2. setup a 3rd-party-hosted Frontend-server that provided the Commenting-Client-Plugin for Websites 

3. Setup a cloud hosted myrasis.com Web-Server from the MonsterGen-Demo-Page-Project that runs the hugo generated W=I=R=E pages with Remark42-Commenting Client-Plugins. 

4. Come to a final conclusion about the overall  W=I=R=E-architecture and  full CI/CD circle, and how this is going to be operated in the future. 

5. Finalize the W=I=R=E platform and start community-building.

6. Analyse the such created test-data in the Backend's Bolt-DB 

7. Specify our own Verivotion requirements

8. Decide how and where you want to extend the solution to cover our own specific VeriVotion requirements.

9. finally extend the current R42 source-code to comply with our own VeriVotion requirements.

### Challenges
I have started to run a project on "improving discussions and debates". 
Find Details here: https://www.polywork.com/invite/renandreas_baron-dewgong
One part is having better interfaces for discussion-forums that make discussions (which currently look all the same on all plattforms) more functional and more fun. Any ideas how the normal "thread of comments" could be improved?

## Primary Goals and Scope of the Comments-Plugin

* **Structured and more educated discussions** towards final conclusions that support better decisions that lead to more sustainable and commonly agreed solutions on personal, regional, national and even global scale. 

* Provide **intelligent weighting** of the comments for relevance, completeness and trust

* Add **bias-free weighting of domain-experts**, and make sure, that relevant people are discussing and voting primarely in the area of their expertise.   
  
* **Prevent echochambers** of like-minded people and/or field experts to keep discussions open to new insights and avoide communities that just defend their own.

* Support wellcoming, collaborative and open debates upon commenting best practice, dialogue examples and well moderated communication rules. 

* **Provide first class moderation tools** working in plain sight and full transparency.

## The W=I=R=E-Programme
The [WIRE Programme](../../REPO/WIRE/_WIRE.md) is the "ideological foundation" and wider organisational, financial and social context/framework the VeriVotion project is built upon. 

The W=I=R=E-Programme defines the high-level goals of the VeriVotion project in a wider context and relates the outcome of the VeriVotion project to other W=I=R=E-programme -orchestrated (sub-)projects.

## Key-Questions to be answered
Discussion-related items from the [W=I=R=E-Document](../../REPO/WIRE/_WIRE.md) are:

- What do we mean by "better"? better for whom? and why?

- What do we mean by "Discussions"? online forums? (social) media contributions? talking with friends, political debates? other?

- Finding the most efficient process to **check whether a statement is true** and how to follow it down to non-disputable facts. 

- How to **compose truth from previously approved facts**  
 
- How can we motivate people for more constructive, non-biased, less emotional and therefore **more relevant and actionalble solution oriented contributions**?

- Which are the **criteria upon with contributions should be weighted**?

- How can we **reduce doublications** and repetitions?

- How to keep spam and **spammers** away?

- How can we use **AI and swarm-intelligence** for more accurate and faster research and verification of truth?

- How can we **speed up the voting process** without losing completness nor quality of research and opinion building.

- How to make an expert-driven and less emotional approach still **attractive and accessible to the masses**

## Out of Scope
Obwohl wichtiger Bestandteil jeglicher konkreter Umsetzung, diskutieren wir aus Gründen der Komplexität und wenig konkreter Fassbarkeit die folgenden Themen (noch) nicht im Detail (wir sammeln zwar diesbezüglichen Input, aber entwicklen noch keine Lösungsvorschläge):

1. **Final clarification of legal stuff**: Topics like ownership, copyrights, data-protection compliance etc., are requirements and are built in from day one, but FINAL and international clarifications can only be done, when things are operational and can be demonstrated in a stable state and therefore can be discussed hands-on with what is, rather than discussing details on moving targets.


## Inspirations & Role Models

-> Discussion-related items from the [W=I=R=E-Document](../../REPO/WIRE/_WIRE.md):

### Kialo.com
![](xPIC/KialoOverview.png)[Kialo]() und Kialo-Edu)(https://www.kialo-edu.com/): Well maintained and still growing **reference model for structured discussion**.  

### Human-Connection
* [Human-Connection](https://human-connection.org/): Great initial design studies (slides only, whereas the project on-itself is a masterpiece on how a project should never be run with most foreseable and obvious consequences: total disaster!). Currently the project is continued on [Ocelot-Social)(https://github.com/Ocelot-Social-Community/Ocelot-Social) in a separate fork.


### Open Web
[OpneWeb.dom](https://www.openweb.com/) is tryping to create trusted spaces for quality conversations that move our society forward, improving how and where we talk to each other online. They claim to build an open, healthier web. Reality is they are selling exclusively to mass media corporations such as Washington Post etc. 

### Kleros.io
[Kleros Homepage](https://kleros.io/): Kleros is an open source online dispute resolution protocol which uses blockchain and crowdsourcing to fairly adjudicate disputes.

---

## Thinklets, Quotes & Insights
„In einer Welt, in der die Qualität öffentlicher Diskussionen, Diskurse und Debatten hinter den technologischen Möglichkeiten zur Verknüpfung von Menschen und dem Austausch von Ideen zurückbleibt sind wir davon überzeugt, dass Plattformen für strukturierte Diskussionen das Potenzial haben, neue Wege für Lösungsfindung und konkrete Umsetzugn zu finden. 

„Eine der wichtigsten Kompetenzen, über die ein Mensch verfügen kann, ist die Fähigkeit, Dinge kritisch zu begründen und zu bewerten. Was sind die Vor- und Nachteile von etwas? Können Sie sich mit jemandem einlassen, der eine andere Meinung vertritt?“
Errikos Pitsos, Gründer von Kialo

---

Right now, a lot of the collective intelligence that moderators gain from being on the front lines of the internet is lost. There’s no effective feedback loop for them to tell their employers what they’re seeing, such as trends and warning signs. I’ve talked to moderators who were probably some of the first people outside the U.S. State Department to know about certain conflict zones, with nowhere to go with that information.

Business ideas could also be gathered from these workers around how to improve online rules or better serve the public. But because moderators are at a remove organizationally, and often geographically, and because communication lines with leadership are nonexistent or broken, they’re seen as automatons who enforce extant rules — not as valued employees with knowledge to contribute to the larger ecosystem. That strikes me as a real missed opportunity.

Hi All, Thx for showing up interest in this topic.
"Discussions" is a huge topic. So the "problem" might be where to start:
Two suggestions:
1. Universal traits and habits to improve discussions regardless where and with whome they are held.
2. I am a big fan of the http://Kialo.com discussion platform and would like to get your feedback, and maybe you know some other great platforms as well.
What do you think?

---

When going for the BIG-picture, first talking about safe spaces and protecting contributors so that open discussions will primarely have a home first, some great inspirations might be taken from The World Economy Forum hosted "Global Coalition for Digital Safety" that aims to accelerate public-private cooperation to tackle harmful content online and will serve to exchange best practices for new online safety regulation, take coordinated action to reduce the risk of online harms, and drive forward collaboration on programs to enhance digital media literacy.

---

Take oil and vinegar for example. Famously, they don’t mix but with the right inputs and methods you’ll get yourself a delicious vinaigrette.
You and your team are no different. Especially as distributed and hybrid environments have become the norm, it’s critical to understand how to collaborate effectively.

## Streaming is key
Output-Streaming is paramount when output speed and granularity/dencity should be synced with what users can atually absorb. When users are getting structured information junks along a well designed ongoing streaming process along the natural limitations of natural human reading- and understanding capabilities motivation and learning experience can dramatically improved. 

Tactically we are using server-sent events (SSEs) that are relatively simple compared to websockets, while still providing a responsive and ways more absorbable and sticky experience.

## Chat is not enough
-> inspired by [this article](https://blendingbits.io/p/unlocking-superior-ux-with-llms?sd=pf)

Chat interfaces often present a "blank canvas" problem: while users recognize their potential, they struggle to initiate or refine their ideas, questions and prompts. In design terms, this is a discoverability issue. 

Providing some template questions and examples of associcated domain-specific output as well as other form of "context panels" can help. 

But as workflows become more complex and involve multiple stakeholders or integrations, this approach still proves inadequate, especially when the current knowledge at hand the specific issue to be discussed are not yet part of the underlaying machinery.

So providing interfaces to efficiently uploading newest and challenging knowledge where it is immediately run against the machine's knowledge for consistency and potential flaws, will become paramount for both sides: for humans to be able to innovate on new insights and for the machine to automatically learn the new stuff and to adjust "old" answers in the advent of new insights.

AI therefore will remain an auxiliary tool but never a ready made answer when addressing new challenges. 

Humans take seconds to process language, with a well-educated adult reading 200-300 words per minute; understanding adds further delay. In contrast, visual information processing occurs in milliseconds. Thus, visual interfaces are highly efficient, often resulting in more engaging user experiences.

For AIs, this suggests the importance of transforming their output into user-friendly interfaces. Instead of merely presenting raw data or textual summaries, we must consider more visual representations beyond simple graphs and associative pictures. 

As an immediate step we have to foster text-based delimiters like CSV or JSONL so that output can be chunked and therefore buffered and streamed to make intermediate processing easier and provoke immediate feedback that can steer the result on the fly and before all the bloated, already irrelevant-determined rest is clogging our networks.


## Links

### Better design
I would love to see more applications of changing behavior for the better. Set friendly defaults, show respect, empower kindness, encourage support and provide understanding — that’s the true power of good design with useful resources on how people think, decide, remember and focus attention:

Psychology Insights Cookbook, by Jerome Ribot
https://lnkd.in/epGNUd9j

Behavioral Science Design System in Figma, by Coglode
https://lnkd.in/gHEU4R9Y

Laws of UX, by Jon Yablonski
https://lawsofux.com/

Psychology UX Glossary, by Peter Ramsey
https://lnkd.in/ek9Pi-CG

Psychological Principles And How To Apply Them (Figjam), by Maryna Kucherova 🇺🇦, via Paweł Huryn 🇺🇦
https://lnkd.in/eGajTYEX

The Psychology of Design, by Dan Benoni and Louis-Xavier Lavallée
https://lnkd.in/d5Z6TpVt

Cognitive Biases Visually Explained, by Krisztina Szerovay
https://lnkd.in/eUaYkjnM

Cognitive Bias Cheat Sheet, by Buster Benson
https://lnkd.in/eBWwnwfv

Behavioral Science Insights (Miro board), by Elina Halonen
https://lnkd.in/eW5XgwDk

The Big Behavioral Bias Miro Board, by Robert Meza
https://lnkd.in/ei-Xs-tD

Behavior Design Framework, by Elina Halonen and Robert Meza
https://lnkd.in/eRZNZrBA

Behavioral Science Resources Hub
https://www.besci.org/

Behavioral Evidence Hub
https://www.bhub.org/