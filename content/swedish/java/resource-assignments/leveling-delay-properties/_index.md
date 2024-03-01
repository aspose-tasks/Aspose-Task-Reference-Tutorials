---
title: Hantera egenskaper för nivåfördröjning i Aspose.Tasks
linktitle: Hantera egenskaper för utjämningsfördröjning för resurstilldelningar i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hanterar utjämningsfördröjningsegenskaper för resurstilldelningar i Aspose.Tasks för Java med denna omfattande handledning.
type: docs
weight: 17
url: /sv/java/resource-assignments/leveling-delay-properties/
---
## Introduktion
I den här handledningen går vi igenom processen att hantera egenskaper för utjämningsfördröjning för resurstilldelningar i Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt Java-bibliotek som låter dig arbeta med Microsoft Project-filer utan att Microsoft Project behöver installeras på ditt system.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Java Development Kit (JDK): Se till att du har Java JDK installerat på ditt system. Du kan ladda ner och installera den från[hemsida](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Ladda ner Aspose.Tasks for Java-biblioteket från[nedladdningssida](https://releases.aspose.com/tasks/java/).

## Importera paket
Importera först de nödvändiga paketen till ditt Java-projekt för att använda Aspose.Tasks-funktioner:
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

## Steg 1: Skapa ett projektobjekt
 Instantiera en`Project` objekt:
```java
Project prj = new Project();
```
## Steg 2: Skapa en uppgift
Lägg till en uppgift till projektet:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Steg 3: Ställ in uppgiftens startdatum och varaktighet
Ställ in startdatum och varaktighet för uppgiften:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Steg 4: Lägg till en resurs
Lägg till en resurs till projektet:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Steg 5: Skapa en resurstilldelning
Skapa en resurstilldelning för uppgiften och resursen:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Steg 6: Ställ in utjämningsfördröjning
Ställ in utjämningsfördröjningen för uppdraget:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Steg 7: Visa resultat
Skriv ut nivelleringsfördröjningen och annan relevant information:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Slutsats
I den här handledningen har vi lärt oss hur man hanterar egenskaper för utjämningsfördröjning för resurstilldelningar i Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt hantera resurstilldelningar i dina Java-projekt.
## FAQ's
### F: Kan jag använda Aspose.Tasks med andra Java-bibliotek?

S: Ja, Aspose.Tasks kan integreras med andra Java-bibliotek för att förbättra projekthanteringsmöjligheterna.

### F: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project-filer?

S: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project-filer, vilket säkerställer kompatibilitet mellan olika miljöer.

### F: Var kan jag hitta ytterligare stöd för Aspose.Tasks?

 S: Du kan hitta support och resurser på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### F: Kan jag prova Aspose.Tasks innan jag köper?

 S: Ja, du kan få en gratis provversion av Aspose.Tasks från[släpper sida](https://releases.aspose.com/).

### F: Hur kan jag få en tillfällig licens för Aspose.Tasks?

 S: Du kan begära en tillfällig licens från[sida för tillfällig licens](https://purchase.aspose.com/temporary-license/) i utvärderingssyfte.