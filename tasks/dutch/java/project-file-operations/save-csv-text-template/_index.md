---
date: 2025-12-21
description: Leer hoe u een project als sjabloon opslaat, MPP exporteert naar CSV
  en MPP converteert naar tekst met Aspose.Tasks voor Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Project opslaan als sjabloon, CSV en tekst met Aspose.Tasks voor Java
url: /nl/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project opslaan als sjabloon, CSV en tekst met Aspose.Tasks

## Introductie
In deze tutorial ontdek je **hoe je een project als sjabloon kunt opslaan** en ook hoe je je Microsoft Project‑bestanden (MPP) kunt exporteren naar CSV‑ en platte‑tekstformaten met de Aspose.Tasks‑bibliotheek voor Java. Of je nu een herbruikbaar projectsjabloon wilt maken, CSV‑rapporten voor analyse wilt genereren, of eenvoudige tekst‑extracten voor integratie wilt produceren, deze stappen begeleiden je snel en efficiënt door het proces.

## Snelle antwoorden
- **Kan ik MPP naar CSV exporteren?** Ja – gebruik `project.save(..., SaveFileFormat.CSV)`.  
- **Hoe exporteer ik tekst?** Sla op met `SaveFileFormat.TEXT`.  
- **Wat doet “project opslaan als sjabloon”?** Het maakt een `.mpt`‑bestand aan dat de feitelijke en baseline‑waarden verwijdert, klaar voor hergebruik.  
- **Heb ik een licentie nodig?** Er is een proefversie beschikbaar; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8+ wordt ondersteund.

## Wat is “project opslaan als sjabloon”?
Een project opslaan als sjabloon (`.mpt`) legt de structuur, taakhiërarchie en resource‑toewijzingen vast terwijl de feitelijke start‑/einddatums en baseline‑gegevens worden verwijderd. Dit maakt het sjabloon ideaal om een standaard projectindeling herhaaldelijk te gebruiken in meerdere nieuwe projecten.

## Waarom Aspose.Tasks voor Java gebruiken?
Aspose.Tasks stelt je in staat Microsoft Project‑bestanden te manipuleren zonder Microsoft Project zelf te installeren. Het ondersteunt **hoe je MPP exporteert**, **hoe je tekst exporteert**, en **MPP naar CSV converteert**, alles vanuit pure Java‑code, perfect voor server‑side automatisering, CI‑pipelines of desktop‑hulpmiddelen.

## Vereisten
Voordat we beginnen, zorg dat je het volgende hebt:

1. Java Development Kit (JDK) 8 of hoger geïnstalleerd.  
2. Aspose.Tasks voor Java‑bibliotheek toegevoegd aan je project. Download deze van [hier](https://releases.aspose.com/tasks/java/).  
3. Basiskennis van Java‑syntaxis en Maven/Gradle‑projectopzet.

## Pakketten importeren
Importeer eerst de benodigde klassen in je Java‑bronbestand:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Project opslaan als CSV (MPP exporteren naar CSV)
Een MPP‑bestand naar CSV exporteren is handig voor data‑analyse in Excel of BI‑tools.

### Stap 1: Het project laden
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Stap 2: Opslaan als CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Project opslaan als tekst (Hoe tekst exporteren)
Als je een platte‑tekstrepresentatie van taken, resources of toewijzingen nodig hebt, sla je het project op als een tekstbestand.

### Stap 1: Het project laden
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Stap 2: Opslaan als tekst
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Project opslaan als sjabloon (Project sjabloon maken in Java)
Een herbruikbaar sjabloon maken verwijdert feitelijke datums en baselines, waardoor een schoon skelet voor nieuwe projecten ontstaat.

### Stap 1: Het project laden
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Stap 2: Sjabloonopties instellen
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Stap 3: Opslaan als sjabloon
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Veelvoorkomende problemen & tips
- **Bestand niet gevonden:** Zorg ervoor dat het naar `YourProject.mpp` correct is of gebruik een absoluut pad.  
- **Licentie‑uitzonderingen:** Zonder een geldige licentie draait de bibliotheek in evaluatiemodus en kan watermerken toevoegen. Pas je licentie vroeg in de code toe (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Grote projecten:** Voor zeer grote MPP‑bestanden, overweeg de JVM‑heapgrootte te verhogen (`-Xmx2g`) om `OutOfMemoryError` te voorkomen.

## Conclusie
We hebben behandeld **hoe je een project als sjabloon opslaat**, evenals hoe je **MPP naar CSV exporteert** en **MPP naar tekst converteert** met Aspose.Tasks voor Java. Deze mogelijkheden stellen je in staat projectdata te automatiseren, herbruikbare sjablonen te genereren en projectinformatie in andere systemen te integreren — allemaal zonder Microsoft Project geïnstalleerd te hebben.

## Veelgestelde vragen
### V: Kan Aspose.Tasks voor Java complexe projectbestanden aan?
A: Absoluut! Aspose.Tasks voor Java kan projecten van uiteenlopende complexiteit moeiteloos verwerken en biedt uitgebreide ondersteuning voor Microsoft Project‑bestandsformaten.  
### V: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
A: Ja, je kunt een gratis proefversie van Aspose.Tasks voor Java verkrijgen via [hier](https://releases.aspose.com/).  
### V: Waar vind ik ondersteuning voor Aspose.Tasks voor Java?
A: Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor hulp of vragen over Aspose.Tasks voor Java.  
### V: Kan ik een tijdelijke licentie aanschaffen voor Aspose.Tasks voor Java?
A: Ja, je kunt een tijdelijke licentie kopen via [hier](https://purchase.aspose.com/temporary-license/), zodat je de volledige mogelijkheden van de bibliotheek kunt evalueren.  
### V: Is Aspose.Tasks voor Java compatibel met verschillende besturingssystemen?
A: Ja, Aspose.Tasks voor Java is compatibel met diverse besturingssystemen, waaronder Windows, macOS en Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest)  
**Auteur:** Aspose  

---