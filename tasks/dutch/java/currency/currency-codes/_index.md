---
date: 2026-09-25
description: Leer hoe u valutacodes uit MS Project‑bestanden kunt ophalen met Aspose.Tasks
  voor Java – de snelle manier om de valutacode te krijgen die Java‑ontwikkelaars
  nodig hebben.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Beheer valutacodes in Aspose.Tasks
og_description: Ophalen valutacode java uit MS Project‑bestanden met Aspose.Tasks.
  Deze gids laat zien hoe u het project leest, de ISO‑valuta‑identifier extraheert
  en toepast in Java‑applicaties.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Ophalen valutacode java uit MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Ophalen valutacode java uit MS Project met Aspose.Tasks
url: /nl/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ophalen valutacode java uit MS Project met Aspose.Tasks

## Inleiding
In deze tutorial leer je **hoe je valutacode java kunt ophalen** uit een MS Project‑bestand met behulp van de Aspose.Tasks Java‑API. Of je nu multi‑valuta financiële rapporten moet genereren, projecten over verschillende regio's moet consolideren, of simpelweg het juiste monetaire symbool in een downstream‑systeem wilt weergeven, de onderstaande stappen nemen je mee van de omgeving‑configuratie tot de één‑regelige aanroep die de ISO‑valutacode retourneert. Aan het einde van de gids kun je elk ondersteund Project‑bestandformaat laden en de drie‑letterige valutacode zoals `USD`, `EUR` of `GBP` extraheren.

## Snelle antwoorden
- **Wat doet de API?** Het leest MS Project‑bestanden en maakt eigenschappen zoals de valutacode beschikbaar.  
- **Welke taal wordt gebruikt?** Java, via de Aspose.Tasks voor Java‑bibliotheek.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik de code in één regel ophalen?** Ja—`prj.get(Prj.CURRENCY_CODE)` retourneert de valutacode‑string onmiddellijk.  
- **Is het compatibel met alle Project‑versies?** Aspose.Tasks ondersteunt meer dan 20 invoerformaten, inclusief legacy MPP-, XML- en XER‑bestanden.

## Wat is een gelezen MS Project‑bestand?
Het lezen van een MS Project‑bestand betekent het programmatisch openen van een *.mpp* (of een ander ondersteund formaat zoals XML of XER) en toegang krijgen tot de interne datastructuren. Deze structuren omvatten taken, resources, kalenders, kostentabellen en financiële instellingen. Door het bestand te parseren kun je informatie extraheren zonder Microsoft Project te starten, waardoor geautomatiseerde rapportage, migratie en integratieworkflows mogelijk worden.

## Waarom Aspose.Tasks gebruiken om msproject‑bestanden te lezen?
Aspose.Tasks biedt een pure‑Java‑oplossing die de noodzaak voor COM‑interop of een lokale Microsoft Project‑installatie wegneemt. Het ondersteunt meer dan 20 bestandsformaten, kan projecten met duizenden taken verwerken terwijl het minder dan 100 MB geheugen gebruikt, en biedt een rijk objectmodel. Directe toegang tot constanten zoals `Prj.CURRENCY_CODE` stelt je in staat valutainformatie onmiddellijk en betrouwbaar op te halen.

## Voorvereisten
Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

### Java Development Kit (JDK) geïnstalleerd
Een recente JDK (11 of hoger) is vereist. Download deze van de officiële Oracle‑site: [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks voor Java‑bibliotheek
Verkrijg de nieuwste Aspose.Tasks voor Java‑binaries en voeg ze toe aan de classpath van je project. De volledige documentatie en downloadlinks zijn beschikbaar [hier](https://reference.aspose.com/tasks/java/).

## Importer pakketten
De `Project`‑klasse en de `Prj`‑constanten bevinden zich in de `com.aspose.tasks`‑namespace. Importeer ze bovenaan je Java‑bronbestand:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Stapsgewijze handleiding

### Stap 1: gegevensdirectory instellen
Definieer de map die je *.mpp*‑bestand bevat. Pas het pad aan zodat het overeenkomt met je omgeving zodat de runtime het projectbestand kan vinden.

```java
String dataDir = "Your Data Directory";
```

### Stap 2: laad het projectbestand
De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel MS Project‑bestand in het geheugen vertegenwoordigt. Het aanmaken van een instantie leest het bestand en bouwt een in‑memory model dat je kunt bevragen.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Stap 3: haal valutacode op
De `Prj.CURRENCY_CODE`‑constante identificeert de eigenschap die de ISO‑valutacode opslaat. Het aanroepen van `prj.get(Prj.CURRENCY_CODE)` retourneert de drie‑letterige code in één enkele bewerking.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
De uitvoer zal de drie‑letterige ISO‑valutacode zijn (bijv. `USD`, `EUR`, `GBP`) die het project gebruikt.

### Stap 4: hoe valutacode op te halen in Java (extra context)
Laad je project, roep `prj.get(Prj.CURRENCY_CODE)` aan en sla het resultaat op in een `String`. Je kunt deze waarde vervolgens doorgeven aan elke financiële service, rapportage‑engine of UI‑component die een valutacode vereist.

### Stap 5: (optioneel) gebruik de valutacode
Typische downstream‑scenario's omvatten:

- **Rapportgeneratie** – plaats de code voor de kostkolommen (`USD 1,200`).  
- **API‑integratie** – stuur de ISO‑code naar betalingsgateways die een valutaparameter vereisen.  
- **Gegevensconsolidatie** – groepeer meerdere projecten op valuta voor portfolio‑niveau analyse.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Null-uitvoer** | Projectbestand definieert geen valuta (standaard is leeg). | Stel de valuta in Microsoft Project in of wijs deze toe via `prj.set(Prj.CURRENCY_CODE, "USD");` vóór het lezen. |
| **Bestand niet gevonden** | Onjuist `dataDir`‑pad. | Controleer het pad en zorg ervoor dat de bestandsnaam exact overeenkomt, inclusief hoofdlettergevoeligheid. |
| **Niet‑ondersteunde bestandsversie** | Zeer oud of beschadigd *.mpp*‑bestand. | Upgrade naar de nieuwste Aspose.Tasks‑versie of converteer het bestand eerst naar een nieuwer formaat in Microsoft Project. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks complexe projectstructuren aan?**  
A: Ja, de API leest hiërarchieën met meerdere taakniveaus, resource‑pools, aangepaste velden en kalenders zonder beperking.

**Q: Is Aspose.Tasks compatibel met verschillende versies van MS Project‑bestanden?**  
A: Absoluut. Het ondersteunt MPP, XML, XER en andere formaten van Project 98 tot de nieuwste Office‑releases.

**Q: Biedt Aspose.Tasks documentatie en ondersteuning?**  
A: Een uitgebreide API‑referentie, code‑voorbeelden en toegewijde technische ondersteuning zijn beschikbaar op de Aspose‑website.

**Q: Kan ik Aspose.Tasks uitproberen voordat ik koop?**  
A: Er wordt een gratis proefversie aangeboden zodat je alle functies kunt evalueren, inclusief het extraheren van valutacodes.

**Q: Waar kan ik een tijdelijke licentie voor evaluatie verkrijgen?**  
A: Tijdelijke licenties zijn beschikbaar via de [website](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-09-25  
**Getest met:** Aspose.Tasks for Java (latest version)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Projecteigenschappen Java – Metagegevens lezen met Aspose.Tasks](/tasks/java/project-properties/)
- [Hoe projectinformatie te lezen uit Microsoft Project met Aspose.Tasks voor Java](/tasks/java/project-properties/read-project-info/)
- [MS Project Outline‑codes ophalen in Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}