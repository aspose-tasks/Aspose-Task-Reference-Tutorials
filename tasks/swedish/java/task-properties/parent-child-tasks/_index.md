---
title: Hantera föräldra- och barnuppgifter i Aspose.Tasks
linktitle: Hantera föräldra- och barnuppgifter i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Förbättra projektledningseffektiviteten med Aspose.Tasks för Java. Lär dig att hantera föräldra- och barnuppgifter steg för steg. Börja nu!
weight: 24
url: /sv/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera föräldra- och barnuppgifter i Aspose.Tasks

## Introduktion
Inom projektledningssfären är effektiv uppgiftsorganisation avgörande. Aspose.Tasks för Java tillhandahåller en robust lösning för att effektivt hantera föräldra- och barnuppgifter. I den här handledningen guidar vi dig genom processen att använda Aspose.Tasks för Java för att effektivisera dina projektuppgifter.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för Java-programmering.
-  Aspose.Tasks för Java-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/tasks/java/).
- En Java Integrated Development Environment (IDE) installerad på ditt system.
## Importera paket
För att börja, importera de nödvändiga paketen till ditt Java-projekt. Dessa paket underlättar sömlös integration med Aspose.Tasks för Java-funktioner.
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
## Steg 1: Ställ in projektstartdatum
Börja med att ställa in projektets startdatum och andra relevanta parametrar.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Ytterligare kod för paketimport kan läggas till här
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Steg 2: Lägg till föräldrauppgift (uppgift 1)
Skapa en överordnad uppgift med namnet "Task 1" och konfigurera dess egenskaper.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Steg 3: Lägg till föräldrauppgift (uppgift 2) med barnuppgifter
Lägg nu till en annan överordnad uppgift som heter "Uppgift 2" och inkludera underordnade uppgifter (Uppgift 3 och Uppgift 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Lägg till underordnade uppgifter till uppgift 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Ytterligare konfiguration för uppgift 3 och uppgift 4 kan läggas till här
```
## Steg 4: Konfigurera underordnade uppgifter
Ange startdatum, varaktigheter och begränsningar för uppgift 3 och uppgift 4.
```java
// Konfigurera uppgift 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Konfigurera uppgift 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Steg 5: Uppdatera procentsats för slutförande av uppgifter
Justera slutförandeprocenten för uppgift 3 och uppgift 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Steg 6: Spara projektet
Slutligen, spara projektet med de tillämpade ändringarna.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Denna steg-för-steg-guide visar hur man hanterar föräldra- och barnuppgifter effektivt med Aspose.Tasks för Java. Experimentera med olika konfigurationer för att passa ditt projekts krav.
## Slutsats
Sammanfattningsvis ger Aspose.Tasks för Java utvecklare möjlighet att effektivt hantera projektuppgifter, vilket säkerställer sömlös organisation och spårning. Implementera de beskrivna stegen för att förbättra din projektledningskapacitet.
## Vanliga frågor
### Är Aspose.Tasks för Java kompatibelt med olika projektfilformat?
Ja, Aspose.Tasks för Java stöder olika projektfilformat, inklusive MPP och XML.
### Kan jag anpassa uppgiftsegenskaper utöver vad som tas upp i denna handledning?
Absolut! Aspose.Tasks för Java tillhandahåller omfattande anpassningsalternativ för uppgiftsegenskaper.
### Finns det ett communityforum för Aspose.Tasks där jag kan söka stöd?
 Ja, du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd.
### Hur kan jag få en tillfällig licens för Aspose.Tasks för Java?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta omfattande dokumentation för Aspose.Tasks för Java?
 Dokumentationen finns tillgänglig[här](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
