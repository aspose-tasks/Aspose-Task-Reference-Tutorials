---
title: Uppdatera uppgiftsdata till MPP-format i Aspose.Tasks
linktitle: Uppdatera uppgiftsdata till MPP-format i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du uppdaterar uppgiftsdata till MPP-format med Aspose.Tasks för Java. Följ vår steg-för-steg-guide för effektiv projektledning.
weight: 35
url: /sv/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uppdatera uppgiftsdata till MPP-format i Aspose.Tasks

## Introduktion
Välkommen till vår steg-för-steg-guide för att uppdatera uppgiftsdata till MPP-format med Aspose.Tasks för Java. I den här handledningen går vi igenom processen och ser till att du förstår varje steg med tydlighet. Aspose.Tasks för Java tillhandahåller en robust lösning för att arbeta med Microsoft Project-filer, och i slutet av den här guiden kommer du att kunna uppdatera uppgiftsdata effektivt i MPP-format.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Tasks för Java: Se till att du har Aspose.Tasks-biblioteket installerat. Du kan ladda ner den från[släpp sida](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Se till att du har Java installerat på ditt system.
- Integrated Development Environment (IDE): Använd en IDE som du väljer för Java-utveckling.
## Importera paket
Börja med att importera de nödvändiga paketen till ditt Java-projekt. Följande utdrag visar hur man importerar paket:
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
## 1. Skapa och konfigurera den initiala uppgiften
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Fortsätt med resten av koden)
```
## 2. Ställ in startdatum och varaktighet
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Fortsätt med resten av koden)
```
## 3. Skapa en sammanfattningsuppgift
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Fortsätt med resten av koden)
```
## 4. Ställ in deadline och uppgiftsanteckningar
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Fortsätt med resten av koden)
```
## 5. Konfigurera uppgiftsbegränsningar
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Fortsätt med resten av koden)
```
## 6. Skapa ytterligare uppgifter
```java
//Skapa 10 nya uppgifter
for (int i = 0; i < 10; i++) {
    //... (Fortsätt med resten av koden)
}
//... (Fortsätt med resten av koden)
```
## 7. Spara projektet
```java
// Spara projektet
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Genom att följa dessa steg har du framgångsrikt uppdaterat uppgiftsdata till MPP-format med Aspose.Tasks för Java.
## Slutsats
Grattis! Du har slutfört en omfattande guide om uppdatering av uppgiftsdata i MPP-format med Aspose.Tasks för Java. Detta kraftfulla bibliotek förenklar projekthanteringsuppgifter, vilket gör det till ett värdefullt verktyg för Java-utvecklare.
## Vanliga frågor
### F: Var kan jag hitta Aspose.Tasks för Java-dokumentationen?
 S: Dokumentationen finns tillgänglig[här](https://reference.aspose.com/tasks/java/).
### F: Hur kan jag ladda ner Aspose.Tasks för Java?
 S: Du kan ladda ner det från[släpp sida](https://releases.aspose.com/tasks/java/).
### F: Finns det en gratis provperiod?
 S: Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).
### F: Var kan jag få support för Aspose.Tasks för Java?
 S: Besök supportforumet[här](https://forum.aspose.com/c/tasks/15).
### F: Erbjuder ni tillfälliga licenser för teständamål?
 S: Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
