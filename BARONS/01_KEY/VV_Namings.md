---
locpath: C:\me\ACTIVE\VeriVotion\01_KEY\VV_Namings.md

author: rene.baron@baronsolutions.ch
created: 11.05.2022 08:38:00
version: draft v0.0.1
draft: true
private: false
disqid: DiscussID
tags: ["aktiv", "***", "bré"]
categories: ["wire", "keydoc", "intern"]
---

<h1 style="font-family: 'Trebuchet MS'; font-weight: bold;">=W<span style="color: #4169e1;">-</span>I<span style="color: #ff8c00;">-</span>R<span style="color: #4169e1;">-</span>E=</h1>
<p style="font-family: 'Trebuchet MS';"><b style="font-size: 8pt;"> &#160;a Baron Solutions project</b></p>
        
<h1 style="text-align: center;">Naming Conventsions for the VeriVotion Project</h1>

`rene.baron@baronsolutions.ch | bré | Mai 11, 2022 | draft work in progress v0.0.1 | updated Mai 11, 2022`

---

This <span style="font-family: 'Trebuchet MS'; font-weight: bold;">=W<span style="color: #4169e1;">-</span>I<span style="color: #ff8c00;">-</span>R<span style="color: #4169e1;">-</span>E=</span> document answers the following questions: 

> **""**

---

<div style="background-color:#DFFF00; border-style:solid; border-color:#DFFF00; border-width:20px;">
<span style="font-weight:bold">Links</span>

* [JS Programming Guidelines](../../../REPO/work/ENTITY/SE/JS/JS_Guidelines.md)

* [JSON Standard](../../../REPO/work/ENTITY/SE/JS/GLOSSARY/J/JSON.md)

</div>

---

## Areas of Application
Areas where the herein listed naming conventions are applied: 

* Namen für gehostete Apps und Services und deren öffentliche URLs und APIs
  
* Projektverzeichnisse für den SourceCode
  
* Projektnamen für die zugehörigen Softwareprojekte (Editor, Testumgebung, Build-Jobs, etc.)
  
* Stagingverzeichnisse für kundenspezifische Konfigurationen  

* [AppLilst](VV_AppList.md)

* [JavaScript Programming](../../../REPO/work/ENTITY/SE/JS/JS_Guidelines.md)

## Why Naming-conventions matter
Cloud-hosting environments such as IBM BlueMix - for security reasons - do not allow reusing (deletion and new creation) of application names, that have already been used in the past. 

## General Rules
Meaningful Names are great to remember but will create chaos in larger environments with different, parallel maintained and running instances for different versions, languages, clients etc. 

Therefore we have come up with more "operations" names that are compiled from a secquence of well defined codes, where all such parts having all specific meaning. The such compiled names will tell us much more about a given instance, file- oder directory name than any adhoc name will ever provide. 

Such parts might iclude codes for

* **Ownership** = Programmezugehörigkeit in der Entwicklung oder Ownership beim Kunden.  

* **AppStatus** = Stand der Entwicklung und Verwendungszweck

## Part I :: Building Blocks

### Owner
A well choosen 3-6+ letter **"Owner"-Code** has different Purpose for Development and Operations. 

#### Development
In Development the Owner-Code corresponds with the Programme or Project-Code (such as VV for the VeriVotion-Project) the Artefact is created with. 

In der Entwicklung legt dieser Code fest, zu welchem Grossprojekt/Programme, welcher "Tech"-Inititative etc. das Softwareprojekt gehört, welches Thema es abdeckt und wer dafür zustündig ist (interner Owner).

#### Production
In Production/Operations the Owner-Code is a reference to either the Department that Owns the instace (such as `MAR` for Marketing) or is referencing the External Customer such as  `UBSh05` for UBS Zurich Headquarters. 

### Current Owner-Codes
Currently are using the following Owner Codes

#### Development

* **VV**: Everything related to the VeriVotion project

* **WIRE** Everything that is related to the W=I=R=E programme

#### Internal Hosting

* **VVA**: Everything internally hosted in the AWS Cloud
* **VVG**: Everything internally hosted in the Google Cloud
* **VVI**: Everything internally hosted in the IBM Cloud

#### Production

* **UBSh05**: UBS Headquarters Zurich (hosted by customer)
* **CH01**: Swiss Government, Bundesamt für Migration, Bern (hosted by customer)
* **SG01**: Kantonsparlament des Kantons St. Gallen, Abteilung Kommunikation, St. Gallen

## Service Codes
Service Codes denote the Type of Service used from Cloud-Providers

* **DB**: Database-Services
* **TXT**: Fileserver for documentation (clear-text)
* **CDN**: Content Distribution Network for any kind of files


## Application Status
Code for the Application-Status are referring to the stage in the development/product life-cycle. Such status is important for SLAs, Quality-Assurance, Change-management, Backup, Audits, etc. 

* **A** = (`ass`):  Assessment, früher Pilot, unfertig, kann jederzeit gelöscht werden

* **B** = (`beta`) Beta Version einer bald für die Produktion freigegebenen Version

* **C** = (`cancel`) Cancelled: Aus irgendwelchen Gründen momentan verworfende oder gestoppte Version

* **D** = (`dev`) Development = laufende Entwicklung

* **E** = (`edu`) Demo-, Verkaufs-, Schulungs- oder Trainingssystem mit Schulungsdaten etc.

* **F** = (`fin`) Final: Fertig erstellter, qualitätsgeprüfter SourceCode und Runtime-Built bereit fürs Stagen

* **S** = (`stage`) Stageing Version: Grundlage/Kopie der kundenspezifisch angepasste Kundenversionen

* **O** = (`ops`) Operative: Kundenspezifische Installation im laufenden Betrieb

* **P** = (`prod`) Produkt, representiert das fertige, ausgelieferte Standalone-Produkt-Paket.

Further wie have a special AppStatus for "TestSystem" = **XT**

Praktisch wird in jeder Phase in irgendeiner Form getested bevor die Phase als abgeschlossen gilt. Deshalb gibt es (im Gegensatz zu früher) keinen App Status = "Test" mehr!

Tests werden meist in separaten Testumgebungen durchgeführt. Diese werden mit einem zusätzlichen, und ein dem Lifecyclecode angehängtes "**T**" markiert.

---

## Part II :: Namings für Apps

### App-Names for Dev-Versions
Der grundlegende App(Stamm)namen beinhaltet eine aufsteigende AppNummer ohne weitere Bedeutung, eine Kurzbeschreibung der App sowie eine vom Chef-Entwickler vergebenen, immer aufsteigendeVersionsnummer:

<p style="font-size: 20pt;text-align: left;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<u style="font-weight: bold; font-size: 20pt; color: #000000;">A</u><i><b style="font-size: 20pt; color: #ff0000;">nn</b><span style="color: #008000;"><b><i><b style="font-size: 20pt;">-Be-schrei-bung-</b><span style="color: #a9a9a9;"><span style="color: #008000;"><span style="color: #8a2be2;"><span style="color: #000000;font-style: normal;font-weight: bold;"><span style="font-size: 24pt;"><span style="font-size: 20pt; text-decoration: underline;">V</span></span></span><span style="color: #a9a9a9;font-weight: bold;"><span style="font-size: 24pt;"><span style="font-size: 20pt; color: #8a2be2;">vv</span></span></span></span></span></span></i></b></span></i></p>

* **A** = fix für "Application"  

* **nn** = Applikationsnummer (aufsteigend, eindeutig, nächste in der AppList des Projekts)

* **Be-schrei-bung** = Bindestrichseparierte Kurzbeschreibung für Art und Nutzen der App

* **V** = fix für "Version"

**vv** = VERSIONS-Nummer des SourceCodes. (diese NICHT mit der INSTANZ-Nummer der gehosteten Instanzen verschseln! Das Mapping zwischen Instanznummer und Versionsnummer erfolgt in der AppList.xls)

**Exmaples:**

* `A01-BotServer-V01`
* `A02-API-React-Client-V12`

Anmerkung zum Stammnamen

Der Stammname `Ann-Be-schrei-bung` wird in allen von dieser App abgeleiteten Instanzen wiederholt!


### gehostete App Instanzen:
Sobald eine App lokal stabil läuft wird sie unter einem von der Version unabhängigen HostingNamen als eigenständige Instanz in der Cloud mit folgemden Instanz = HostingNamen angelegt:

<p style="text-align: left;"><span style="color: #ff8c00;font-weight: bold;"><span style="font-size: 28pt;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-size: 20pt;"><i>Owner</i>-<u style="font-weight: bold; font-size: 20pt; color: #000000;">A</u><i><b style="font-size: 20pt; color: #ff0000;">nn</b></i></span></span></span><b><i><span style="color: #008000;"><b><i><b style="font-size: 20pt;">-Be-schrei-bung-</b><span style="color: #a9a9a9;"><span style="color: #008000;"><span style="color: #8a2be2;"><span style="color: #a9a9a9;font-weight: bold;"><span style="font-size: 28pt;"><span style="font-size: 20pt;">i</span></span></span><span style="color: #808080;font-weight: bold;"><span style="font-size: 28pt;"><span style="font-size: 20pt;">i</span></span></span><b style="font-size: 20pt;">-Z</b></span></span></span></i></b></span></i></b></p>

Dabei ist der mit Ann-Be-schrei-bung gebildete AppStammname identisch mit demjenigen der EntwicklerApp

* **Owner** = OwnerCode
* **A** = fix für "Application"
* **nn** = Applikationsnummer (aufsteigend, eindeutig, nächste in der AppList des Projekts)
* **Be-schrei-bung** = Kurzbeschreibung für Art und Nutzen der App
* **ii** = INSTANZ-Nummer der auf Bluemix gehosteten Instanz
* (NICHT mit der VERSIONSnummer des Sourcecodeszu verwechseln! Das Mapping zwischen Instanznummer und Versionsnummer erfolgt in der AppList.xls)
* **Z** = Kurzzeichen für den App Status Code

Examples


    Netlive-WatCon-01-T

Netlive hostet IBM Watson Conversaton Service Instanze #01 zum Testen

Teil IV :: Projektverzeichnisse
Je nach Reifegrad der jeweiligen App (Entwicklung, Test, Stageing, Schulung, Produktion) werden jeweils eigene Instanzen in separaten Verzeichnisssen erstellt und getestet. Diese Verzeichnisse enthalten deshalb meist nur Instanzen eines bestimmten App Status und haben standardmässig die folgenden Namen:




## 40 DEV (EntwicklerVerzeichnis)
Hauptsächliches, projektmässige geführte Verzeichnis der Entwicklungsabteilung inkl. Prototypen, Evaluation, Integrations/ArchitekturTests - geht es überhaupt? 
beinhaltet SourceCode mit App-Status A,B,C,D

### 41 TEST (TestVerzeichnis)
beinhaltet die Testvarianten mit App-Status A,B,C, D. resp AT, BT, CT und DT für die Testinstanzen

### 42 CLEAN (Qualitätsgeprüftes Pre-Pack/Stage Verzeichnis)
beinhaltet gereinigten, qualitätsüberprüften Code mit App-StatusD und die dazugehörigen DT
(A,B,C haben hier nichts zu suchen) gem. Projekthandbuch (Namenskonventionen, Best Practice, etc.)
Basis für die nachfolgenden Packs/Builds

### 43 PACK
Die aus den Clean-Versionen der D-Klassen erstellten GENERISCHEN Built Versionen (Minified, uglified, secure, compressed, ...) als fertiges Softwarepackage und damit Grundlage für die Schulung, Stageing, Produktion oder ProduktRelease-Instanzen.

Enthält deshalb nur Code mit App-Status F.

### 44 STAGE (BereitstellungsVerzeichnis)

Kundenspezifisch konfigurierte Kopien der beim Kunden installierten Systeme.
Alles was benötigt wird um die App via cf-Kommando hochzuladen
Verzeichnisname stimmt mit der Bluemix APP InstanzID im Kundenzielsystem überein
Enthält nur S-Instanzen

### 45 EDU
RuntimeVersionen für die aktuelle (interne) Schulung
Enthält nur E-Instanzen

### 46 DEMO
Generische RuntimeVersionen für adhoc Kundenpräsentationen
Enthält nur E-Instanzen

### 47 OPS
Runtime Versionen für die intern operativ verwendeten Instanzen
Enthält nur O-Instanzen

### 47 PROD
Runtime Versionen für die als Produkt vermarkteten Versionen
Enthält nur P-Instanzen

### 48 MAINT
temporäre Kopien von Produktivsystemen für die Analyse und Wartung

### 49 ARCHIVE
Museum als Inspirationsquelle für Entwickler


## Docs

### Folders

### Markdown Files

## App-Instances


## Source-Code