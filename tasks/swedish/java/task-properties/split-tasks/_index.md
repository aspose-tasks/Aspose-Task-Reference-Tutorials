---
title: Dela upp uppgifter i Aspose.Tasks
linktitle: Dela upp uppgifter i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Bemästra uppgiftshantering i Java med Aspose.Tasks! Lär dig hur du delar upp uppgifter effektivt för optimerade projekttidslinjer. Ladda ner nu!
type: docs
weight: 29
url: /sv/java/task-properties/split-tasks/
---
## Introduktion
Kämpar du med uppgiftshantering i ditt Java-projekt? Aspose.Tasks för Java tillhandahåller en kraftfull lösning för att dela upp uppgifter effektivt, vilket förbättrar projektledningskapaciteten. I den här handledningen kommer vi att guida dig genom processen att dela upp uppgifter med Aspose.Tasks för Java, vilket hjälper dig att optimera dina projekttidslinjer och resursallokeringar.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Java Development Kit (JDK) installerat på din maskin.
-  Aspose.Tasks för Java-bibliotek har laddats ner och lagts till i ditt projekt. Du kan ladda ner den från[Aspose.Tasks för Java-dokumentation](https://reference.aspose.com/tasks/java/).
## Importera paket
Börja med att importera de nödvändiga paketen till ditt Java-projekt:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Steg 1: Skapa ett nytt projekt
Börja med att skapa ett nytt projekt med Aspose.Tasks-biblioteket:
```java
// Skapa ett nytt projekt
Project splitTaskProject = new Project();
```
## Steg 2: Ställ in projektkalender
Ställ in projektets kalenderinställningar för att fastställa tidslinjen:
```java
// Skaffa en standardkalender
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Ställ in projektets kalenderinställningar
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (fortsätt med exemplet)
```
## Steg 3: Lägg till en rotuppgift
Lägg till en rotuppgift till ditt projekt:
```java
// Rotuppgift
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Steg 4: Lägg till en ny uppgift till Split
Lägg till en ny uppgift till ditt projekt som du vill dela upp:
```java
// Lägg till en ny uppgift
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Steg 5: Skapa en resurstilldelning
Skapa en ny resurstilldelning för uppgiften:
```java
// Skapa en ny resurstilldelning
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Steg 6: Generera tidsfasdata
Generera tidsfasdata för resurstilldelning:
```java
// Generera resurstilldelning tidsfasad data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Steg 7: Dela upp uppgiften
Dela upp uppgiften i flera delar:
```java
// Dela upp uppgiften i 3 delar
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (fortsätt med exemplet)
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du delar upp uppgifter med Aspose.Tasks för Java. Detta kraftfulla bibliotek förenklar uppgiftshanteringen i Java-projekt och ger effektiva lösningar för att optimera projekttidslinjer och resursallokering.
## Vanliga frågor
### Kan jag dela upp uppgifter med olika längd?
Ja, du kan anpassa varaktigheten av uppgifterna enligt dina projektkrav.
### Är Aspose.Tasks för Java kompatibelt med alla Java-versioner?
Aspose.Tasks för Java är utformad för att fungera sömlöst med olika Java-versioner, vilket säkerställer kompatibilitet.
### Kan jag använda Aspose.Tasks för Java gratis?
Aspose.Tasks för Java erbjuder en gratis provperiod, så att du kan utforska dess funktioner innan du gör ett köp.
### Hur kan jag få support för Aspose.Tasks för Java?
 Besök[Aspose.Tasks för Java supportforum](https://forum.aspose.com/c/tasks/15) för att få hjälp och få kontakt med samhället.
### Behöver jag en tillfällig licens för Aspose.Tasks för Java?
 Du kan få en tillfällig licens från[den här länken](https://purchase.aspose.com/temporary-license/) för test- och utvärderingsändamål.