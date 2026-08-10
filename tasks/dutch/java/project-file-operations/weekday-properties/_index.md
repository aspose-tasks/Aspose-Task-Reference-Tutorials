---
date: 2026-03-29
description: Leer hoe u dagen per maand kunt wijzigen en andere weekdag‑eigenschappen
  kunt beheren in Aspose.Tasks voor Java. Pas de startdatums van de week aan, wijzig
  de projectkalender en sla het project op als XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wijzig dagen per maand met de Weekdag‑eigenschappen van Aspose.Tasks
url: /nl/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wijzig dagen per maand met Aspose.Tasks Weekdag-eigenschappen

## Introductie
Aspose.Tasks for Java stelt je in staat om **dagen per maand** te wijzigen en andere weekdaginstellingen fijn af te stemmen zonder dat Microsoft Project geïnstalleerd hoeft te zijn. Of je nu een projectkalender afstemt op een niet‑standaard fiscaal maand of simpelweg de startdag van de week moet aanpassen, deze tutorial leidt je door de meest voorkomende scenario's — het ophalen van de huidige startdag van de week, het aanpassen van de startdatum van de week, het wijzigen van de projectkalender en het opslaan van het project als XML.

## Snelle antwoorden
- **Kan ik het aantal dagen per maand wijzigen?** Ja, gebruik `Prj.DAYS_PER_MONTH` op het `Project` object.  
- **Hoe pas ik de startdatum van de week aan?** Stel `Prj.WEEK_START_DAY` in op een `DayType` waarde (bijv. `DayType.Monday`).  
- **Welk formaat kan ik gebruiken om het project te exporteren?** Het voorbeeld slaat het bestand op als XML met `SaveFileFormat.Xml`.  
- **Is een licentie vereist voor productiegebruik?** Een geldige Aspose.Tasks‑licentie is nodig voor niet‑evaluatie‑implementaties.  
- **Welke IDE's worden ondersteund?** Elke Java‑IDE zoals IntelliJ IDEA, Eclipse of NetBeans werkt.

## Wat betekent “dagen per maand wijzigen” in Aspose.Tasks?
Het wijzigen van dagen per maand betekent dat de `Prj.DAYS_PER_MONTH`‑eigenschap van een `Project`‑instantie wordt bijgewerkt. Deze eigenschap vertelt de engine hoeveel werkdagen er per maand in aanmerking moeten worden genomen, wat direct invloed heeft op taakplanning en kostencalculaties.

## Waarom projectkalender‑eigenschappen wijzigen?
Het aanpassen van de projectkalender — zoals het instellen van een andere week startdag of het wijzigen van minuten per dag — helpt je:
- Plannen afstemmen op regionale werkweken.  
- Niet‑standaard werkpatronen modelleren (bijv. 4‑daagse weken).  
- Nauwkeurige rapportage waarborgen voor contracten die aangepaste kalenders gebruiken.

## Vereisten
- **Java Development Kit (JDK)** – Installeer de nieuwste JDK van Oracle.  
- **Aspose.Tasks for Java library** – Download deze van de officiële site [here](https://releases.aspose.com/tasks/java/).  
- **IDE naar keuze** – IntelliJ IDEA, Eclipse of NetBeans.

## Pakketten importeren
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Stap 1: Projectbestand laden
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Dit laadt een bestaand Microsoft Project‑bestand (`project.mpp`) uit de opgegeven map.

## Stap 2: Weekdag‑eigenschappen weergeven
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Hier halen we de huidige weekdaginstellingen op en printen ze, inclusief de **week startdag** en **dagen per maand**.

## Stap 3: Weekdag‑eigenschappen instellen
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
In deze stap **wijzigen we dagen per maand** naar 24, stellen we de week in om op maandag te beginnen, en passen we de minuten per dag/week aan. Dit toont hoe je **projectkalender**‑waarden programmatisch **wijzigt**.

## Stap 4: Project opslaan
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Het gewijzigde project wordt opgeslagen met het **save project as XML**‑formaat, wat handig is voor integratie met andere tools of voor versie‑gecontroleerde opslag.

## Stap 5: Resultaat weergeven
```java
System.out.println("Process completed Successfully");
```
Een eenvoudige bevestiging dat de bewerkingen zonder fouten zijn voltooid.

## Hoe de startdatum van de week aanpassen
Als je organisatie een zondag‑eerste kalender hanteert, vervang dan `DayType.Monday` door `DayType.Sunday`. Dezelfde eigenschap (`Prj.WEEK_START_DAY`) wordt gebruikt, waardoor de wijziging eenvoudig is.

## Hoe de week startdag op te halen
Je kunt op elk moment `project.get(Prj.WEEK_START_DAY)` aanroepen om **de week startdag** op te halen, zoals getoond in Stap 2.

## Hoe de projectkalender te wijzigen
Naast de week startdag kun je ook `Prj.MINUTES_PER_DAY` en `Prj.MINUTES_PER_WEEK` aanpassen om aangepaste werktijden of ploegenschema's weer te geven.

## Veelvoorkomende problemen en oplossingen
- **Onjuiste dagtype‑waarde** – Zorg ervoor dat je de `DayType`‑enum gebruikt (bijv. `DayType.Monday`).  
- **Foutieve bestands‑pad** – Controleer of `dataDir` eindigt op de juiste scheidingsteken (`/` of `\`).  
- **Licentie niet ingesteld** – Als je licentie‑waarschuwingen ziet, registreer dan je Aspose.Tasks‑licentie voordat je het `Project`‑object maakt.

## Veelgestelde vragen

**Q: Kan Aspose.Tasks for Java complexe projectstructuren aan?**  
A: Ja, Aspose.Tasks for Java biedt uitgebreide ondersteuning voor het moeiteloos verwerken van complexe projectstructuren.

**Q: Is Aspose.Tasks for Java compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut, Aspose.Tasks for Java ondersteunt diverse versies van Microsoft Project‑bestanden, waardoor compatibiliteit over platformen heen wordt gegarandeerd.

**Q: Kan ik Aspose.Tasks for Java integreren in mijn bestaande Java‑applicaties?**  
A: Ja, Aspose.Tasks for Java biedt naadloze integratiemogelijkheden, zodat je je Java‑applicaties kunt verrijken met krachtige projectmanagementfuncties.

**Q: Biedt Aspose.Tasks for Java documentatie en ondersteuning?**  
A: Ja, je kunt uitgebreide documentatie en community‑ondersteuning voor Aspose.Tasks for Java vinden op hun [website](https://releases.aspose.com/).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, je kunt een gratis proefversie van Aspose.Tasks for Java downloaden via hun [website](https://reference.aspose.com/tasks/java/) om de functies te verkennen voordat je een aankoop doet.

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}