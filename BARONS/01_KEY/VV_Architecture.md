---
locpath: C:\me\ACTIVE\VeriVotion\01_KEY\VV_Architecture.md

author: rene.baron@baronsolutions.ch
created: 06.05.2022 09:51:40
version: draft v0.0.1
draft: true
private: false
disqid: DiscussID
tags: ["aktiv", "***", "bré"]
categories: ["Hugo", "Intern"]
---

# VeriVotion: Solution Architecture Blueprint
`rene.baron@baronsolutions.ch | bré | Mai 06, 2022 | draft work in progress v0.0.1 | updated Mai 06, 2022`

---

This document outlines the

> **"core components and key third-party solutions that together make the VeriVotion comments and voting plugin for Webpages"**

---

<div style="background-color:#DFFF00; border-style:solid; border-color:#DFFF00; border-width:20px;">
<span style="font-weight:bold">Links</span>

* [Project Charter](../VeriVotion_Charter.md) -:|:- [Handbook](../VeriVotion_PRJ_Handbook.md) -:||:- [Log](VeriVotion_LOG.md)

* [WIRE Architectural Blueprint](../../../REPO/WIRE/01_KEY/BluePrint.md)

* [Remark42](../../../REPO/work/TOOLS/H/HUGO/COMMENTS/EVAL/Remark42/_Remark42.md)
</div>

---

## Design principles
1. **Security and Data-Protection first** (built in compliance from day one is key)
2. **Web-First** (mobile second)
3. **No-RealTime** (Realtime messaging is something completely different from what we are trying to achieve here). 


## Core Components
The overall VeriVotion programme splits into the following core components:

a) **Commenting Plugin** 
b) **Frontend Server** from where it is served and which further provides a demo-Website that illustates how the Commenting Plugin needs to be mounted in customer websites
c) **Backend Server** that stores all comments and deals with authentication provides such as FB, Google, etc. 
d) The **Votioner** Kialo.com scraper project the creates testdata
e) **W=I=R=E-Programme** activities that provide all the ideological famework and marketing aspects of the overall program

![](../xPIC/VV-Architecture.png)

### Commenting Plugin
This is a piece of HTM/JS-Code that renders the Commenting interface for Authentication, listing and filtering existing comments and n authoring new ones. This Commenting Plugin is hosted by the Frontend Web-Application Server that is explained below. 

### Frontend Web-Application Server
The Application Server provides the Commenting Plugin for Client-Websites and further provides a demo-website that illustrates how the Commenting Plugin has to be mounted in generic customer websites. 

### Backend Server
The BackendServer provides the Database and does all the authentication and security work. 

### Votioner
a commandline tool (developed in the context of the Votioner porject) for scraping pre-existing comments form various online-forums such as Kialo.com. Scraped comments will be written into a standardized JSON file from where it can be loaded into the Bachend Server's DB. 



## Source Projects
The following project have helpe us a lot in terms of sourcecode and project management settings and experiencs. 
### Remark42 Commenting and Voting Tool
[Remark42](../../../REPO/work/TOOLS/H/HUGO/COMMENTS/EVAL/Remark42/_Remark42.md) is built with a React/Redux bases Frontend and a Go-Backend, similar to the the one I have used along the [Bot project](), and has an active and supporting GitHub community. 

### WatCon Bot-Project (dropped)
Reviewing the former WatCon-Bot Project for Sympany insurance company for the project artefacts and the documdented React/Redux-Source-Code for interactive commenting and Aurelia for reporting might be reused for our VV-project. 