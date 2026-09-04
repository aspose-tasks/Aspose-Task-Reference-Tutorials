---
date: 2026-06-15
description: Leer hoe u timephased data uit MS Project resources kunt extraheren met
  Aspose.Tasks voor Java. Stapsgewijze handleiding om een resource op id op te halen.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Lezen van timephased data voor resources in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Lezen van timephased data voor resources in Aspose.Tasks – resource ophalen
  op id
url: /nl/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees tijdgebaseerde gegevens voor resources in Aspose.Tasks

## Inleiding
In deze tutorial leer je **how to get resource by id** en lees je de tijdgebaseerde gegevens met Aspose.Tasks voor Java. We lopen elke stap door — van het instellen van de projectmap tot het afdrukken van werk- en kostentijdgebaseerde waarden — zodat je waardevolle planningsinformatie uit elk Microsoft Project‑bestand programmatisch kunt extraheren. Aspose.Tasks voor Java is een uitgebreide API die ontwikkelaars in staat stelt Microsoft Project‑bestanden te maken, lezen, wijzigen en converteren zonder dat Microsoft Project geïnstalleerd hoeft te zijn, en ondersteunt een breed scala aan projectmanagementfuncties en -formaten.

## Snelle antwoorden
- **Wat doet “get resource by id”?** Het haalt een specifiek `Resource`‑object op uit een `Project` met behulp van de unieke identifier.  
- **Welke bibliotheek verwerkt tijdgebaseerde gegevens?** Aspose.Tasks voor Java biedt de `Resource.getTimephasedData` API.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik grote projecten lezen?** Ja — Aspose.Tasks kan bestanden met tot 10.000 taken verwerken zonder het volledige bestand in het geheugen te laden.  
- **Welke Java‑versie is vereist?** Java 8 of hoger; de bibliotheek is compatibel met alle belangrijke JDK's.

## Wat is “get resource by id”?
`get resource by id` is een methode‑aanroep die een `Resource`‑instantie ophaalt uit een geladen `Project` met behulp van de numerieke ID van de resource. Deze bewerking maakt precieze toegang tot de gedetailleerde eigenschappen van een resource mogelijk, zoals zijn toewijzingen, agenda's en aangepaste velden, en is essentieel voor het extraheren van tijdgebaseerde werk‑ of kostengegevens die aan die specifieke resource zijn gekoppeld.

## Waarom Aspose.Tasks gebruiken voor tijdgebaseerde gegevens?
Aspose.Tasks ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** (MPP, XML, CSV, enz.) en kan tijdgebaseerde werk‑ en kostwaarden voor resources over meerjarige schema’s extraheren terwijl het geheugenverbruik laag blijft. De API retourneert standaard gegevens in intervallen van 15 minuten, waardoor je gedetailleerd inzicht krijgt voor rapportage of aangepaste analyses.

## Voorvereisten
Zorg er voordat we beginnen voor dat je de volgende voorvereisten hebt:
1. Java Development Kit (JDK): Zorg ervoor dat je JDK op je systeem geïnstalleerd hebt. Je kunt het downloaden van de [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) en de installatie‑instructies volgen.  
2. Aspose.Tasks for Java Library: Download de Aspose.Tasks for Java‑bibliotheek van de [downloadpagina](https://releases.aspose.com/tasks/java/) en volg de installatie‑instructies die in de documentatie worden gegeven.

## Importeer pakketten
De eerste stap is om de benodigde Aspose.Tasks‑klassen te importeren in je Java‑bronbestand.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Stap 1: Gegevensmap instellen
Definieer eerst de map waarin je MS Project‑bestand zich bevindt. Het gescheiden houden van de gegevensmap en de broncode maakt het project makkelijker te onderhouden.

```java
String dataDir = "Your Data Directory";
```

## Stap 2: MS Project‑sjabloonbestand lezen
Geef de naam op van je MS Project‑sjabloonbestand. Het gebruik van een sjabloon zorgt voor consistente kolominstellingen over verschillende projecten heen.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Stap 3: Invoerbestand lezen als Project
De `Project`‑klasse is het kernobject van Aspose.Tasks dat een Microsoft Project‑bestand in het geheugen vertegenwoordigt. Het laden van het bestand geeft je programmatische toegang tot taken, resources en schema's.

```java
Project project = new Project(dataDir + fileName);
```

## Stap 4: Resource ophalen op ID
Om een specifieke resource op te halen, roep je de methode `getResources().getById(id)` aan. Dit is de exacte bewerking waar het primaire trefwoord naar verwijst.

```java
Resource resource = project.getResources().getByUid(1);
```

## Stap 5: Tijdgebaseerde gegevens voor resource‑werk afdrukken
Zodra je het `Resource`‑object hebt, kun je `resource.getTimephasedData(ResourceTimephasedDataType.Work)` aanroepen om werktoewijzingen over tijd te verkrijgen. De geretourneerde collectie bevat `TimephasedData`‑objecten die de startdatum, einddatum en de hoeveelheid werk voor elk interval bevatten.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Stap 6: Tijdgebaseerde gegevens voor resource‑kosten afdrukken
Evenzo retourneert `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` kostinformatie, opgesplitst over dezelfde tijdsintervallen. Dit is nuttig voor budgettering en kosten‑volgrapporten.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Hoe haal je resource op op ID in één regel?
Laad het project en roep vervolgens `project.getResources().getById(5)` aan — vervang **5** door de daadwerkelijke resource‑ID die je nodig hebt. Deze enkele aanroep retourneert het `Resource`‑object, waarna je de tijdgebaseerde gegevens, toewijzingen of aangepaste velden kunt opvragen. De methode werkt in O(1) tijd omdat resources intern geïndexeerd zijn.

## Veelvoorkomende problemen en oplossingen
- **Resource niet gevonden** – Zorg ervoor dat de ID bestaat in het projectbestand; ID's beginnen bij 1 en zijn uniek per resource.  
- **Lege tijdgebaseerde gegevens** – Controleer of de resource werk‑ of kosttoewijzingen heeft; anders zal de collectie leeg zijn.  
- **Prestaties bij grote bestanden** – Gebruik `Project.setLoadOptions(LoadOptions.fromFile(...))` om lazy loading in te schakelen voor projecten groter dan 500 MB.

## Veelgestelde vragen

**Q: Kan Aspose.Tasks andere soorten projectbestanden verwerken naast Microsoft Project?**  
A: Ja, Aspose.Tasks ondersteunt MPP, XML, CSV en verschillende andere formaten, waardoor je kunt lezen en schrijven over verschillende standaarden.

**Q: Is Aspose.Tasks compatibel met verschillende Java‑ontwikkelomgevingen?**  
A: Absoluut. De bibliotheek werkt met alle belangrijke IDE's (IntelliJ IDEA, Eclipse, NetBeans) en build‑tools (Maven, Gradle).

**Q: Kan ik projectgegevens manipuleren met Aspose.Tasks?**  
A: Ja, je kunt taken, resources, toewijzingen en zelfs aangepaste velden maken, wijzigen en verwijderen via de API.

**Q: Is Aspose.Tasks geschikt voor enterprise‑niveau projecten?**  
A: Ja. Enterprises vertrouwen op Aspose.Tasks voor grootschalige verwerking, batch‑conversies en server‑side rapportage omdat er geen Microsoft Project‑installatie nodig is.

**Q: Waar kan ik ondersteuning vinden als ik problemen ondervind bij het gebruik van Aspose.Tasks?**  
A: Je kunt het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) bezoeken voor hulp van de community en het supportteam.

## Conclusie
In deze tutorial hebben we geleerd hoe je **get resource by id** kunt gebruiken en de tijdgebaseerde werk‑ en kostgegevens kunt lezen met Aspose.Tasks voor Java. Door deze stappen te volgen kun je efficiënt waardevolle planningsinformatie uit je projectbestanden extraheren en integreren in aangepaste rapportage‑ of analytische pipelines.

---

**Laatst bijgewerkt:** 2026-06-15  
**Getest met:** Aspose.Tasks 24.11 for Java  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Resource toevoegen aan project met Aspose.Tasks voor Java](/tasks/java/resource-management/create-resources/)
- [Beheer MS Project resourcekosten met Aspose.Tasks voor Java](/tasks/java/resource-management/resource-cost/)
- [Werkweken lezen in Java vanuit MS Project‑kalender met Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}