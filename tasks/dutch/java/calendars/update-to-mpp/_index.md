---
date: 2026-08-13
description: Leer hoe u feestdagen aan een kalender kunt toevoegen, de kalender aan
  een project kunt toewijzen en het MS Project‑bestand als MPP opslaat met Aspose.Tasks
  voor Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Kalender bijwerken naar MPP‑formaat in Aspose.Tasks
og_description: Voeg feestdagen toe aan een kalender, wijs deze toe aan een project
  en converteer de planning naar MPP met Aspose.Tasks voor Java. Leer stap‑voor‑stap
  automatisering.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Feestdagen toevoegen aan kalender en opslaan als MPP met Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Feestdagen toevoegen aan kalender en opslaan als MPP met Aspose.Tasks
url: /nl/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feestdagen toevoegen aan agenda en opslaan als MPP met Aspose.Tasks

## Introductie

In modern projectmanagement moet u vaak **feestdagen toevoegen aan agenda**‑bestanden, een **MS Project‑agenda** maken, en vervolgens het schema delen in het native MPP‑formaat. Of u nu tijdlijnen van meerdere bronnen consolideert of legacy‑gegevens migreert, het programmatic genereren van een agenda elimineert handmatige fouten en versnelt de levering. Deze tutorial leidt u door het volledige proces van het maken van een agenda in MS Project, deze aanpassen met feestdagen, **agenda toewijzen aan project**, en uiteindelijk **project converteren naar MPP** met behulp van de Aspose.Tasks Java‑API.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Feestdagen toevoegen aan een agenda, deze toewijzen aan een project, en het resultaat opslaan als een MPP‑bestand met Aspose.Tasks voor Java.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of hoger (JDK 8+).  
- **Kan ik de agenda aanpassen?** Ja – u kunt werktijden, uitzonderingen en feestdagen toevoegen.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisagenda.  

## Wat is “create calendar MS Project”?

Een calendar MS Project maken betekent het definiëren van de werkdagen, uren en uitzonderingen die de taakplanning binnen een Microsoft Project‑bestand aansturen. Met Aspose.Tasks kunt u deze agenda programmatic bouwen, feestdagen instellen, en deze in een project insluiten zonder de MS Project‑UI te openen.

## Waarom Aspose.Tasks gebruiken voor deze taak?

U moet Aspose.Tasks gebruiken omdat het volledige Java‑compatibiliteit biedt, geen Microsoft Office nodig heeft, en u in staat stelt native MPP‑bestanden direct vanuit code te genereren en op te slaan. De bibliotheek ondersteunt alle agenda‑functies, werkt in elke serveromgeving, en verwerkt projecten tot 10.000 taken in minder dan een seconde.

## Vereisten

1. **Java Development Kit (JDK) 8+** – zorg dat `java -version` 1.8 of nieuwer aangeeft.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, of een andere editor naar keuze.  
4. **Basis Java‑kennis** – vertrouwd met klassen, methoden en bestands‑I/O.

## Hoe feestdagen toevoegen aan agenda

Om feestdagen toe te voegen maakt u een nieuw `Calendar`‑object, haalt u de `Exceptions`‑collectie op, en voegt u `DateException`‑items toe voor elke feestdag. `DateException` vertegenwoordigt een enkele niet‑werkdag of een bereik in een agenda. Aspose.Tasks behandelt die data vervolgens als niet‑werkdagen, waardoor taken rond de gedefinieerde feestdagen worden gepland.

### Stap 1: vereiste pakketten importeren

First, bring the Aspose.Tasks classes and Java utilities into scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Stap 2: stel de gegevensdirectory in

Define where your input template and output files will live. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Stap 3: invoer- en uitvoerbestandsnamen definiëren

We’ll load an existing MPP file (or a blank project) and write the result to a new file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Stap 4: laad het project en voeg een nieuwe agenda toe

`Project` class represents an MS Project file in memory and provides access to its calendars, tasks, and resources.

Create a `Project` instance from the source file and add a calendar named **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Stap 5: agenda aanpassen (optioneel)

`Calendar` object defines working days, hours, and exceptions for a project schedule.

If you need specific working times, holidays, or exceptions, call your own helper method. The sample uses `GetTestCalendar` as a placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** U kunt direct `cal1.getWeekDays()` manipuleren om de werktijden voor elke dag van de week in te stellen, of `cal1.getExceptions()` gebruiken om **feestdagen aan agenda toevoegen**.

### Stap 6: wijs de agenda toe aan het project

Tell the project to use the newly created calendar for all its scheduling calculations.

```java
project.set(Prj.CALENDAR, cal1);
```

### Stap 7: sla het project op als MPP

`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating native Microsoft Project format.

Now **convert project to MPP** by saving it with the `SaveFileFormat.Mpp` option.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Stap 8: bevestig succesvolle voltooiing

A simple console message lets you know the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Veelvoorkomende toepassingsgevallen

- **Geautomatiseerde schema‑generatie** voor terugkerende projecten (bijv. wekelijkse sprints).  
- **Legacy CSV‑ of Excel‑agenda's migreren** naar een volledig uitgeruste MS Project‑file.  
- **Server‑side rapportage** waarbij een webservice op aanvraag een MPP‑bestand retourneert.  

## Probleemoplossing & veelvoorkomende valkuilen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| `NullPointerException` on `project.save` | `dataDir` wijst naar een niet‑bestaande map | Zorg ervoor dat de map bestaat of maak deze programmatisch aan. |
| Agenda niet toegepast op taken | Taken verwijzen nog steeds naar de standaardagenda | Na het instellen van `Prj.CALENDAR`, werk ook elke taak’s `Task.CALENDAR` bij als deze eerder is overschreven. |
| Uitvoerbestand is 0 KB | Ontbrekende schrijfrechten | Voer de JVM uit met de juiste bestandsrechten of kies een schrijfbare pad. |

## Veelgestelde vragen

**Q: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?**  
A: Ja, Aspose.Tasks ondersteunt alle Microsoft Project‑bestandsformaten van Project 2007 tot en met Project 2024, meer dan 10 versies.

**Q: Kan ik agenda's aanpassen aan specifieke projectvereisten?**  
A: Absoluut. U kunt werkdagen definiëren, aangepaste werkweken instellen, feestdagen toevoegen, en zelfs meerdere agenda's binnen één projectbestand maken.

**Q: Biedt Aspose.Tasks voor Java ondersteuning voor probleemoplossing en hulp?**  
A: Ja, u kunt hulp krijgen via het Aspose.Tasks community‑forum [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, een volledig functionele gratis proefversie is beschikbaar [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks voor Java?**  
A: Tijdelijke licenties kunnen worden aangevraagd via de Aspose‑website [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-08-13  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Agenda toevoegen aan project met Aspose.Tasks voor Java](/tasks/java/calendars/create/)
- [Hoe weekdagen definiëren in MS Project‑agenda's – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aangepaste agenda‑uitzonderingen maken met Aspose.Tasks voor Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}