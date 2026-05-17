---
date: 2026-02-10
description: Leer hoe u Java‑projecteigenschappen, zoals het valutasymbool, kunt extraheren
  en bijwerken met Aspose.Tasks voor Java. Verander de projectvaluta en haal het valutasymbool
  eenvoudig op.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: java‑projecteigenschappen – Valutasymbool extraheren uit MPP met Aspose.Tasks
  voor Java
url: /nl/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Valutasymbool uit MPP halen met Aspose.Tasks voor Java

## Inleiding
In deze tutorial leer je hoe je werkt met **java project properties** — specifiek hoe je het valutasymbool uit een Microsoft Project (MPP) bestand haalt en hoe je **change currency symbol java** of **retrieve currency symbol java** gebruikt met de Aspose.Tasks bibliotheek. Of je nu een rapportagetool bouwt, Project‑gegevens integreert in een financieel systeem, of simpelweg het juiste valutasymbool in je UI moet weergeven, het beheersen van deze kleine maar essentiële taak maakt je Java‑applicaties robuuster en gebruiksvriendelijker.

## Snelle antwoorden
- **Wat betekent “extract currency symbol mpp”?** Het betekent het lezen van het valutasymbool dat is opgeslagen in een MPP (Microsoft Project) bestand.  
- **Welke bibliotheek behandelt dit?** Aspose.Tasks for Java biedt een eenvoudige API voor deze taak.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Hoe lang duurt het?** Met de onderstaande code kun je het symbool in minder dan een minuut verkrijgen.  
- **Kan ik het symbool ook wijzigen?** Ja – je kunt een nieuwe waarde instellen met dezelfde `Prj.CURRENCY_SYMBOL` eigenschap.

## Wat is “extract currency symbol mpp”?
Microsoft Project slaat het valutasymbool (bijv. $, €, £) op in de header van het projectbestand. De **extract currency symbol mpp** bewerking leest die waarde zodat je het programmatisch kunt weergeven of manipuleren.

## Waarom het valutasymbool bijwerken in java project properties?
Projecten bestrijken vaak meerdere regio's. Het kunnen **change project currency** of **update currency symbol** tijdens runtime stelt je in staat rapporten, facturen of dashboards aan te passen aan de lokale markt zonder het hele projectbestand opnieuw te maken. Deze flexibiliteit is een kernonderdeel van het effectief beheren van java project properties.

## Vereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de [Aspose.Tasks downloadpagina](https://releases.aspose.com/tasks/java/).  
3. Een geldig **project.mpp** bestand geplaatst in een map die je vanuit je code kunt refereren.

## Pakketten importeren
Importeer eerst de klassen die we nodig hebben om met Project‑bestanden te werken.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Stap 1: Definieer de gegevensdirectory
Geef de applicatie aan waar je *.mpp* bestand zich bevindt.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Gebruik `System.getProperty("user.dir")` om een absoluut pad te bouwen dat op elke machine werkt.

## Stap 2: Laad het MS Project‑bestand
Maak een `Project` object dat het MPP‑bestand in het geheugen vertegenwoordigt.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Stap 3: Haal (en wijzig optioneel) het valutasymbool op
Nu **retrieve currency symbol java** door de `Prj.CURRENCY_SYMBOL` eigenschap te lezen. Je kunt ook **change currency symbol java** (of **change project currency**) door een nieuwe string toe te wijzen aan dezelfde eigenschap.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

De `System.out.println` oproep drukt het symbool (bijv. `$`) af naar de console, wat bevestigt dat de extractie geslaagd is.

## Veelvoorkomende problemen & hoe ze op te lossen
| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| `NullPointerException` op `project.get(...)` | Verkeerd bestandspad of bestand niet gevonden | Controleer `dataDir` en bestandsnaam; gebruik `new File(dataDir).exists()` om te debuggen |
| Onverwacht symbool (bijv. `?`) | Project aangemaakt met een niet‑standaard locale | Zorg ervoor dat het bron‑MPP‑bestand daadwerkelijk een valutasymbool definieert; je kunt er een programmatically instellen zoals hierboven getoond |
| Licentiefout | Gebruik van de proefversie zonder een geldig licentiebestand | Laad je licentie met `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` voordat je het `Project` object maakt |

## Veelgestelde vragen

**Q: Kan ik andere projectattributen dan valutasymbolen manipuleren met Aspose.Tasks?**  
A: Ja, Aspose.Tasks laat je taken, resources, toewijzingen, kalenders en nog veel meer projecteigenschappen bewerken.

**Q: Is Aspose.Tasks compatibel met verschillende versies van MS Project‑bestanden?**  
A: Absoluut. Het ondersteunt MPP, MPT en XML‑formaten van Project 98 tot de nieuwste releases.

**Q: Biedt Aspose.Tasks documentatie en ondersteuning voor ontwikkelaars?**  
A: Uitgebreide API‑documentatie, code‑voorbeelden en een speciaal ondersteuningsforum zijn beschikbaar op de Aspose.Tasks‑website.

**Q: Kan ik Aspose.Tasks uitproberen voordat ik het koop?**  
A: Ja – een volledig functionele gratis proefversie kan worden gedownload van de [Aspose‑website](https://purchase.aspose.com/buy).

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?**  
A: Tijdelijke licenties worden verstrekt op de [Aspose tijdelijke‑licentiepagina](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

---

**Laatst bijgewerkt:** 2026-02-10  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}