---
date: 2026-08-03
description: Leer hoe je een ms project calendar maakt, een calendar toevoegt aan
  een project, en het project opslaat als XML met Aspose.Tasks for Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Calendar toevoegen aan project met Aspose.Tasks
og_description: Maak ms project calendar programmatisch met Aspose.Tasks for Java.
  Voeg calendars toe, pas schedules aan, en exporteer naar XML in enkele minuten.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Maak ms project calendar met Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Maak ms project calendar met Aspose.Tasks for Java
url: /nl/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak ms project kalender met Aspose.Tasks voor Java

## Inleiding
In moderne project‑managementworkflows kan de mogelijkheid om **ms project kalender** programmatisch te maken uren handmatig bewerken besparen. Aspose.Tasks for Java biedt u een schone, type‑veilige API om Microsoft Project‑bestanden te manipuleren zonder ooit de desktopclient te openen. In deze tutorial leert u hoe u een kalender toevoegt, hoe u een MS Project‑kalender maakt, en hoe u het project opslaat als XML — allemaal met slechts een paar regels Java‑code.

## Snelle antwoorden
- **Wat betekent “create ms project calendar”?**  
  Het betekent het invoegen van een nieuwe werktijddefinitie (kalender) in een Microsoft Project‑bestand via code.  
- **Welke bibliotheek behandelt dit?**  
  Aspose.Tasks for Java levert de `Calendar`‑klasse en de `Project`‑container om kalenders te beheren.  
- **Heb ik een licentie nodig?**  
  Een tijdelijke evaluatielicentie werkt voor testen; een volledige licentie is vereist voor productiegebruik.  
- **Kan ik het bestand opslaan als XML?**  
  Ja — gebruik `SaveFileFormat.Xml` om het project te exporteren als een XML‑bestand.  
- **Wat zijn de vereisten?**  
  Java JDK 8+ en de Aspose.Tasks for Java‑JAR op uw classpath.

## Wat is create ms project calendar?
Het maken van een MS Project‑kalender betekent dat u programmatisch een nieuwe kalenderdefinitie toevoegt aan een Project‑bestand, waarbij u werkdagen, uitzonderingen en dagelijkse werktijden opgeeft, en vervolgens die kalender toewijst aan taken, resources of het gehele project zodat planningsberekeningen rekening houden met de gedefinieerde werktijd.

## Waarom Aspose.Tasks for Java gebruiken om een kalender aan een project toe te voegen?
U moet Aspose.Tasks for Java gebruiken omdat het een volledig type‑veilige API biedt die werkt zonder Microsoft Project geïnstalleerd, alle belangrijke Project‑versies ondersteunt (2007‑2021, meer dan 5 releases), en kan exporteren naar XML, MPP en **10+** andere formaten, waardoor geautomatiseerde bulk‑kalendercreatie op elke server mogelijk is.

## Vereisten
- **Java Development Kit (JDK) 8 of nieuwer** geïnstalleerd en geconfigureerd.  
- **Aspose.Tasks for Java** bibliotheek – download van de [official website](https://releases.aspose.com/tasks/java/) en voeg de JAR toe aan de classpath van uw project.  
- Een IDE of build‑tool (Maven/Gradle) naar keuze.

## Stapsgewijze handleiding

### Stap 1: importeer het vereiste Aspose.Tasks‑pakket
Breng eerst de Aspose.Tasks‑klassen in scope zodat u met projecten en kalenders kunt werken.

```java
import com.aspose.tasks.*;
```

### Stap 2: stel het gegevensdirectorypad in
Definieer waar het gegenereerde projectbestand wordt weggeschreven. Vervang de tijdelijke aanduiding door een absoluut of relatief pad op uw machine.

```java
String dataDir = "Your Data Directory";
```

### Stap 3: maak een nieuw Project‑object aan
`Project` is de kernklasse die een Microsoft Project‑bestand in het geheugen vertegenwoordigt.

```java
Project prj = new Project();
```

### Stap 4: definieer de kalenders die u wilt toevoegen
`Calendar` definieert een planning met werkdagen, uitzonderingen en werktijden voor een project.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** Na het toevoegen van een kalender kunt u de werkdagen aanpassen met `cal1.getWeekDays().add(...)` en de dagelijkse werktijden instellen met `cal1.getBaseCalendar().setWorkingTime(...)`.

### Stap 5: sla het project op (sla project op als XML)
`SaveFileFormat.Xml` vertelt Aspose.Tasks om het project in XML‑formaat te schrijven.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Stap 6: toon een voltooiingsbericht
Laat de gebruiker weten dat de bewerking succesvol is voltooid.

```java
System.out.println("Process completed Successfully");
```

Door deze zes beknopte stappen te volgen, heeft u met succes **een kalender aan een project toegevoegd** en het resultaat opgeslagen als een XML‑bestand.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`NullPointerException` on `prj.getCalendars()`** | Projectobject niet correct geïnitialiseerd. | Zorg ervoor dat `new Project()` wordt aangeroepen voordat u kalenders benadert. |
| **File not found when saving** | `dataDir` wijst naar een niet‑bestaande map. | Maak de map eerst aan of gebruik een absoluut pad. |
| **Calendar name appears as “no info”** | Plaatsvervangende namen werden in het voorbeeld gebruikt. | Vervang door betekenisvolle namen die het schema weerspiegelen (bijv. “US Holiday Calendar”). |
| **Saved XML cannot be opened in MS Project** | Gebruik van een verouderde Aspose.Tasks‑versie. | Werk bij naar de nieuwste Aspose.Tasks for Java‑release. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks complexe kalenders met meerdere uitzonderingen verwerken?**  
A: Ja – na het toevoegen van een kalender kunt u uitzonderingen, werktijden en niet‑werkdagen definiëren met de `WeekDay`‑ en `Exception`‑klassen.

**Q: Is het mogelijk om de nieuwe kalender toe te wijzen aan specifieke taken?**  
A: Absoluut. Haal een taak op via `prj.getRootTask().getChildren().add("Task Name")` en stel `task.set(Tsk.CALENDAR, cal3);` in.

**Q: Ondersteunt de bibliotheek het opslaan in andere formaten zoals MPP?**  
A: Ja. Vervang `SaveFileFormat.Xml` door `SaveFileFormat.Mpp` of `SaveFileFormat.P6` indien nodig; Aspose.Tasks ondersteunt **12** uitvoerformaten.

**Q: Heb ik een licentie nodig voor ontwikkel‑builds?**  
A: Een tijdelijke evaluatielicentie is voldoende voor testen; een volledige licentie is vereist voor productie‑implementaties.

**Q: Waar kan ik hulp krijgen als ik tegen problemen aanloop?**  
A: Het Aspose.Tasks‑communityforum is een uitstekende bron: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2026-08-03  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe weekdagen te definiëren in MS Project‑kalenders – Aspose.Tasks Java](/tasks/java/calendars/)
- [Hoe projectkalender in Java in te stellen met Aspose.Tasks](/tasks/java/calendars/properties/)
- [Aangepaste kalenderexcepties maken met Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}