---
title: WBS associerad med uppgift i Aspose.Tasks
linktitle: WBS associerad med uppgift i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Bemästra WBS med Aspose.Tasks för Java - Lär dig att läsa och numrera om uppgifts WBS-koder. Öka effektiviteten i projektledningen!
weight: 36
url: /sv/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS associerad med uppgift i Aspose.Tasks

## Introduktion
Välkommen till en värld av projektledning med Aspose.Tasks för Java! I den här handledningen kommer vi att fördjupa oss i krångligheterna i Work Breakdown Structure (WBS) som är förknippade med uppgifter som använder Aspose.Tasks för Java. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här guiden dig att navigera genom det väsentliga för att hantera WBS-koder effektivt.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Java Development Kit (JDK) installerat på din maskin.
-  Aspose.Tasks för Java-bibliotek har laddats ner och lagts till i ditt projekt. Du kan få det från[här](https://releases.aspose.com/tasks/java/).
## Importera paket
Se till att du importerar de nödvändiga paketen för att kickstarta ditt projekt:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Läs WBS-koder
Låt oss börja med att läsa WBS-koder förknippade med uppgifter. Följ dessa steg:
## Steg 1: Ladda projektet
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Steg 2: Samla uppgifter
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Steg 3: Analysera och anpassa
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Det här utdraget läser och anpassar WBS-koder som är kopplade till uppgifter i ditt projekt.
## Omnumrera uppgift WBS-koder
Låt oss nu utforska omnumrering av WBS-koder för uppgifter:
## Steg 1: Ladda projektet
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Steg 2: Välj Alla uppgifter
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Steg 3: Mata ut initiala WBS-koder
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Steg 4: Numrera om WBS-koder
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Steg 5: Mata ut uppdaterade WBS-koder
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Genom att följa dessa steg kommer du effektivt att numrera om WBS-koder för uppgifter i ditt projekt.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man arbetar med WBS-koder med Aspose.Tasks för Java. Denna kunskap ger dig möjlighet att effektivt hantera och anpassa ditt projekts uppgiftshierarki.
## Vanliga frågor
### F: Var kan jag hitta dokumentationen för Aspose.Tasks för Java?
 S: Dokumentationen finns tillgänglig[här](https://reference.aspose.com/tasks/java/).
### F: Hur kan jag ladda ner Aspose.Tasks för Java?
 S: Du kan ladda ner den[här](https://releases.aspose.com/tasks/java/).
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan få en gratis provperiod[här](https://releases.aspose.com/).
### F: Var kan jag få support för Aspose.Tasks för Java?
 A: Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för support.
### F: Kan jag få en tillfällig licens för Aspose.Tasks för Java?
 S: Ja, skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
