---
date: 2025-12-04
description: Leer hoe u valutaproperties in Java kunt uitlezen uit MS Project‑bestanden
  met Aspose.Tasks voor Java. Volg deze stapsgewijze handleiding om valutacode, symbool,
  decimalen en positie programmatisch te extraheren.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Valuta‑eigenschappen lezen in Java met Aspose.Tasks‑projecten
url: /nl/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Valuta‑eigenschappen lezen in Java met Aspose.Tasks‑projecten

## Introduction
In deze tutorial **lees je valuta‑eigenschappen Java** uit Microsoft Project‑bestanden met behulp van de Aspose.Tasks for Java‑API. Aspose.Tasks stelt je in staat om met .mpp‑bestanden te werken zonder dat Microsoft Project geïnstalleerd is, waardoor het ideaal is voor geautomatiseerde rapportage, datamigratie of integratie in Java‑gebaseerde enterprise‑applicaties. Aan het einde van deze gids kun je de valutacode, het symbool, het aantal decimale cijfers en de positie van het symbool direct uit een projectbestand extraheren.

## Quick Answers
- **Wat betekent “read currency properties java”?** Het verwijst naar het ophalen van valuta‑gerelateerde metadata (code, symbool, cijfers, positie) uit een MS Project‑bestand met Java‑code.  
- **Heb ik een licentie nodig om dit te proberen?** Een gratis proefversie van Aspose.Tasks is beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke JDK‑versie is vereist?** Java 8 of hoger.  
- **Kan ik de valutainstellingen wijzigen nadat ik ze heb gelezen?** Ja, Aspose.Tasks ondersteunt zowel lees‑ als schrijf‑operaties op valutaproperties.  
- **Is dit compatibel met alle .mpp‑versies?** De API ondersteunt bestanden die zijn aangemaakt met Microsoft Project 2003‑2021.

## What is read currency properties java?
Het lezen van valutaproperties in Java betekent dat je toegang krijgt tot de project‑niveau instellingen die bepalen hoe monetaire waarden worden weergegeven in een Microsoft Project‑bestand. Deze instellingen omvatten de ISO‑valutacode (bijv. **USD**), het symbool (**$**), het aantal decimale cijfers en of het symbool vóór of ná het bedrag wordt geplaatst.

## Why read currency properties java with Aspose.Tasks?
- **Geen Microsoft Project‑installatie nodig** – de API werkt op elk platform dat Java ondersteunt.  
- **Snelle, in‑process extractie** – ideaal voor batchverwerking van grote aantallen projectbestanden.  
- **Volledige controle** – je kunt de opgehaalde waarden combineren met aangepaste rapportage of integreren in ERP‑systemen.  
- **Cross‑versie ondersteuning** – werkt met .mpp‑bestanden van Project 2003 tot en met de nieuwste 2021‑release.

## Prerequisites
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – Java 8 of nieuwer geïnstalleerd en geconfigureerd in je `PATH`.  
2. **Aspose.Tasks for Java JAR** – download de nieuwste bibliotheek van [here](https://releases.aspose.com/tasks/java/) en voeg deze toe aan de classpath van je project.  

## Import Packages
Begin met het importeren van de Aspose.Tasks‑namespace die nodig is voor projectmanipulatie:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
Definieer de map die het `.mpp`‑bestand bevat dat je wilt analyseren. Het pad in een variabele plaatsen maakt de code herbruikbaar:

```java
String dataDir = "Your Data Directory";
```

*Vervang `"Your Data Directory"` door het absolute of relatieve pad naar de map waar `project.mpp` zich bevindt.*

## Step 2: Create a Project Reader Instance
Laad het Microsoft Project‑bestand in een `Project`‑object. Dit object geeft je toegang tot alle project‑eigenschappen, inclusief de valutainstellingen:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Als je bestand een andere naam heeft, wijzig dan `"project.mpp"` dienovereenkomstig.*

## Step 3: Display Currency Properties
Haal nu elk valutatribuut op met behulp van de `Prj`‑enumeratie en print de resultaten naar de console. De API retourneert objecten die je naar strings kunt converteren voor weergave:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Wat je zult zien:**  
- **Currency Code** – ISO‑4217‑code zoals `USD`, `EUR`, `JPY`.  
- **Currency Digits** – meestal `2` voor de meeste valuta’s, `0` voor de Japanse Yen.  
- **Currency Symbol** – het teken dat in rapporten wordt getoond (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` voor **voor** het bedrag, `1` voor **na** het bedrag.

## Step 4: Process Completion
Geef aan dat de extractie succesvol is afgerond. Dit eenvoudige bericht is handig wanneer de code wordt uitgevoerd als onderdeel van een grotere batch‑taak:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir`‑pad is onjuist of de bestandsnaam is verkeerd gespeld. | Controleer de directory‑string en zorg ervoor dat het `.mpp`‑bestand bestaat op de opgegeven locatie. |
| **NullPointerException on `project.get(...)`** | Het projectbestand bevat geen valutainformatie (onwaarschijnlijk) of de property‑sleutel is fout. | Gebruik `project.contains(Prj.CURRENCY_CODE)` om het bestaan te controleren vóór het lezen. |
| **LicenseException** | Uitvoeren zonder een geldige Aspose.Tasks‑licentie in een productieomgeving. | Pas een licentiebestand toe met `License license = new License(); license.setLicense("Aspose.Tasks.lic");` vóór het aanmaken van het `Project`‑object. |

## Frequently Asked Questions

**Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?**  
A: Aspose.Tasks ondersteunt .mpp‑bestanden die zijn gegenereerd door Microsoft Project 2003‑2021, zowel oudere als de nieuwste formaten.

**Q: Can I modify currency properties using Aspose.Tasks?**  
A: Ja, je kunt zowel lezen als schrijven van valutainstellingen. Gebruik `project.set(Prj.CURRENCY_CODE, "EUR");` en sla vervolgens het project op.

**Q: Is Aspose.Tasks suitable for commercial use?**  
A: Absoluut. Het is een commerciële bibliotheek; je kunt een licentie aanschaffen [here](https://purchase.aspose.com/buy).

**Q: Does Aspose.Tasks offer a free trial?**  
A: Ja, een volledig functionele proefversie is beschikbaar via [here](https://releases.aspose.com/).

**Q: Where can I seek help or support for Aspose.Tasks?**  
A: Het officiële Aspose.Tasks‑forum is de beste plek voor ondersteuning – bezoek het [here](https://forum.aspose.com/c/tasks/15).

## Conclusion
Je hebt nu geleerd hoe je **read currency properties java** kunt uitvoeren op een MS Project‑bestand met Aspose.Tasks for Java. Deze mogelijkheid stelt je in staat om valutametadata op te nemen in aangepaste rapporten, financiële analyses of integratie‑pijplijnen zonder afhankelijk te zijn van Microsoft Project zelf. Voel je vrij om te experimenteren met het wijzigen van de eigenschappen het combineren van deze data met andere project‑attributen om rijkere oplossingen te bouwen.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}