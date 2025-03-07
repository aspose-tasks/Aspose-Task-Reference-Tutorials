---
title: Beheer ouder- en kindtaken in Aspose.Tasks
linktitle: Beheer ouder- en kindtaken in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Verbeter de efficiëntie van projectbeheer met Aspose.Tasks voor Java. Leer stap voor stap hoe u ouder- en kindtaken kunt beheren. Begin nu!
weight: 24
url: /nl/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheer ouder- en kindtaken in Aspose.Tasks

## Invoering
Op het gebied van projectmanagement is een effectieve taakorganisatie cruciaal. Aspose.Tasks voor Java biedt een robuuste oplossing voor het efficiënt beheren van bovenliggende en onderliggende taken. In deze zelfstudie begeleiden we u bij het gebruik van Aspose.Tasks voor Java om uw projecttaken te stroomlijnen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van Java-programmeren.
-  Aspose.Tasks voor Java-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/java/).
- Een Java Integrated Development Environment (IDE) die op uw systeem is geïnstalleerd.
## Pakketten importeren
Importeer om te beginnen de benodigde pakketten in uw Java-project. Deze pakketten faciliteren een naadloze integratie met Aspose.Tasks voor Java-functionaliteiten.
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
## Stap 1: Stel de startdatum van het project in
Begin met het instellen van de startdatum van het project en andere relevante parameters.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Extra code voor pakketimport kan hier worden toegevoegd
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Stap 2: Bovenliggende taak toevoegen (taak 1)
Maak een bovenliggende taak met de naam "Taak 1" en configureer de eigenschappen ervan.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Stap 3: Voeg oudertaak (taak 2) toe met onderliggende taken
Voeg nu nog een bovenliggende taak toe met de naam "Taak 2" en voeg onderliggende taken toe (Taak 3 en Taak 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Voeg onderliggende taken toe aan taak 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Aanvullende configuratie voor taak 3 en taak 4 kan hier worden toegevoegd
```
## Stap 4: Onderliggende taken configureren
Geef startdata, duur en beperkingen op voor taak 3 en taak 4.
```java
// Configureer taak 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configureer taak 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Stap 5: Update taakvoltooiingspercentage
Pas het voltooiingspercentage voor taak 3 en taak 4 aan.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Stap 6: Sla het project op
Sla ten slotte het project op met de aangebrachte wijzigingen.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Deze stapsgewijze handleiding laat zien hoe u bovenliggende en onderliggende taken effectief kunt beheren met Aspose.Tasks voor Java. Experimenteer met verschillende configuraties om aan de vereisten van uw project te voldoen.
## Conclusie
Concluderend stelt Aspose.Tasks voor Java ontwikkelaars in staat om projecttaken efficiënt af te handelen, waardoor een naadloze organisatie en tracking wordt gegarandeerd. Implementeer de geschetste stappen om uw projectmanagementmogelijkheden te verbeteren.
## Veelgestelde vragen
### Is Aspose.Tasks voor Java compatibel met verschillende projectbestandsformaten?
Ja, Aspose.Tasks voor Java ondersteunt verschillende projectbestandsindelingen, waaronder MPP en XML.
### Kan ik taakeigenschappen aanpassen die verder gaan dan wat in deze zelfstudie wordt behandeld?
Absoluut! Aspose.Tasks voor Java biedt uitgebreide aanpassingsmogelijkheden voor taakeigenschappen.
### Is er een communityforum voor Aspose.Tasks waar ik ondersteuning kan zoeken?
 Ja, u kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapssteun.
### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks voor Java?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor Java?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
