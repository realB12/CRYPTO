---
locpath: C:\me\ACTIVE\VeriVotion\VeriVotion_PRJ_Handbook.md

author: rene.baron@baronsolutions.ch
created: 27.04.2022 18:51:44
version: draft v0.0.1
draft: true
private: false
disqid: DiscussID
tags: ["aktiv", "***", "bré"]
categories: ["Hugo", "Intern"]
---

# VeriVotion (VV) Project-Handbook 
`rene.baron@govy.swiss | bré | Apr 27, 2022 | draft work in progress v0.0.1 | updated Apr 27, 2022`

---

The **VeriVotion Project Handbook** contains links towards all  

> **"Key Artefacts** that are normally used on a daily base for lookup and reference"**

by project-stakeholders and workers - especially when they are new to the project or when in need of a referesh of project related process documentation and/or key artefacts. 

---

<div style="background-color:#DFFF00; border-style:solid; border-color:#DFFF00; border-width:20px;">
<span style="font-weight:bold">Links</span>


* Project **Logs**: [Overal](01_KEY/VeriVotion_LOG.md) // [Frontend](40_DEV/2_FRONT/votionApp_LOG.md) // [Backend](40_DEV/1_BACK/votionSrv_DEV_LOG.md)

* [Overall Project Charter](VeriVotion_Charter.md)

* [User Manual](01_KEY/VV_UserManual.md)

* [externalLink]() -> 

* [Key-Docs](01_KEY/_01_KEY.md): Index

* [VV Architecture Doc](01_KEY/VV_Architecture.md)

* [GitHub](https://github.com/realB12/VeriVotion): Where this project (docs & code) is versioned

* [Registered Domain](../../REPO/work/ENTITY/SE/HOST/PROVIDER/Domain.com/_Domain.com.md) = `blah-blah.space`

* [W=I=R=E Programm](../../REPO/WIRE/01_KEY/WIRE_PRG-Handbook.md)  

</div>

---

## WHY?
When joining a development team, it takes some time to become productive. This is usually a combination of learning the code base and getting your environment setup. 

This is why we provide an onboarding document for setting up your environment and we are trying hard to keep it up to date. If in doubt, don't be shy and ask the people you think, they might now: they are awared to help people to get on speed as fast as possible!

## All around Git & Docker
To overcome the “works on my machine” problem and to ensure that everybody is working on the same, most up to date piece of code all our workflows are based on Git (Versions, Issues, Docs) and [Docker](../../REPO/work/ENTITY/SE/DEVOPS/06_TOOLS/Docker/_Docker.md) (Containerization). 

As Git and Docker are essential for us, we expect every contributor to have some hands-on routine with this and we discourage plumbing with our code and absorb our resources by doing stuff outside of our virtualisation principles.

## Project Key-Data

* **ProjectName** = **VeriVotion** 

* **Project Aconyme** = **VV**

* **Project Owner**: René Baron (bré), Zurich - rene.baron@baronsolutions.ch

* List of [Key-Docs](01_KEY/_01_KEY.md)

* [GitHub Repository](https://github.com/realB12/VeriVotion): Where this project (docs & code) is versioned

* [Registered Domain](../../REPO/work/ENTITY/SE/HOST/PROVIDER/Domain.com/_Domain.com.md) = `blah-blah.space`

* [Budget]() = **CHF 250'000** for first scalable, function complete prototype till November 2023. 

* **Project Start**: November, 2022

* Milestones
    a) February 2023: Requirements complete
    b) Sept 2023: OpenSource Project launched for the public

## Core Components
From a technical perspective the key components are 
a) the **Commenting Plugin** (that can be mounted in customer's website) and that is provided by 
b) the **FrontEnd-Server** which again 
c) interacts with the **BackendServer** that holds the database and does all the security stuff. 

![](xPIC/VV-Architecture.png)

-> check our [VV Architecture Doc](01_KEY/VV_Architecture.md) for more details. 

## Project Dependencies

### Remark42 docker-composed local Demo Server
The `C:\me\ACTIVE\Remark42`-folder contains a `docker-compose.yml` generated set of an out-of-the-box, unmodified and ready-made [Remark42 Commenting Front- and BackendServers](../VeriVotion/89_TOOLS/Remark42/_Remark42-for-VV.md) which were installed by running the `docker-compose.yml`-file according to the  [Remark42 Setup Guide](../VeriVotion/89_TOOLS/Remark42/Setup/R42-DevSetupGuide.md). 

Further this setup provides a draft "client"-webpage (`index.html`) that demonstrates how this backend-server is accessed from a local Windows client and verifies that local connections from client to server works. 

The purpose of this setup is to have a **ready-made, non-modifiable out-of-the-(docker-)box running local Remark42 setup environment** that proofs the fact the having installed everything locally works out-of-the-box and therefore local development is possible. So this setup is just for illustration purpose and a proof of concept that illustrates how the various parts fit together - but beyond this, it currendtly has no further meaning and relevance for the programme as such. 

-> find [more details here](../Remark42/_Remark42_Commenting_TestServer.md)

### Remark42Dev
-> [Project Description](../Remark42Dev/_Remark42Dev.md)



### W=I=R=E
W=I=R=E is the conceputal, all enbracing mothership-programme this VeriVotion project is implementing a part of. 

-> [WIRE SPE-Doc](../../REPO/WIRE/_WIRE.md): SPE-Doc -:|:-  [Key-Docs](../../REPO/WIRE/01_KEY/KEY-Docs.md) -:|:- [Milestones](../../REPO/WIRE/01_KEY/PLAN.md) -:|:- 

## Standards

### Naming Conventions for SoftwareKomponents
All software componeents shall follow the rules of our internal Document about ["Naming Conventions for Architectural Components"]

## Software Stack
### Frontend
* Preact/Redux run from Goland IDE as well. 

### Backend
* Goland on Goland IDE (Backend)
* Libs: Go-Flag, Go-Log, 
* BoltDB (Storage)
* Various Authentication Services (Facebook, Google, Telegram, eMial, Anonymous ...)
* Go Microservices (Backend)

### Operations
* **GitHub**: Sourcecode and Documentation hosting
* Google Cloud Platform (**GCP**) for scalable hosting)
* Docker & **Docker-Compose** (containerized development and deployment)

## Project ADMIN Tools
* **Cmder** (Windows Kommando-Shell)
* **Agent Ransack** (local Search) 
* **Markdown Monster** (doucmentation)
* SPADoc themed **HUGO**  (Website generation)
* Microsoft **Excel** (varous lists)
* **LucidChart** Online (visual concepts)
* **ClickUp** (remote project management, planning, tasklists, WBS, etc.)
* **Mural** (remote brainstorming)
* **Trello**, **Slack**, **Goalscape**, **theBrain** (adhoc team communication)
