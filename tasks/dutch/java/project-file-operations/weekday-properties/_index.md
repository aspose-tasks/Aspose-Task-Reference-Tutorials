---
date: 2025-12-23
description: Leer hoe je Aspose Tasks Java gebruikt om het projectrooster bij te werken,
  de startdag van de week in te stellen, het aantal dagen per maand te wijzigen en
  de projectkalender efficiënt aan te passen.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Beheren van weekdag‑eigenschappen
url: /nl/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Weekdag Eigenschappen Beheren

## Inleiding
Aspose.Tasks for Java (aspose tasks java) is een robuuste API die Java‑ontwikkelaars in staat stelt met Microsoft Project‑bestanden te werken zonder dat Microsoft Project geïnstalleerd hoeft te zijn. In deze tutorial leer je hoe je een MPP‑bestand **laadt**, **de startdag van de week instelt**, **het aantal dagen per maand wijzigt**, en anderszins **de projectkalender aanpast** — allemaal essentiële stappen voor het bijwerken van een projectschema. Aan het einde kun je de weekdag‑eigenschappen programmatically aanpassen en de wijzigingen opslaan in het gewenste formaat.

## Snelle antwoorden
- **Wat is de primaire klasse voor het verwerken van projecten?** `Project` uit de Aspose.Tasks‑bibliotheek.  
- **Hoe wijzig ik de startdag van de week?** Gebruik `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Kan ik een bestaand .mpp‑bestand laden?** Ja — instantiate `Project` met het bestandspad.  
- **Welke methode slaat het project op als XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor evaluatie; een licentie is vereist voor productie.

## Voorvereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

- **Java Development Kit (JDK)** – de nieuwste versie geïnstalleerd.  
- **Aspose.Tasks for Java library** – download het [hier](https://releases.aspose.com/tasks/java/).  
- **Een IDE** zoals IntelliJ IDEA, Eclipse of NetBeans.  

## Importpakketten
Om te beginnen importeer je de essentiële Aspose.Tasks‑klassen:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Laten we nu elke stap van het beheren van weekdag‑eigenschappen doorlopen.

## Stap 1: Een MPP‑bestand Laden
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Hier **laden we een bestaand .mpp‑bestand** (`load mpp file`) zodat we de kalendersettings kunnen inspecteren en aanpassen.*

## Stap 2: Huidige Weekdag‑Eigenschappen Weergeven
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Deze code print de huidige **startdag van de week**, **dagen per maand**, **minuten per dag**, en **minuten per week** — de kernonderdelen die je vaak nodig hebt om de **projectkalender aan te passen**.

## Stap 3: Nieuwe Weekdag‑Eigenschappen Instellen
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
In deze stap **stellen we de startdag van de week** in op maandag, **wijzigen we het aantal dagen per maand** naar 24, en passen we de dagelijkse en wekelijkse minuutenaantallen aan. Deze instellingen zijn typisch wanneer je het **projectschema moet bijwerken** om overeen te komen met een niet‑standaard werkrooster.

## Stap 4: Het Bijgewerkte Project Opslaan
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Het aangepaste project wordt opgeslagen als een XML‑bestand, waardoor het eenvoudig te delen of te importeren is in andere tools.

## Stap 5: De Operatie Bevestigen
```java
System.out.println("Process completed Successfully");
```
Een eenvoudige console‑melding laat je weten dat de workflow zonder fouten is voltooid.

## Veelvoorkomende problemen & tips
- **Onjuist bestandspad** – Controleer of `dataDir` eindigt op een slash of gebruik `Paths.get(...)` voor platformonafhankelijke paden.  
- **Licentie niet ingesteld** – Roep in een productie‑omgeving `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` aan voordat je `Project` maakt.  
- **Onverwachte startdag van de week** – Zorg ervoor dat je de juiste `DayType`‑enumwaarde gebruikt (bijv. `DayType.Sunday`).  

## Veelgestelde vragen

**V: Kan Aspose.Tasks for Java complexe projectstructuren verwerken?**  
**A: Ja, Aspose.Tasks for Java biedt uitgebreide ondersteuning voor het eenvoudig verwerken van complexe projectstructuren.**

**V: Is Aspose.Tasks for Java compatibel met verschillende versies van Microsoft Project‑bestanden?**  
**A: Absoluut, Aspose.Tasks for Java ondersteunt verschillende versies van Microsoft Project‑bestanden, waardoor compatibiliteit over platformen heen wordt gegarandeerd.**

**V: Kan ik Aspose.Tasks for Java integreren in mijn bestaande Java‑applicaties?**  
**A: Ja, Aspose.Tasks for Java biedt naadloze integratiemogelijkheden, zodat je je Java‑applicaties kunt verrijken met krachtige projectmanagementfuncties.**

**V: Biedt Aspose.Tasks for Java documentatie en ondersteuning?**  
**A: Ja, je kunt uitgebreide documentatie en community‑ondersteuning voor Aspose.Tasks for Java vinden op hun [website](https://releases.aspose.com/).**

**V: Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?**  
**A: Ja, je kunt een gratis proefversie van Aspose.Tasks for Java downloaden van hun [website](https://reference.aspose.com/tasks/java/) om de functies te verkennen voordat je een aankoop doet.**

---

**Laatst bijgewerkt:** 2025-12-23  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}