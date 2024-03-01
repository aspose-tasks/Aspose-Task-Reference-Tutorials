---
title: Behandel de eigenschappen van de nivelleringsvertraging in Aspose.Tasks
linktitle: Behandel de eigenschappen van de nivelleringsvertraging voor resourcetoewijzingen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer met deze uitgebreide tutorial hoe u omgaat met de eigenschappen van nivelleringsvertraging voor resourcetoewijzingen in Aspose.Tasks voor Java.
type: docs
weight: 17
url: /nl/java/resource-assignments/leveling-delay-properties/
---
## Invoering
In deze zelfstudie doorlopen we het proces van het afhandelen van eigenschappen van nivelleringsvertraging voor resourcetoewijzingen in Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java-bibliotheek waarmee u met Microsoft Project-bestanden kunt werken zonder dat Microsoft Project op uw systeem hoeft te worden geïnstalleerd.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Java Development Kit (JDK): Zorg ervoor dat Java JDK op uw systeem is geïnstalleerd. Je kunt het downloaden en installeren vanaf de[website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks voor Java-bibliotheek: Download de Aspose.Tasks voor Java-bibliotheek van de[downloadpagina](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Importeer eerst de benodigde pakketten in uw Java-project om de Aspose.Tasks-functionaliteiten te gebruiken:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Stap 1: Maak een projectobject
 Instantieer een`Project` voorwerp:
```java
Project prj = new Project();
```
## Stap 2: Maak een taak
Voeg een taak toe aan het project:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Stap 3: Stel de startdatum en -duur van de taak in
Stel de startdatum en duur van de taak in:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Stap 4: Voeg een bron toe
Voeg een resource toe aan het project:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Stap 5: Maak een resourcetoewijzing
Maak een resourcetoewijzing voor de taak en resource:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Stap 6: Stel de nivelleringsvertraging in
Stel de nivelleringsvertraging voor de toewijzing in:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Stap 7: Resultaten weergeven
Druk de nivelleringsvertraging en andere relevante informatie af:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe we moeten omgaan met de eigenschappen van nivelleringsvertraging voor resourcetoewijzingen in Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u de resourcetoewijzingen in uw Java-projecten efficiënt beheren.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks gebruiken met andere Java-bibliotheken?

A: Ja, Aspose.Tasks kan worden geïntegreerd met andere Java-bibliotheken om de mogelijkheden voor projectbeheer te verbeteren.

### Vraag: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project-bestanden?

A: Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project-bestanden, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.

### Vraag: Waar kan ik aanvullende ondersteuning vinden voor Aspose.Tasks?

 A: U kunt ondersteuning en hulpmiddelen vinden op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).

### Vraag: Kan ik Aspose.Tasks uitproberen voordat ik een aankoop doe?

 A: Ja, u kunt een gratis proefversie van Aspose.Tasks verkrijgen via de[releases pagina](https://releases.aspose.com/).

### Vraag: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?

 A: U kunt een tijdelijke licentie aanvragen bij de[tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.