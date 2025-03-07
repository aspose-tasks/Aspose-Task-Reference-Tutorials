---
title: Update taakgegevens naar MPP-indeling in Aspose.Tasks
linktitle: Update taakgegevens naar MPP-indeling in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u taakgegevens kunt bijwerken naar MPP-indeling met behulp van Aspose.Tasks voor Java. Volg onze stap-voor-stap handleiding voor efficiënt projectmanagement.
weight: 35
url: /nl/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Update taakgegevens naar MPP-indeling in Aspose.Tasks

## Invoering
Welkom bij onze stapsgewijze handleiding voor het bijwerken van taakgegevens naar MPP-indeling met behulp van Aspose.Tasks voor Java. In deze zelfstudie leiden we u door het proces, zodat u elke stap duidelijk begrijpt. Aspose.Tasks voor Java biedt een robuuste oplossing voor het werken met Microsoft Project-bestanden, en aan het einde van deze handleiding kunt u taakgegevens efficiënt bijwerken in MPP-indeling.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
-  Aspose.Tasks voor Java: Zorg ervoor dat de bibliotheek Aspose.Tasks is geïnstalleerd. Je kunt het downloaden van de[pagina vrijgeven](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd.
- Integrated Development Environment (IDE): Gebruik een IDE naar keuze voor Java-ontwikkeling.
## Pakketten importeren
Begin met het importeren van de benodigde pakketten in uw Java-project. Het volgende fragment laat zien hoe u pakketten importeert:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Maak en configureer de initiële taak
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Ga verder met de rest van de code)
```
## 2. Stel de startdatum en -duur in
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Ga verder met de rest van de code)
```
## 3. Maak een samenvattingstaak
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Ga verder met de rest van de code)
```
## 4. Stel de deadline en taaknotities in
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Ga verder met de rest van de code)
```
## 5. Configureer taakbeperkingen
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Ga verder met de rest van de code)
```
## 6. Maak aanvullende taken
```java
//Creëer 10 nieuwe taken
for (int i = 0; i < 10; i++) {
    //... (Ga verder met de rest van de code)
}
//... (Ga verder met de rest van de code)
```
## 7. Sla het project op
```java
// Sla het project op
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Door deze stappen te volgen, hebt u de taakgegevens met succes bijgewerkt naar de MPP-indeling met behulp van Aspose.Tasks voor Java.
## Conclusie
Gefeliciteerd! U hebt een uitgebreide handleiding voltooid over het bijwerken van taakgegevens in MPP-indeling met behulp van Aspose.Tasks voor Java. Deze krachtige bibliotheek vereenvoudigt projectbeheertaken, waardoor het een waardevol hulpmiddel is voor Java-ontwikkelaars.
## Veelgestelde vragen
### Vraag: Waar kan ik de Aspose.Tasks voor Java-documentatie vinden?
 A: De documentatie is beschikbaar[hier](https://reference.aspose.com/tasks/java/).
### Vraag: Hoe kan ik Aspose.Tasks voor Java downloaden?
 A: U kunt het downloaden van de[pagina vrijgeven](https://releases.aspose.com/tasks/java/).
### Vraag: Is er een gratis proefversie beschikbaar?
 A: Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 A: Bezoek het ondersteuningsforum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Bieden jullie tijdelijke licenties aan voor testdoeleinden?
 A: Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
