---
title: MS-project bijwerken en opnieuw plannen in Aspose.Tasks
linktitle: Project bijwerken en onvoltooid werk opnieuw plannen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u MS Project-bestanden programmatisch kunt bijwerken en opnieuw plannen met Aspose.Tasks voor Java.
weight: 23
url: /nl/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS-project bijwerken en opnieuw plannen in Aspose.Tasks

## Invoering
Microsoft Project is een veelgebruikte projectbeheersoftware waarmee gebruikers taken, bronnen en tijdlijnen efficiënt kunnen beheren. Aspose.Tasks voor Java biedt een krachtige set API's om Microsoft Project-bestanden programmatisch te manipuleren. In deze zelfstudie leren we hoe u MS Project-bestanden kunt bijwerken en onvoltooid werk opnieuw kunt plannen met Aspose.Tasks voor Java.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
3. Basiskennis van de Java-programmeertaal.

## Pakketten importeren
Importeer eerst de benodigde pakketten in uw Java-code:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Stap 1: Stel het project in
Initialiseer een nieuw Project-object en definieer taken daarin, samen met hun duur en afhankelijkheden.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Definieer taken en hun duur
// ...
// Taakafhankelijkheden definiëren
// ...
// Sla de oorspronkelijke projectstatus op
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Stap 2: Projectwerk bijwerken
Werk het projectwerk bij om het tot een bepaalde datum als voltooid te markeren.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Sla het bijgewerkte project op
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Stap 3: Plan onvoltooid werk opnieuw
Plan onvoltooid werk opnieuw zodat het na een bepaalde datum kan beginnen.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Sla het opnieuw geplande project op
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u MS Project-bestanden kunt bijwerken en onvoltooid werk opnieuw kunt plannen met Aspose.Tasks voor Java. Dit kan met name handig zijn in scenario's waarin de projecttijdlijnen moeten worden aangepast op basis van de voortgang of veranderende prioriteiten.

## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks voor Java complexe projectstructuren aan?
A: Ja, Aspose.Tasks voor Java biedt robuuste API's om taken, afhankelijkheden, bronnen en andere projectelementen efficiënt te beheren.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt een gratis proefperiode krijgen van[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 A: U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor eventuele hulp of vragen.
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks voor Java?
 A: Ja, tijdelijke licenties zijn te koop[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik gedetailleerde documentatie vinden voor Aspose.Tasks voor Java?
 A: U kunt de documentatie raadplegen[hier](https://reference.aspose.com/tasks/java/) voor uitgebreide handleidingen en API-referenties.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
