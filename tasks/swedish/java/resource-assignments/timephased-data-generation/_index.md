---
title: Generera tidsfasdata i Aspose.Tasks
linktitle: Generera tidsfasdata för resurstilldelningar i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du genererar tidsfasdata för resurstilldelningar med Aspose.Tasks för Java. Förbättra projektledningseffektiviteten med denna omfattande guide.
weight: 24
url: /sv/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera tidsfasdata i Aspose.Tasks

## Introduktion
I den här handledningen går vi igenom processen att generera tidsfasdata för resurstilldelningar med Aspose.Tasks för Java. Tidsfasad data ger värdefulla insikter om hur resurser allokeras över tid inom ett projekt, vilket hjälper projektledare att fatta välgrundade beslut.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner och installera JDK från[här](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java Library: Du måste ha Aspose.Tasks for Java-biblioteket. Du kan ladda ner den från[hemsida](https://releases.aspose.com/tasks/java/).

## Importera paket
Låt oss först importera de nödvändiga paketen för att arbeta med Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Steg 1: Läs käll-MPP-filen
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
// Läs käll-MPP-filen
Project project = new Project(dataDir + "project.mpp");
```
## Steg 2: Få uppgift och resurstilldelning
```java
// Få projektets första uppgift
Task task = project.getRootTask().getChildren().getById(1);
// Få projektets första resurstilldelning
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Steg 3: Generera tidsfasdata med platt kontur
```java
// Platt kontur är standardkonturen
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 4: Ändra Contour till Turtle
```java
// Ändra kontur till Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 5: Ändra Contour till BackLoaded
```java
// Ändra konturen till BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 6: Ändra Contour till FrontLoaded
```java
// Ändra konturen till FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 7: Ändra Contour till Bell
```java
// Ändra kontur till Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 8: Ändra Contour till EarlyPeak
```java
// Ändra kontur till EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 9: Ändra Contour till LatePeak
```java
// Ändra kontur till LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Steg 10: Ändra Contour till DoublePeak
```java
// Ändra kontur till DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Slutsats
den här handledningen har vi täckt hur man genererar tidsfasdata för resurstilldelningar med Aspose.Tasks för Java. Att förstå olika arbetskonturer kan hjälpa projektledare att effektivt hantera resursallokering och schemaläggning i sina projekt.
## FAQ's
### Kan jag använda Aspose.Tasks med andra Java-bibliotek?
Ja, Aspose.Tasks kan integreras med andra Java-bibliotek för att förbättra projekthanteringsmöjligheterna.
### Är Aspose.Tasks lämpligt för storskaliga företagsprojekt?
Absolut, Aspose.Tasks är designat för att hantera projekt av alla storlekar, inklusive storskaliga företagsprojekt.
### Ger Aspose.Tasks stöd för olika projektfilformat?
Ja, Aspose.Tasks stöder olika projektfilformat, inklusive MPP, XML och MPX.
### Kan jag anpassa arbetskonturer enligt mina projektkrav?
Ja, Aspose.Tasks tillåter användare att definiera anpassade arbetskonturer för att passa deras specifika projektbehov.
### Finns det ett communityforum där jag kan få hjälp med Aspose.Tasks?
 Ja, du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för stöd och diskussioner.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
