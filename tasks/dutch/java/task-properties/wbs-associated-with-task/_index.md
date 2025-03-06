---
title: WBS gekoppeld aan taak in Aspose.Tasks
linktitle: WBS gekoppeld aan taak in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Beheers WBS met Aspose.Tasks voor Java - Leer taak-WBS-codes lezen en opnieuw nummeren. Verhoog de efficiëntie van projectmanagement!
weight: 36
url: /nl/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS gekoppeld aan taak in Aspose.Tasks

## Invoering
Welkom in de wereld van projectmanagement met Aspose.Tasks voor Java! In deze zelfstudie verdiepen we ons in de fijne kneepjes van de Work Breakdown Structure (WBS) die verband houden met taken die Aspose.Tasks voor Java gebruiken. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze handleiding helpt u bij het navigeren door de essentie van het efficiënt beheren van WBS-codes.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw computer geïnstalleerd.
-  Aspose.Tasks voor de Java-bibliotheek gedownload en toegevoegd aan uw project. Je kunt het krijgen van[hier](https://releases.aspose.com/tasks/java/).
## Pakketten importeren
Zorg ervoor dat u de benodigde pakketten importeert om uw project een kickstart te geven:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## WBS-codes lezen
Laten we beginnen met het lezen van WBS-codes die aan taken zijn gekoppeld. Volg deze stappen:
## Stap 1: Laad het project
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Stap 2: Verzamel taken
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Stap 3: Parseren en aanpassen
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Dit fragment leest WBS-codes die zijn gekoppeld aan taken in uw project en past deze aan.
## Hernummer taak-WBS-codes
Laten we nu eens kijken naar het hernummeren van WBS-codes voor taken:
## Stap 1: Laad het project
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Stap 2: Selecteer Alle taken
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Stap 3: Voer initiële WBS-codes uit
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Stap 4: WBS-codes opnieuw nummeren
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Stap 5: Voer bijgewerkte WBS-codes uit
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Door deze stappen te volgen, hernummert u effectief WBS-codes voor taken in uw project.
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u met WBS-codes kunt werken met behulp van Aspose.Tasks voor Java. Deze kennis stelt u in staat de takenhiërarchie van uw project efficiënt te beheren en aan te passen.
## Veelgestelde vragen
### Vraag: Waar kan ik de documentatie voor Aspose.Tasks voor Java vinden?
 A: De documentatie is beschikbaar[hier](https://reference.aspose.com/tasks/java/).
### Vraag: Hoe kan ik Aspose.Tasks voor Java downloaden?
 Antwoord: Je kunt het downloaden[hier](https://releases.aspose.com/tasks/java/).
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 A: Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) Voor ondersteuning.
### Vraag: Kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks voor Java?
 A: Ja, vraag een tijdelijke licentie aan[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
