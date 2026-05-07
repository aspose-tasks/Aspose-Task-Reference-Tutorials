---
date: 2026-02-23
description: Leer hoe u de startdatum van het project instelt, de taakduur instelt
  en het project opslaat als MPP met Aspose.Tasks voor Java. Beheer ouder‑ en kindtaken
  efficiënt.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Stel project startdatum in en beheer hoofd‑ en subtaken in Aspose.Tasks
url: /nl/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel project startdatum in en beheer ouder‑ en kindtaken in Aspose.Tasks

## Introduction
Effectieve taakorganisatie is de ruggengraat van succesvol projectmanagement, en **het instellen van de project startdatum** correct is de eerste stap naar een goed gestructureerde planning. In deze tutorial zie je hoe je **de project startdatum instelt**, taakduur configureert en ouder‑kindrelaties beheert met Aspose.Tasks voor Java. Aan het einde ben je klaar om **project op te slaan als MPP**, de voortgang van taken bij te werken en taak‑eigenschappen aan te passen aan elke real‑world situatie.

## Quick Answers
- **Hoe stel ik de project startdatum in?** Gebruik `proj.set(Prj.START_DATE, startDate);` na het initialiseren van het `Project` object.  
- **Kan ik kindtaken toevoegen onder een oudertaak?** Ja – roep `parentTask.getChildren().add("Child Task")` aan.  
- **In welk formaat slaat Aspose.Tasks het bestand op?** Gebruik `SaveFileFormat.Mpp` om **project op te slaan als MPP**.  
- **Hoe werk ik de taakvoortgang bij?** Stel `Tsk.PERCENT_COMPLETE` in op het taakobject.  
- **Waar kan ik een tijdelijke licentie verkrijgen?** Bezoek de tijdelijke‑licentiepagina die in de FAQ’s is gelinkt.

## Prerequisites
Voordat je aan de tutorial begint, zorg ervoor dat je de volgende vereisten hebt:
- Basiskennis van Java-programmeren.  
- Aspose.Tasks for Java bibliotheek geïnstalleerd. Je kunt deze downloaden [hier](https://releases.aspose.com/tasks/java/).  
- Een Java Integrated Development Environment (IDE) geïnstalleerd op je systeem.

## Import Packages
Om te beginnen, importeer je de benodigde pakketten in je Java‑project. Deze pakketten vergemakkelijken een naadloze integratie met de functionaliteiten van Aspose.Tasks voor Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
Begin met het instellen van de startdatum van het project en andere relevante parameters.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Step 2: Add Parent Task (Task 1)
Maak een oudertaak met de naam "Task 1" en configureer de eigenschappen, inclusief **taakduur instellen**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Step 3: Add Parent Task (Task 2) with Child Tasks
Voeg nu een andere oudertaak toe met de naam "Task 2" en voeg kindtaken toe (Task 3 en Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Step 4: Configure Child Tasks
Specificeer startdatums, duur en beperkingen voor Task 3 en Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Step 5: Update Task Completion Percentage
Pas het voltooiingspercentage aan voor Task 3 en Task 4 – zo **werk je de taakvoortgang bij**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Step 6: Save the Project
Sla tenslotte het **project op als MPP** op met de aangebrachte wijzigingen.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Deze stapsgewijze gids laat zien hoe je ouder‑ en kindtaken effectief beheert met Aspose.Tasks voor Java. Experimenteer met verschillende configuraties om aan de eisen van je project te voldoen.

## Why Customize Task Properties?
Het aanpassen van taak‑eigenschappen zoals startdatums, duur, beperkingen en voltooiingspercentages geeft je gedetailleerde controle over het gedrag van de planning. Of je nu taken moet afstemmen op de beschikbaarheid van resources of bedrijfsregels moet afdwingen, Aspose.Tasks stelt je in staat om **taak‑eigenschappen** programmatically aan te passen.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Startdatum niet toegepast** | Zorg ervoor dat je `proj.set(Prj.START_DATE, …)` **na** het aanmaken van het `Project` object en vóór het toevoegen van taken aanroept. |
| **Kindtaken erven verkeerde beperkingen** | Stel elke kind's `ConstraintType` en `ConstraintDate` expliciet in, zoals getoond in Stap 4. |
| **Opgeslagen bestand kan niet worden geopend in MS Project** | Controleer of je de nieuwste Aspose.Tasks versie gebruikt en sla op met `SaveFileFormat.Mpp`. |
| **Percentage wordt niet weergegeven in de UI** | Na het instellen van `Tsk.PERCENT_COMPLETE`, roep `proj.calculateTaskSchedule()` aan als je herberekende datums nodig hebt. |

## FAQs
### Is Aspose.Tasks for Java compatible with different project file formats?
Ja, Aspose.Tasks for Java ondersteunt verschillende projectbestandsformaten, waaronder MPP en XML.

### Can I customize task properties beyond what is covered in this tutorial?
Kun ik taak‑eigenschappen aanpassen buiten wat in deze tutorial wordt behandeld?  
**Antwoord:** Absoluut! Aspose.Tasks for Java biedt uitgebreide aanpassingsopties voor taak‑eigenschappen.

### Is there a community forum for Aspose.Tasks where I can seek support?
Is er een community‑forum voor Aspose.Tasks waar ik ondersteuning kan zoeken?  
**Antwoord:** Ja, je kunt het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) bezoeken voor community‑ondersteuning.

### How can I obtain a temporary license for Aspose.Tasks for Java?
Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks voor Java?  
**Antwoord:** Je kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).

### Where can I find comprehensive documentation for Aspose.Tasks for Java?
Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor Java?  
**Antwoord:** De documentatie is beschikbaar [hier](https://reference.aspose.com/tasks/java/).

**Additional Q&A**

**Q: Hoe verkrijg ik programmatically een tijdelijke licentie?**  
A: Laad het tijdelijke licentiebestand met `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Kan ik de standaard eenheid voor taakduur wijzigen?**  
A: Ja – wijzig het `TimeUnitType` argument in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: Welke versie van Aspose.Tasks is vereist om `SaveFileFormat.Mpp` te gebruiken?**  
A: Alle recente versies (2022‑2026) ondersteunen het opslaan als MPP; controleer de release‑notes voor eventuele breaking changes.

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}