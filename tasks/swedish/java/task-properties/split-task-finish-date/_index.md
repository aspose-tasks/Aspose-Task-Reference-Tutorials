---
title: Dela uppgift Slutdatum i Aspose.Tasks
linktitle: Dela uppgift Slutdatum i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du enkelt delar upp uppgifternas slutdatum med Aspose.Tasks för Java. Förbättra projektledning med exakta tidslinjer.
weight: 28
url: /sv/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dela uppgift Slutdatum i Aspose.Tasks

## Introduktion
Inom projektledning är förståelse av uppgiftens tidslinjer avgörande för framgångsrikt projektslut. Aspose.Tasks för Java tillhandahåller kraftfulla funktioner för att manipulera projektuppgifter effektivt. I den här handledningen kommer vi att fördjupa oss i att dela upp uppgiftens slutdatum med Aspose.Tasks, vilket hjälper dig att hantera projekttidslinjer effektivt.
## Förutsättningar
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i Java-programmering.
-  Aspose.Tasks för Java-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/tasks/java/).
- En Java-utvecklingsmiljö inrättad.
## Importera paket
Börja med att inkludera nödvändiga paket i ditt Java-projekt:
```java
import com.aspose.tasks.*;
```
## Steg 1: Hitta en delad uppgift
Leta upp uppgiften du vill dela upp inom projektet:
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Läs projektet
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Steg 2: Hitta projektkalendern
Hämta projektkalendern för korrekta datumberäkningar:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Steg 3: Beräkna uppgiftens slutdatum med olika varaktigheter
Beräkna nu uppgiftens slutdatum för olika varaktigheter:
## Steg 3.1: Längd på 8 timmar
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Upprepa ovanstående kod för olika varaktigheter, justera timmarna därefter.
## Slutsats
Att bemästra konsten att manipulera uppgiftens slutdatum är avgörande för effektiv projektledning. Aspose.Tasks för Java förenklar denna process, vilket gör att du enkelt kan effektivisera dina projekttidslinjer.
## Vanliga frågor
### F1: Hur kan jag ladda ner Aspose.Tasks för Java?
 A1: Du kan ladda ner den[här](https://releases.aspose.com/tasks/java/).
### F2: Var kan jag hitta dokumentation för Aspose.Tasks?
 S2: Se dokumentationen[här](https://reference.aspose.com/tasks/java/).
### F3: Hur får jag en tillfällig licens för Aspose.Tasks?
 A3: Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### F4: Var kan jag söka support för Aspose.Tasks?
 S4: Besök supportforumet[här](https://forum.aspose.com/c/tasks/15).
### F5: Kan jag köpa Aspose.Tasks?
 A5: Ja, du kan köpa det[här](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
