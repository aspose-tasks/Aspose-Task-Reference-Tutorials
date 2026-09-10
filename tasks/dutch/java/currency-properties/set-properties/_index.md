---
date: 2026-09-09
description: Leer hoe u het valutateken wijzigt in Aspose.Tasks Java‑projecten, valutacodes
  instelt, symbolen aanpast en aangepaste opmaak toepast voor Microsoft Project‑bestanden.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Valuta‑eigenschappen instellen in Aspose.Tasks-projecten
og_description: Hoe het valutateken te wijzigen in Aspose.Tasks met Java. Ontdek stapsgewijze
  instructies, vereisten en tips om de kostenopmaak van projecten aan te passen.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Hoe het valutateken te wijzigen in Aspose.Tasks – Java‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Hoe het valutateken te wijzigen in Aspose.Tasks-projecten – Java‑gids
url: /nl/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe het valutateken te wijzigen in Aspose.Tasks – Java‑gids

## Inleiding
In deze tutorial leer je **hoe je het valutateken** wijzigt voor een Microsoft Project‑bestand met behulp van de Aspose.Tasks Java‑API. Of je nu rapporten voorbereidt voor een buitenlandse klant, budgetten consolideert over meerdere regio's, of simpelweg de boekhoudnormen van je bedrijf moet volgen, het aanpassen van het valutateken zorgt ervoor dat elk kosten‑gerelateerd veld het juiste monetaire teken weergeeft. De gids doorloopt elke stap, van het opzetten van de ontwikkelomgeving tot het opslaan van de wijzigingen in een nieuw of bestaand projectbestand.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java.  
- **Kan ik het valutateken wijzigen?** Ja – stel `Prj.CURRENCY_SYMBOL` in en kies `CurrencySymbolPositionType`.  
- **Welke bestandsformaten worden ondersteund?** XML, MPP en vele andere via `SaveFileFormat`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een basisopzet.

## Hoe het valutateken te wijzigen in Aspose.Tasks met Java?
Laad het doelproject (of maak een nieuw project), stel de gewenste valutaproperties in en sla het bestand op. De volledige bewerking bestaat uit drie API‑aanroepen: een `Project`‑object maken of laden, de valutacode, het symbool en de positie toewijzen, en vervolgens `project.save` aanroepen. Deze aanpak werkt zowel voor nieuwe projecten als voor bestaande bestanden zonder dat Microsoft Project geïnstalleerd hoeft te zijn.

## Waarom Aspose.Tasks gebruiken om het valutateken te wijzigen?
Aspose.Tasks biedt **volledige API‑dekking voor meer dan 30 valutagerelateerde eigenschappen**, waardoor je code, symbool, decimale cijfers en positionering op één plek kunt definiëren. De bibliotheek verwerkt multi‑honderd‑pagina Project‑bestanden in minder dan een seconde op typische serverhardware, en werkt op Windows, Linux en macOS zonder extra afhankelijkheden.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK) 8 of hoger** – de API vereist minimaal JDK 8.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de [Aspose.Tasks downloadpagina](https://releases.aspose.com/tasks/java/).  
3. **Een IDE** – Eclipse, IntelliJ IDEA, of elke editor die Java ondersteunt.  
4. **Een beschrijfbare map** – waar het gegenereerde projectbestand wordt opgeslagen.

## Pakketten importeren
De volgende klassen geven toegang tot projecteigenschappen, bestandsafhandeling en valutainstellingen.

`Project` – vertegenwoordigt een Microsoft Project‑bestand in het geheugen.  
`Prj` – bevat constanten voor alle project‑niveau eigenschappen, inclusief valutavelden.  
`CurrencySymbolPositionType` – somt mogelijke posities voor het valutateken op (voor of na het bedrag).

Deze imports zijn vereist voordat code een project kan manipuleren.

## Stapsgewijze handleiding

### Stap 1: Definieer de gegevensdirectory
Kies een map die je bronbestanden bevat en waar de uitvoer wordt weggeschreven. Zorg ervoor dat de map bestaat en dat je Java‑proces schrijfrechten heeft.

### Stap 2: Maak een nieuw project‑instance
De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel Project‑bestand in het geheugen vertegenwoordigt. Een instantie ervan maken creëert een leeg project dat klaar is voor configuratie.

### Stap 3: Stel valutaproperties in
Hier configureer je de valutacode, het aantal decimale cijfers, het symbool zelf, en de positie van het symbool.

- **Valutacode** – een drie‑letterige ISO‑4217‑code zoals `AUD` of `USD`.  
- **Decimale cijfers** – meestal 2 voor de meeste valuta's.  
- **Valutateken** – het teken of de tekenreeks die bij bedragen wordt weergegeven, bv. `$` of `€`.  
- **Symboolpositie** – `CurrencySymbolPositionType.Before` plaatst het symbool vóór het getal; `After` plaatst het erna.

Deze instellingen beïnvloeden elk kosten‑gerelateerd veld (resource‑tarieven, taakbudgetten, enz.) in het project.

> **Pro tip:** Als je de valuta voor een bestaand bestand moet wijzigen, laad het dan met `new Project("file.mpp")` voordat je de bovenstaande instellingen toepast.

### Stap 4: Sla het bijgewerkte project op
Schrijf het project terug naar schijf met het gewenste formaat. Het XML‑formaat is mens‑leesbaar, terwijl `SaveFileFormat.MPP` volledige compatibiliteit met Microsoft Project behoudt.

### Stap 5: Bevestig succes
Print een korte boodschap of logvermelding zodat je weet dat de bewerking zonder fouten is voltooid. Dit is vooral nuttig in geautomatiseerde pipelines.

## Veelvoorkomende problemen & oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`NullPointerException` on `project.save`** | `dataDir` is geen geldig pad of heeft geen schrijfrechten. | Zorg ervoor dat de map bestaat en dat je Java‑proces schrijfrechten heeft. |
| **Valutateken wordt niet weergegeven** | De symboolpositie is onjuist ingesteld voor je locale. | Gebruik `CurrencySymbolPositionType.Before` als het symbool vóór het bedrag moet staan. |
| **Projectbestand opent niet in MS Project** | Opslaan in een ouder formaat met incompatibele instellingen. | Sla op met `SaveFileFormat.MPP` voor volledige compatibiliteit met recente MS Project‑versies. |

## Veelgestelde vragen

**Q: Kan ik meerdere valuta's in één project instellen met Aspose.Tasks?**  
A: Ja, je kunt verschillende valutainstellingen toewijzen aan individuele resources of taken door hun respectieve kostvelden te wijzigen nadat de project‑niveau valuta is gedefinieerd.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut. De bibliotheek ondersteunt MPP‑bestanden van Project 2000 tot de nieuwste releases, evenals XML en andere uitwisselformaten.

**Q: Biedt Aspose.Tasks ondersteuning voor aangepaste valutavormen?**  
A: Ja, je kunt aangepaste symbolen, decimale cijfers en positionering definiëren om te voldoen aan elke regionale eis, en deze instellingen worden bewaard in het opgeslagen bestand.

**Q: Kan ik Aspose.Tasks integreren met andere Java‑frameworks?**  
A: Zeker. De API is pure Java, dus werkt naadloos met Spring, Hibernate, Maven, Gradle en andere ecosystemen.

**Q: Waar kan ik extra hulp of voorbeelden vinden?**  
A: Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor community‑ondersteuning, of raadpleeg de officiële documentatie voor gedetailleerde API‑referenties.

## Conclusie
Je weet nu **hoe je het valutateken** kunt wijzigen in Aspose.Tasks‑projecten met Java, hoe je de valutacode instelt, decimale cijfers aanpast en een aangepast symbool toepast. Deze mogelijkheden stellen je in staat om locale‑specifieke kostrapporten te genereren, projectbudgetten af te stemmen op regionale boekhoudnormen, en je Microsoft Project‑bestanden consistent te houden binnen wereldwijde teams.

---

**Laatst bijgewerkt:** 2026-09-09  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Gerelateerde tutorials

- [java-projecteigenschappen – Valutateken extraheren uit MPP met Aspose.Tasks voor Java](/tasks/java/currency/currency-symbols/)
- [Valuta‑eigenschappen lezen Java met Aspose.Tasks‑projecten](/tasks/java/currency-properties/read-properties/)
- [Valutacodes beheren Java met Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}