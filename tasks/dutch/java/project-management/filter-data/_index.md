---
date: 2026-06-05
description: Leer hoe u MPP-bestanden kunt filteren met Aspose.Tasks for Java, filtercriteria
  kunt aanpassen en taken op datum kunt filteren om projectbeheer te stroomlijnen.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Hoe MPP-bestanden filteren met Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hoe MPP-bestanden filteren met Aspose.Tasks for Java
url: /nl/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe MPP-bestanden filteren met Aspose.Tasks voor Java

## Inleiding
Als je werkt met Microsoft Project‑bestanden (*.mpp*) in een Java‑applicatie, moet je vaak **MPP‑bestanden filteren** om de taken, resources of toewijzingen te isoleren die het belangrijkst zijn. In deze tutorial lopen we stap voor stap door **hoe je mpp‑bestanden** programmatically filtert met Aspose.Tasks voor Java, laten we zien hoe je **filtercriteria kunt aanpassen**, en demonstreren we een praktisch “filter taken op datum” scenario. Aan het einde heb je een kant‑klaar fragment dat je in elk Java‑project kunt gebruiken.

## Snelle antwoorden
- **Wat betekent “filter mpp”?** Het betekent een deelverzameling van projectgegevens extraheren op basis van gedefinieerde voorwaarden.  
- **Welke bibliotheek behandelt dit?** Aspose.Tasks voor Java biedt een uitgebreide API voor het maken en toepassen van filters.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik taken, resources en toewijzingen filteren?** Ja – elk entiteitstype heeft zijn eigen filtercollectie.  
- **Is Java 8 of hoger vereist?** Aspose.Tasks ondersteunt Java 8 en latere versies.

## Wat is “how to filter mpp” in Java?
`How to filter mpp` is het proces waarbij je Aspose.Tasks‑`Filter`‑objecten gebruikt om alleen die projectelementen te selecteren die voldoen aan specifieke predicaten zoals startdatum, kosten of aangepaste velden. Laad een `Project`, haal een `Filter` op, en de API retourneert een collectie die aan je criteria voldoet, waardoor gerichte rapportage of downstream‑integratie mogelijk wordt.

## Waarom filtercriteria aanpassen?
Aangepaste filtercriteria stellen je in staat om high‑risk‑taken, achterstallige items of resources met budgetoverschrijding te targeten, waardoor een enorm projectbestand wordt omgezet in een beknopt, actiegericht overzicht. Aspose.Tasks ondersteunt **meer dan 50 vooraf gedefinieerde filtertypen** en laat je onbeperkt aangepaste filters bouwen, waardoor handmatig data‑siften tot wel 70 % wordt verminderd.

## Voorvereisten
Zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of nieuwer.  
2. **Aspose.Tasks voor Java** – download het van de [downloadpagina](https://releases.aspose.com/tasks/java/).  
3. **Een IDE** – IntelliJ IDEA, Eclipse of NetBeans werkt prima.  

## Pakketten importeren
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` en `Project` zijn kernklassen die worden gebruikt om filters te definiëren en toe te passen op projectgegevens.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Stapsgewijze handleiding

### Stap 1: Het project instellen
Maak eerst een `Project`‑instantie die verwijst naar het MPP‑bestand dat je wilt analyseren, en laad het vervolgens in het geheugen. Deze enkele stap bereidt het volledige projectmodel voor op filteren, validatie en verdere manipulatie, waardoor je via de API toegang krijgt tot taken, resources en toewijzingen.

### Hoe stel ik het project in om MPP‑bestanden te filteren?
De `Project`‑klasse laadt en vertegenwoordigt een MPP‑bestand in het geheugen. Maak een `Project`‑instantie die verwijst naar het MPP‑bestand dat je wilt analyseren, en laad het vervolgens in het geheugen. Deze enkele stap bereidt het volledige projectmodel voor op filteren, validatie en verdere manipulatie, waardoor je via de API toegang krijgt tot taken, resources en toewijzingen.

### Hoe kan ik een filter ophalen en inspecteren?
`Filter`‑objecten omvatten filterdefinities die worden gebruikt om projectitems te selecteren. Aspose.Tasks slaat vooraf gedefinieerde filters op zoals “All Tasks” of “Critical Tasks”. Gebruik `project.getTaskFilters().getByName("My Filter")` of index‑gebaseerde toegang om een `Filter`‑object te verkrijgen, en bekijk vervolgens de `FilterCriteria`‑collectie om elke regel en de logische operator (AND/OR) die ze combineert te zien, zodat het filter aan je eisen voldoet.

### Hoe doorloop ik geneste criteria‑rijen?
`FilterCriteriaGroup` vertegenwoordigt een groep filtercriteria die zijn gecombineerd met een logische operator. Filters kunnen groepen criteria bevatten, elk met een eigen operator. Loop door `filter.getCriteria().getRows()` en, voor elke rij die een `FilterCriteriaGroup` is, recursief door de onderliggende rijen. Deze traversatie laat je de complexe filterlogica volledig begrijpen, zoals “(Start < vandaag AND Cost > 1000) OR Priority = High”, en de criteria naar behoefte aanpassen.

### Hoe print ik criteria‑informatie voor debugging?
Na het doorlopen van de criteria‑boom, geef je voor elke rij de veldnaam, testoperator en waarde weer in de console. Deze eenvoudige dump helpt je verifiëren dat het filter overeenkomt met de beoogde bedrijfsregels voordat je het op grote projecten toepast, en maakt het makkelijker om onjuiste operators of waarden te ontdekken.

### Hoe maak ik programmatically een gloednieuwe filter?
Instantieer een `Filter` met `new Filter("My Filter")`, en voeg deze toe aan de taakfiltercollectie van het project via `project.getTaskFilters().add(filter)`. Voeg daarna de gewenste rijen toe aan de `FilterCriteria`‑collectie, met veldnamen, testoperators en waarden om precies te definiëren welke taken moeten worden opgenomen wanneer het filter wordt toegepast.

### Kan ik een filter toepassen op resources in plaats van taken?
De `ResourceFilters`‑collectie bevat filterdefinities die van toepassing zijn op resources. Ja – gebruik `project.getResourceFilters()` om met resourcespecifieke filters te werken op dezelfde manier als taakfilters. Na het toevoegen of ophalen van een filter, configureer je de `FilterCriteria` net zoals bij taken, en pas je het vervolgens toe op de resource‑collectie om de gefilterde set resources te verkrijgen.

### Is het mogelijk om meerdere filters te combineren met OR‑logica?
Maak een bovenliggende `FilterCriteriaGroup` met de `Operation` ingesteld op `OR`, en voeg individuele `FilterCriteria`‑objecten als kinderen toe. Deze groep evalueert elk kindcriterium en retourneert items die aan een van hen voldoen, waardoor je verschillende eenvoudige filters kunt combineren tot een bredere selectie.

### Ondersteunt Aspose.Tasks filteren op aangepaste velden?
De `CustomField`‑enum biedt identifiers voor aangepaste velden die in een project zijn gedefinieerd. Absoluut. Verwijs naar aangepaste velden via de `CustomField`‑enum; ze gedragen zich als elk ingebouwd veld in filterexpressies. Je kunt ze opnemen in `FilterCriteria`‑rijen, met dezelfde operators en waarden, waardoor krachtige queries op door de gebruiker gedefinieerde data naast standaard projectattributen mogelijk zijn.

### Welke impact heeft filteren op de prestaties bij grote MPP‑bestanden?
Filteren gebeurt volledig in het geheugen en verwerkt doorgaans een project met 1.000 taken in minder dan 200 ms. Voor projecten met duizenden taken, overweeg dan om alleen de benodigde secties te laden met `ProjectReader` en pas filters toe na selectief laden, zodat het geheugenverbruik laag blijft en de responstijd snel is, zelfs bij zeer grote projecten.

---

**Laatst bijgewerkt:** 2026-06-05  
**Getest met:** Aspose.Tasks voor Java 24.10  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Laad MPP‑bestand Java - Beheer projecteigenschappen met Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Moeiteloos MS Project Online‑gegevens lezen](/tasks/java/project-data-reading/read-project-online/)
- [Stel project‑startdatum in MS Project met Aspose.Tasks voor Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```