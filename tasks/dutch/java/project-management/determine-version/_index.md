---
date: 2026-05-31
description: Leer hoe u de projectversie kunt ophalen en de laatst opgeslagen datum
  kunt opvragen uit MS Project-bestanden met Aspose.Tasks voor Java. Stapsgewijze
  gids met code-voorbeelden.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Projectversie bepalen met Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hoe de projectversie op te halen – Aspose Tasks Java-tutorial
url: /nl/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de projectversie op te halen – Aspose Tasks Java Tutorial

In deze **Aspose Tasks Java tutorial** leer je **hoe je de projectversie kunt ophalen** van een Microsoft Project‑bestand en ook hoe je de **laatste opgeslagen datum** kunt **ophalen** met behulp van de Aspose.Tasks‑bibliotheek voor Java. Het kennen van de bestandsversie en het opslagtijdstip helpt je compatibiliteitsproblemen te vermijden, migratie‑beleid af te dwingen en nauwkeurige audit‑logboeken bij te houden. We lopen elke stap door — van het opzetten van de omgeving tot het afdrukken van de versie en datum — zodat je deze controle in elke Java‑applicatie kunt integreren met vertrouwen.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Het bepalen van de MS Project‑bestandversie en de laatst‑opgeslagen datum met Aspose.Tasks voor Java.  
- **Heb ik Microsoft Project geïnstalleerd nodig?** Nee, Aspose.Tasks werkt onafhankelijk van Microsoft Project.  
- **Welke bestandsformaten worden ondersteund?** XML‑gebaseerde Project‑bestanden zoals MPP en XML worden volledig ondersteund.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een eenvoudige versiecontrole.  
- **Is een licentie vereist?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productiegebruik.

## Wat is de Aspose Tasks Java Tutorial?
De `Aspose.Tasks` Java‑tutorial is een beknopte, praktische gids die laat zien hoe je programmatically met Microsoft Project‑gegevens kunt werken. Het laat zien hoe je projectinformatie kunt lezen, wijzigen en analyseren zonder dat Microsoft Project op de server geïnstalleerd hoeft te zijn. Bovendien behandelt het het laden van bestanden, het benaderen van eigenschappen en het opslaan van wijzigingen, waardoor ontwikkelaars project‑beheertaken efficiënt kunnen automatiseren.

## Waarom Aspose.Tasks gebruiken om de projectversie te bepalen?
Aspose.Tasks biedt **exacte versie‑metadata** en **laatst‑opgeslagen tijdstempels** terwijl het draait op elk besturingssysteem dat Java ondersteunt. Het verwerkt bestanden tot **500 pagina's in minder dan 2 seconden** op een standaard 2,5 GHz CPU, waardoor het ideaal is voor batch‑automatisering en grootschalige migratiescenario's.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks for Java JAR** – download van de [website](https://releases.aspose.com/tasks/java/) en voeg toe aan de classpath van je project.  
3. **MS Project‑bestand** – een XML‑gebaseerd Project‑bestand (bijv. `input.xml`) dat je wilt inspecteren.  

> **Pro tip:** Sla het Project‑bestand op in een speciale `data`‑map om paden overzichtelijk te houden en onbedoelde overschrijvingen te voorkomen.

## Importeer pakketten
Eerst importeer je de essentiële Aspose.Tasks‑klassen:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Hoe de projectdirectory in te stellen
Om je projectbestanden correct te vinden, maak je een speciale map binnen de structuur van je applicatie en sla je daar alle invoerbestanden op. Dit houdt de code overzichtelijk en voorkomt pad‑gerelateerde fouten bij het laden van bestanden. Gebruik een duidelijke variabelenaam voor het mappad, die absoluut of relatief ten opzichte van de project‑root kan zijn.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute of relatieve pad waar `input.xml` zich bevindt.

## Hoe het project te laden
`Project` is het primaire Aspose.Tasks‑object dat een Microsoft Project‑bestand in het geheugen vertegenwoordigt, waardoor je toegang krijgt tot alle project‑eigenschappen en collecties. Na het aanmaken van de `Project`‑instantie kun je zijn velden opvragen, over taken itereren of gegevens wijzigen voordat je het bestand weer opslaat op schijf.

```java
Project project = new Project(dataDir + "input.xml");
```

Als je bestand een andere naam heeft, pas dan `"input.xml"` dienovereenkomstig aan.

## Hoe de projectversie te bepalen
`Prj.SAVE_VERSION` is een eigenschap die het versienummer aangeeft van Microsoft Project dat het bestand heeft opgeslagen. `Prj.LAST_SAVED` is een eigenschap die de datum en tijd opslaat waarop het bestand voor het laatst is opgeslagen. `Prj.SAVE_VERSION` geeft de numerieke versie van de Microsoft Project‑applicatie terug die het bestand heeft opgeslagen (bijv. 12 voor Project 2010). `Prj.LAST_SAVED` levert de exacte datum en tijd van de meest recente opslaactie.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Deze waarden stellen je in staat om programmatically versie‑specifieke bedrijfsregels af te dwingen of audit‑rapporten te genereren.

## Hoe het resultaat weer te geven
Nadat je de versie‑ en laatst‑opgeslagen informatie hebt opgehaald, wil je deze meestal naar de console of een logbestand schrijven. Gebruik `System.out.println` om de waarden weer te geven, waarbij je de datum naar behoefte formatteert. Dit bevestigt dat de extractie geslaagd is en biedt directe feedback tijdens ontwikkeling of in geautomatiseerde scripts.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `NullPointerException` on `project.get(...)` | Bestand niet gevonden of pad onjuist | Controleer `dataDir` en bestandsnaam; gebruik een absoluut pad voor testen. |
| Onverwacht versienummer (bijv. 0) | Een niet‑Project XML‑bestand laden | Zorg ervoor dat het bestand een geldig Microsoft Project‑bestand is (MPP/XML). |
| Licentie‑exception | De proefversie gebruiken zonder geldige licentie in productie | Pas je Aspose.Tasks‑licentie toe (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks ondersteunt .NET, Java en C++ onder andere.

**Q: Is Aspose.Tasks geschikt voor grootschalige projecten?**  
A: Absoluut; het kan projecten van meerdere honderden pagina's in seconden verwerken zonder het volledige bestand in het geheugen te laden.

**Q: Kan ik projectgegevens aanpassen met Aspose.Tasks?**  
A: Ja, je kunt taken, resources, kalenders en elk ander projectelement via de API wijzigen.

**Q: Vereist Aspose.Tasks een Microsoft Project‑installatie?**  
A: Nee, de bibliotheek werkt onafhankelijk en heeft geen Microsoft Project op de hostmachine nodig.

**Q: Is technische ondersteuning beschikbaar voor Aspose.Tasks?**  
A: Ja, je kunt hulp krijgen via het Aspose.Tasks‑forum [hier](https://forum.aspose.com/c/tasks/15).

**Aanvullende Q&A**

**Q: Hoe haal ik andere projecteigenschappen op (bijv. auteur, bedrijf)?**  
A: Gebruik `project.get(Prj.AUTHOR)` of `project.get(Prj.COMPANY)` op dezelfde manier als je de versie ophaalt.

**Q: Kan ik de versie van een MPP (binair) bestand controleren?**  
A: Ja, Aspose.Tasks laadt `.mpp`‑bestanden direct; de `Prj.SAVE_VERSION`‑eigenschap werkt ook voor binaire formaten.

**Q: Is er een manier om programmatically een ouder projectbestand naar een nieuwere versie te upgraden?**  
A: Laad het oudere bestand en sla het vervolgens op met `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks schrijft het bestand standaard in het nieuwste formaat.

## Conclusie
Je hebt nu geleerd **hoe je de projectversie kunt ophalen** en **de laatst opgeslagen datum** uit MS Project‑bestanden te **verkrijgen** met Aspose.Tasks voor Java. Integreer deze fragmenten in automatiserings‑pipelines, rapportagetools of migratie‑hulpmiddelen om er zeker van te zijn dat je altijd de exacte Project‑versie kent waarmee je werkt.

---

**Laatst bijgewerkt:** 2026-05-31  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Project startdatum instellen in MS Project met Aspose.Tasks voor Java](/tasks/java/project-properties/write-project-info/)
- [Microsoft Project-database lezen met Aspose.Tasks voor Java](/tasks/java/project-data-reading/read-project-database/)
- [Project opslaan als sjabloon, CSV en tekst met Aspose.Tasks voor Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}